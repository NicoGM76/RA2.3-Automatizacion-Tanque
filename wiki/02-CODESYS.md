# 2. Implementación en CODESYS

## Entorno utilizado

La simulación se realizó en **CODESYS V3.5 SP22 Patch 3** utilizando **CODESYS Control Win V3 x64** como runtime.

La aplicación trabaja con una tarea cíclica de **20 ms**.

## Programa de control

La lógica final se validó en un POU de Structured Text equivalente al diseño Ladder:

```iecst
IF START THEN
    RUN := TRUE;
END_IF;

IF STOP THEN
    RUN := FALSE;
END_IF;

H1 := RUN AND B1 AND B2 AND NOT B3;
H2 := RUN AND B1 AND NOT B2 AND NOT B3;
H3 := RUN AND B1 AND B2 AND B3;
H4 := RUN AND NOT B1 AND NOT B2 AND NOT B3;
H5 := RUN AND ((B2 AND NOT B1) OR (B3 AND NOT B2));
```

La lógica Ladder equivalente se documenta en la página [Diseño y lógica](01-Diseno-y-logica).

## HMI

Se creó una visualización sencilla para operar y observar el sistema sin modificar las variables directamente desde la tabla de CODESYS.

La HMI incluye:

- Pulsador START.
- Pulsador STOP.
- Tres interruptores para B1, B2 y B3.
- Indicador RUN.
- Indicadores H1 a H5.

Los interruptores B1, B2 y B3 funcionan como variables conmutadas. START y STOP se comportan como pulsadores momentáneos.

### Identificación visual

| Indicador | Significado | Color utilizado |
|---|---|---|
| RUN | Sistema habilitado | Verde |
| H1 | Nivel correcto | Verde |
| H2 | Nivel bajo | Amarillo |
| H3 | Nivel alto | Rojo |
| H4 | Tanque vacío | Azul |
| H5 | Error de sensores | Gris |

## Validación realizada

Se comprobó que:

- START activa RUN.
- STOP desactiva RUN.
- Con RUN desactivado, las salidas permanecen apagadas.
- Las ocho combinaciones de B1, B2 y B3 producen el estado esperado.
- La HMI refleja correctamente los cambios de estado.

## Archivo del proyecto

El proyecto nativo utilizado para la simulación es **2.3.project**.

### Evidencias por agregar

En la versión final de la Wiki se recomienda incluir:

1. Captura del árbol del proyecto.
2. Captura del POU de control.
3. Captura de la HMI ejecutándose.
4. Captura de al menos un estado normal y un estado de error.
