# Conectores y Acciones

Lista de conectores y notas sobre entradas, salidas y caracteristicas relevantes

## Dynamics 365 Business Central

### Find records (V3)

#### <img src="icons/square-arrow-right-enter.svg" width="18"/> Parametros

- **API category** 
    - La API usada para acceder a los datos. Por defecto usa `v2.0`. En caso esta API no exponga los campos que necesitas, puedes seleccionar tu propia API.
- **Filter Query**
    - Aplica un filtro de BC a los resultados que se obtendrán. `<field> <operator> <value>`. Ej: `age ge 40 and status eq 'hired'`

## Office 365 Outlook

### Send an email (V2)

- El cuerpo del email acepta HTML como entrada. Para ello, cambiar a 'code view' con el botón `</>`
- Si el formato es complejo, es mejor generarlo desde afuera o guardarlo en una variable antes de añadirlo al cuerpo del correo.

## SharePoint

### Get file properties

#### <img src="icons/square-arrow-right-enter.svg" width="18"/> Parametros

- **Id** `integer`

#### <img src="icons/square-arrow-right-exit.svg" width="18"/> Salidas

- **File Identifier** `string`

### Get file content

#### <img src="icons/square-arrow-right-enter.svg" width="18"/> Parametros

- **File Identifier** `string`
#### <img src="icons/square-arrow-right-exit.svg" width="18"/> Salidas

- **File Content** `binary`

### Update item

#### <img src="icons/square-arrow-right-enter.svg" width="18"/> Parametros

- **Id** `Integer`

## Word Online (Business)

### Populate a Microsoft Word template

El documento deberá tener por lo menos un campo `control de contenido de texto sin formato`.

Estos campos solo pueden ser añadidos desde la versión de escritorio de Word, luego de activar "Programador" en la cinta de opciones. (`Archivo > Opciones > Personalizar lista de opciones`)

#### <img src="icons/square-arrow-right-exit.svg" width="18"/> Salidas

- **Microsoft Word document** `binary`

### Convert Word Documento to PDF

#### <img src="icons/square-arrow-right-enter.svg" width="18"/> Parametros

- **File** `string`
    - Espera la ruta al documento en relación a la *Biblioteca de documentos* escogida
        - Si el archivo esta en la raiz de la biblioteca, basta con el nombre. ej: `documento.docx`
        - Si el archivo esta dentro de una carpeta usar la ruta. ej: `folder/documento.docx`
        - No encontrará el documento si se da una ruta absoluta. `Shared Documents/documento.docx`

#### <img src="icons/square-arrow-right-exit.svg" width="18"/> Salidas

- **PDF document** `binary`