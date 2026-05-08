# Flujos Manuales / Instantáneos

## For a selected record (V3) #BusinessCentral
### ➜\] Parametros

- **Page or table** `string` 
    - Dónde se muestra y ejecuta el flujo
    - Ej: `PAGE21`, `TABLE18`
### \]➜ Salidas

- **System Id** `string`
    - Identificador interno del Registro seleccionado
    - Ej: `79f2a067-b215-f111-ac6a-6045bdfd99bf`
- **N.º** `string`
    - Número de fila del registro
    - Ej: `10000`
- **Blocked** `string`
    - Ej: `All`

## For a selected file #SharePoint

### \]➜ Salidas

- **ID** `integer`
- **File Name** `string`
    - Incluye extension. Ej: `imagen_01.jpg`
- **User email** y **User name** `string`
    - Ambos tiene una version **encoded** en base64 y una normal en plain text que puede ser confusa
    - '*user email encoded*' se muestra solo como '*user email*' y el verdadero '*user email*' no se muestra, pero es accesible con `triggerOutputs()?['headers']?['x-ms-user-email']`. Lo mismo para user name.