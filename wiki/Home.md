# RA2.3 - Automatización del monitoreo de nivel de un tanque

Esta Wiki documenta el diseño, implementación y validación de un sistema de automatización para monitorear el nivel de un tanque mediante tres señales digitales de nivel, una lógica de habilitación START/STOP y cinco salidas de estado.

El sistema trabaja con **B1, B2 y B3** como señales de nivel. A partir de su combinación se determina si el tanque está vacío, en nivel bajo, en nivel correcto, en nivel alto o si existe una combinación incoherente de sensores.

## Estado general del proyecto

| Etapa | Estado |
|---|---|
| Diseño de la lógica combinacional | ✅ Completado |
| Tabla de verdad | ✅ Completada |
| Simulación en CODESYS | ✅ Validada |
| HMI en CODESYS | ✅ Validada |
| Implementación Ladder en OpenPLC | ✅ Construida |
| Configuración de Arduino en OpenPLC | ⏳ Pendiente de validación |
| Montaje físico | 🟡 Preparado |
| Pruebas físicas finales | ⏳ Pendientes |
| Video de demostración | ⏳ Pendiente |

## Variables principales

| Variable | Función |
|---|---|
| START | Habilita el sistema |
| STOP | Deshabilita el sistema |
| RUN | Memoria de funcionamiento |
| B1 | Sensor de nivel inferior |
| B2 | Sensor de nivel medio |
| B3 | Sensor de nivel superior |
| H1 | Nivel correcto |
| H2 | Nivel bajo |
| H3 | Nivel alto |
| H4 | Tanque vacío |
| H5 | Error o incoherencia de sensores |

## Navegación

- [Diseño y lógica](01-Diseno-y-logica)
- [Implementación en CODESYS](02-CODESYS)
- [Implementación en OpenPLC](03-OpenPLC)
- [Montaje físico](04-Hardware)
- [Pruebas y resultados](05-Pruebas-y-resultados)
- [Conclusiones](06-Conclusiones)
- [Evidencias y entrega](07-Evidencias-y-entrega)

> **Nota:** La combinación B1=0, B2=0 y B3=0 representa un tanque vacío. No se considera un error.
