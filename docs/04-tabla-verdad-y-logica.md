# 4. Tabla de verdad y lógica

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

La condición **000** no representa una falla: corresponde al tanque vacío.

Los estados de error aparecen cuando un sensor ubicado en una posición superior indica presencia de líquido mientras un sensor inferior no lo hace. Estas combinaciones pueden representar un fallo de sensor o una señal incoherente.

## Ecuaciones lógicas

```text
H1 = B1 AND B2 AND NOT B3
H2 = B1 AND NOT B2 AND NOT B3
H3 = B1 AND B2 AND B3
H4 = NOT B1 AND NOT B2 AND NOT B3
H5 = (B2 AND NOT B1) OR (B3 AND NOT B2)
```

En la implementación de CODESYS se utiliza además la variable **RUN** para habilitar el sistema mediante START y STOP.
