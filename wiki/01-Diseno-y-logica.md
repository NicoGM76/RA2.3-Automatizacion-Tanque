# 1. Diseño y lógica del sistema

## Descripción del proceso

Los tres sensores se ubican conceptualmente a diferentes alturas del tanque:

```text
        TANQUE
     ┌───────────┐
B3 ──┤ ●         │  Nivel superior
     │           │
B2 ──┤ ●         │  Nivel medio
     │           │
B1 ──┤ ●         │  Nivel inferior
     └───────────┘
```

Un estado físicamente coherente debe llenarse desde abajo hacia arriba. Por ejemplo, si B2 está activo, B1 también debería estar activo. Si B3 está activo, B1 y B2 deberían estar activos.

## Tabla de verdad

| B1 | B2 | B3 | Salida | Estado |
|---:|---:|---:|---|---|
| 0 | 0 | 0 | H4 | Tanque vacío |
| 1 | 0 | 0 | H2 | Nivel bajo |
| 1 | 1 | 0 | H1 | Nivel correcto |
| 1 | 1 | 1 | H3 | Nivel alto |
| 0 | 1 | 0 | H5 | Error |
| 0 | 0 | 1 | H5 | Error |
| 1 | 0 | 1 | H5 | Error |
| 0 | 1 | 1 | H5 | Error |

## Ecuaciones lógicas

Todas las salidas se habilitan únicamente cuando **RUN = TRUE**.

```text
H1 = RUN AND B1 AND B2 AND NOT B3
H2 = RUN AND B1 AND NOT B2 AND NOT B3
H3 = RUN AND B1 AND B2 AND B3
H4 = RUN AND NOT B1 AND NOT B2 AND NOT B3
H5 = RUN AND ((B2 AND NOT B1) OR (B3 AND NOT B2))
```

La salida **H5** agrupa las combinaciones imposibles o incoherentes. Esto permite diferenciar un tanque realmente vacío de una posible falla de sensores.

## Lógica START/STOP

El sistema utiliza una variable interna **RUN**:

- START activa RUN.
- RUN permanece activo después de soltar START.
- STOP desactiva RUN.
- Si RUN está desactivado, H1 a H5 permanecen apagadas.

Referencia Ladder:

```text
[ START ] ------------------------------ (S RUN)

[ STOP  ] ------------------------------ (R RUN)
```

## Ladder de las salidas

```text
[RUN]--[B1]--[B2]--[/B3]---------------(H1)

[RUN]--[B1]--[/B2]--[/B3]--------------(H2)

[RUN]--[B1]--[B2]--[B3]----------------(H3)

[RUN]--[/B1]--[/B2]--[/B3]-------------(H4)

             +--[B2]--[/B1]--+
[RUN]--------|                |---------(H5)
             +--[B3]--[/B2]--+
```
