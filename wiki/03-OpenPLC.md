# 3. Implementación en OpenPLC

## Objetivo

OpenPLC se utiliza para reproducir la misma lógica validada en CODESYS y posteriormente conectarla con el Arduino UNO del prototipo físico.

## Variables y direcciones

| Variable | Dirección |
|---|---|
| Start | %IX0.0 |
| Stop | %IX0.1 |
| B1 | %IX0.2 |
| B2 | %IX0.3 |
| B3 | %IX0.4 |
| Run | Variable interna |
| H1 | %QX0.0 |
| H2 | %QX0.1 |
| H3 | %QX0.2 |
| H4 | %QX0.3 |
| H5 | %QX0.4 |

## Redes Ladder

El programa contiene siete redes principales:

1. START activa **Run** mediante una bobina SET.
2. STOP desactiva **Run** mediante una bobina RESET.
3. H1 representa nivel correcto.
4. H2 representa nivel bajo.
5. H3 representa nivel alto.
6. H4 representa tanque vacío.
7. H5 detecta combinaciones incoherentes mediante dos ramas en paralelo.

Referencia:

```text
[Start]---------------------------------(S Run)

[Stop]----------------------------------(R Run)

[Run]--[B1]--[B2]--[/B3]---------------(H1)

[Run]--[B1]--[/B2]--[/B3]--------------(H2)

[Run]--[B1]--[B2]--[B3]----------------(H3)

[Run]--[/B1]--[/B2]--[/B3]-------------(H4)

             +--[B2]--[/B1]--+
[Run]--------|                |---------(H5)
             +--[B3]--[/B2]--+
```

## Estado actual

El proyecto Ladder ya está construido en el archivo `main.ld`.

En este momento la configuración del proyecto todavía aparece como **OpenPLC Simulator** y el archivo de mapeo de pines está vacío. Por lo tanto, antes de afirmar que la prueba física está terminada, falta seleccionar/configurar el Arduino UNO y validar el mapeo real de entradas y salidas.

## Mapeo físico previsto

| Señal | Arduino UNO |
|---|---|
| START | D2 |
| STOP | D3 |
| B1 | D4 |
| B2 | D5 |
| B3 | D6 |
| H1 | D8 |
| H2 | D9 |
| H3 | D10 |
| H4 | D11 |
| H5 | D12 |

Cuando se complete la carga y prueba sobre hardware, esta página debe actualizarse con el resultado real y las capturas correspondientes.
