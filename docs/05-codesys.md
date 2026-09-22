# 5. Implementación en CODESYS

## Estado

En desarrollo.

La implementación utiliza Ladder (LD2) e incluye las variables:

- B1, B2, B3
- START, STOP, RUN
- H1, H2, H3, H4, H5

La lógica START/STOP utiliza SET y RESET sobre RUN.

Las salidas H1-H5 se implementan como bobinas normales condicionadas por RUN y por los estados de B1, B2 y B3.

## Pendiente

- Capturas finales del Ladder.
- Validación de las ocho combinaciones.
- Diseño y capturas de la HMI.
- Explicación de la simulación.
