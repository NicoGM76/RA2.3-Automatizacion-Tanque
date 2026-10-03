# 5. Pruebas y resultados

## Pruebas en CODESYS

La lógica y la HMI fueron ejecutadas correctamente en CODESYS. Se probaron los estados normales y las combinaciones de error.

| B1 | B2 | B3 | Esperado | CODESYS | OpenPLC | Hardware |
|---:|---:|---:|---|---|---|---|
| 0 | 0 | 0 | H4 - Vacío | ✅ | ⏳ | ⏳ |
| 1 | 0 | 0 | H2 - Bajo | ✅ | ⏳ | ⏳ |
| 1 | 1 | 0 | H1 - Correcto | ✅ | ⏳ | ⏳ |
| 1 | 1 | 1 | H3 - Alto | ✅ | ⏳ | ⏳ |
| 0 | 1 | 0 | H5 - Error | ✅ | ⏳ | ⏳ |
| 0 | 0 | 1 | H5 - Error | ✅ | ⏳ | ⏳ |
| 1 | 0 | 1 | H5 - Error | ✅ | ⏳ | ⏳ |
| 0 | 1 | 1 | H5 - Error | ✅ | ⏳ | ⏳ |

## Prueba de START y STOP

También se verificó el comportamiento de habilitación:

| Acción | Resultado esperado | CODESYS |
|---|---|---|
| Pulsar START | RUN pasa a TRUE | ✅ |
| Soltar START | RUN se mantiene activo | ✅ |
| Pulsar STOP | RUN pasa a FALSE | ✅ |
| RUN = FALSE | H1-H5 apagadas | ✅ |

## Criterio para cerrar la validación

La validación completa del proyecto se considerará terminada cuando las mismas ocho combinaciones sean comprobadas también en OpenPLC y sobre el prototipo físico.

## Evidencias recomendadas

Para evitar llenar la Wiki con ocho capturas casi iguales, es suficiente mostrar:

- Una prueba de tanque vacío.
- Una prueba de nivel correcto.
- Una prueba de nivel alto.
- Una combinación de error.
- Una fotografía del prototipo funcionando.
- La tabla anterior con el resultado de las ocho combinaciones.
