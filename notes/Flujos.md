# Flujos Manuales / Instantáneos

## For a selected record (V3) / Para un registro seleccionado (V3) (Business Central)

[Enlace a la documentación oficial](https://learn.microsoft.com/es-es/connectors/dynamicssmbsaas/#para-un-registro-seleccionado-(v3))

### ➜\] Parametros

- **Page or table** `string` 
    - Dónde se muestra y ejecuta el flujo
    - Ej: `PAGE21`, `TABLE18`

###   \]➜ Salidas

La salida depende de la API usada. En este caso, asumiendo la api V2.0, estos son algunos valores de salida:

- **System Id** `string`
    - Identificador interno del Registro seleccionado
    - Ej: `79f2a067-b215-f111-ac6a-6045bdfd99bf`
- **N.º** `string`
    - Número de fila del registro
    - Ej: `10000`
- **Blocked** `string`
    - Ej: `All`

## For a selected file / Para un archivo seleccionado (Share Point)

[Enlace a la documentación oficial](https://learn.microsoft.com/es-es/connectors/sharepointonline/#para-un-archivo-seleccionado)

###   \]➜ Salidas

- **ID** `integer`
- **File Name** `string`
    - Incluye extension. Ej: `imagen_01.jpg`
- **User email** y **User name** / Nombre de usuario y Correo electronico de usuario `string`
    - Ambos tiene una version **encoded** en base64 y una normal en plain text que puede ser confusa
    - '*user email encoded*' se muestra solo como '*user email*' y el verdadero '*user email*' no se muestra, pero es accesible con `triggerOutputs()?['headers']?['x-ms-user-email']`. Lo mismo para user name.