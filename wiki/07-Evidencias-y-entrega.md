# 7. Evidencias y entrega

Esta página funciona como lista de control para la entrega final.

## Evidencias de CODESYS

- [x] Proyecto creado.
- [x] Lógica funcional.
- [x] Runtime ejecutado.
- [x] HMI creada.
- [x] START y STOP verificados.
- [x] Estados B1-B3 verificados.
- [ ] Subir capturas finales a la Wiki.

## Evidencias de OpenPLC

- [x] Proyecto creado.
- [x] Variables definidas.
- [x] Ladder construido.
- [ ] Compilar en la instalación final.
- [ ] Seleccionar/configurar Arduino UNO.
- [ ] Confirmar mapeo de pines.
- [ ] Ejecutar prueba física.
- [ ] Subir capturas finales.

## Evidencias de hardware

- [x] Arduino UNO disponible.
- [x] Protoboard disponible.
- [x] Pulsadores, switches, LEDs y resistencias disponibles.
- [x] Montaje preparado.
- [ ] Validación completa con OpenPLC.
- [ ] Fotografía final del prototipo funcionando.

## Archivos de entrega

Se recomienda entregar un ZIP organizado de esta forma:

```text
RA2.3-Automatizacion-Tanque/
├── CODESYS/
│   └── 2.3.project
├── OpenPLC/
│   └── Tanque/
├── Evidencias/
│   ├── CODESYS/
│   ├── OpenPLC/
│   └── Hardware/
└── README.md
```

Además:

- URL del repositorio.
- URL de la Wiki.
- Video de demostración.
- Archivo nativo de CODESYS.
- Proyecto de OpenPLC.
- Evidencia del montaje físico.

## Video final

En el video se debe mostrar, en orden:

1. Breve explicación de B1, B2 y B3.
2. Tabla de estados.
3. Funcionamiento en CODESYS.
4. HMI.
5. Ladder en OpenPLC.
6. Montaje físico.
7. Ejecución de varios estados normales.
8. Ejecución de al menos un estado de error.
9. STOP apagando el sistema.
