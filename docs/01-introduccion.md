# 1. Introducción

La automatización industrial permite supervisar procesos mediante sensores, controladores y elementos de señalización o actuación.

En este proyecto se desarrolla un sistema para monitorear el nivel de líquido de un tanque utilizando tres señales digitales: **B1, B2 y B3**. A partir de sus combinaciones, el sistema determina si el tanque está vacío, presenta un nivel bajo, se encuentra en un nivel correcto o alcanza un nivel alto.

También se incluye una condición de seguridad para identificar combinaciones de sensores que no son físicamente coherentes. Cuando ocurre uno de estos casos se activa la salida **H5**, que representa un posible error de sensores.

La lógica de control se implementará mediante **Ladder Logic (LD)**. Primero se desarrollará y simulará en **CODESYS**, incluyendo una interfaz HMI, y posteriormente se validará mediante **OpenPLC** y un prototipo físico.
