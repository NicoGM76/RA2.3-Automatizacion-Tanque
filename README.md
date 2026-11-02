# RA2.3 - Automatización del monitoreo de nivel de un tanque

Proyecto individual de automatización industrial para monitorear el nivel de un tanque mediante lógica combinacional.

## Objetivo general

Diseñar e implementar un sistema capaz de identificar el estado de nivel de un tanque utilizando tres señales de entrada (B1, B2 y B3), mostrar el estado mediante una HMI en CODESYS y validar la solución con OpenPLC y hardware real.

## Estados del sistema

- **H1:** Nivel correcto
- **H2:** Nivel bajo
- **H3:** Nivel alto
- **H4:** Tanque vacío
- **H5:** Error de sensores

La combinación **B1=0, B2=0, B3=0** representa tanque vacío y no se considera un error.

## Documentación

La documentación del proyecto se está organizando en la carpeta [docs](./docs/):

1. [Introducción](./docs/01-introduccion.md)
2. [Objetivos](./docs/02-objetivos.md)
3. [Diseño de la solución](./docs/03-diseno-solucion.md)
4. [Tabla de verdad y lógica](./docs/04-tabla-verdad-y-logica.md)
5. [Implementación en CODESYS](./docs/05-codesys.md)
6. [Implementación en OpenPLC](./docs/06-openplc.md)
7. [Montaje físico](./docs/07-montaje-fisico.md)
8. [Pruebas y resultados](./docs/08-pruebas-resultados.md)
9. [Conclusiones](./docs/09-conclusiones.md)
10. [Referencias](./docs/10-referencias.md)

> Nota: estas páginas sirven como base de la Wiki final de GitHub. Las secciones de CODESYS, OpenPLC y pruebas se completarán con capturas y resultados finales.

---

# Continuación RA3.2 - Gemelo Digital / IoT

El proyecto continúa en **RA3.2**, donde el activo físico y la HMI desarrollados en RA2.3 se integran mediante **Modbus** y posteriormente con una plataforma IoT.

📘 **[Ver avance de la Wiki RA3.2 - Gemelo Digital](./docs/11-ra3-2-gemelo-digital.md)**

Estado actual de RA3.2:

- ✅ Activo físico reutilizado y validado.
- ✅ Lógica OpenPLC conservada.
- ✅ Variante `Tanque_V2_Modbus` configurada con Modbus RTU.
- 🟡 Comunicación Arduino ↔ CODESYS en implementación.
- ⏳ Publicación y control desde plataforma IoT pendientes.
