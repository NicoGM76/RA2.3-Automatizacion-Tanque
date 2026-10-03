# 6. Conclusiones

El diseño permite representar el nivel de un tanque mediante tres entradas digitales y clasificar todas las combinaciones posibles en estados normales o de error.

La condición **000** se trata correctamente como tanque vacío, mientras que H5 se reserva para combinaciones físicamente incoherentes. Esto evita interpretar una condición normal como una falla.

La variable RUN permite separar la lógica de nivel de la habilitación general del sistema. START activa el proceso y STOP permite apagar todas las salidas sin modificar el estado de los sensores.

La implementación fue validada en CODESYS y la HMI permitió comprobar la lógica de una forma visual y sencilla. La misma lógica fue construida en Ladder para OpenPLC.

La conclusión definitiva sobre la integración con hardware debe escribirse después de realizar la prueba con Arduino UNO. Hasta ese momento, no se debe presentar la validación física como finalizada.

## Resultado esperado al finalizar

Si OpenPLC y el montaje físico reproducen la misma tabla de verdad comprobada en CODESYS, se podrá concluir que el diseño lógico se mantiene consistente entre simulación, PLC abierto y prototipo físico.
