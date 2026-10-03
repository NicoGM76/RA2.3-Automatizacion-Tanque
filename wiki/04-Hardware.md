# 4. Montaje físico

## Componentes utilizados

- 1 Arduino UNO.
- 1 protoboard.
- 2 pulsadores para START y STOP.
- 3 switches para B1, B2 y B3.
- 5 LEDs para H1, H2, H3, H4 y H5.
- 5 resistencias de 220 Ω para los LEDs.
- Resistencias de 10 kΩ para las entradas.
- Cables jumper.
- Cable USB.

## Distribución de pines

| Pin | Elemento | Tipo |
|---|---|---|
| D2 | START | Entrada |
| D3 | STOP | Entrada |
| D4 | B1 | Entrada |
| D5 | B2 | Entrada |
| D6 | B3 | Entrada |
| D8 | H1 | Salida |
| D9 | H2 | Salida |
| D10 | H3 | Salida |
| D11 | H4 | Salida |
| D12 | H5 | Salida |

## Conexión de las entradas

Cada entrada utiliza una resistencia de **10 kΩ** como pull-down:

```text
5 V
 |
[Pulsador / Switch]
 |
 +----------> Entrada Arduino
 |
[10 kΩ]
 |
GND
```

De esta forma, la entrada permanece en 0 lógico mientras el elemento está abierto y pasa a 1 lógico cuando se cierra.

## Conexión de los LEDs

Cada salida se conecta de la siguiente forma:

```text
Pin Arduino
    |
   LED
    |
  220 Ω
    |
   GND
```

Las resistencias de 220 Ω limitan la corriente de los LEDs.

## Consideraciones del montaje

- Todos los componentes deben compartir la misma referencia de GND.
- Se debe verificar la polaridad de cada LED.
- El cableado debe revisarse antes de energizar el montaje.
- La validación final debe realizarse después de configurar OpenPLC con el Arduino UNO.

## Evidencia final

Agregar una fotografía general del prototipo y, si es posible, una fotografía cercana de la distribución de entradas y salidas.
