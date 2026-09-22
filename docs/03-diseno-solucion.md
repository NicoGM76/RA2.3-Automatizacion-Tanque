# 3. Diseño de la solución

El sistema utiliza tres señales digitales ubicadas conceptualmente a diferentes alturas del tanque:

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

Las salidas representan el estado del proceso:

- **H1:** nivel correcto.
- **H2:** nivel bajo.
- **H3:** nivel alto.
- **H4:** tanque vacío.
- **H5:** error de sensores.

## Prototipo físico

Para la validación con hardware, las entradas B1, B2 y B3 serán representadas mediante tres switches. También se utilizarán dos pulsadores para START y STOP.

Las salidas H1 a H5 serán representadas mediante cinco LEDs.

Esquema conceptual:

```text
3 switches (B1, B2, B3)
          │
2 pulsadores (START, STOP)
          │
          ▼
      Arduino UNO
      + OpenPLC
          │
          ▼
     5 LEDs (H1-H5)
```
