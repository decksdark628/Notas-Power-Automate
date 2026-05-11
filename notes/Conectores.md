# Conectores y Acciones

Lista de conectores y notas sobre entradas, salidas y caracteristicas relevantes

## Dynamics 365 Business Central

[Enlace a la documentación oficial](https://learn.microsoft.com/es-es/connectors/dynamicssmbsaas/)

### Find records (V3) / Buscar registros (V3)

#### ➜\] Parametros

- **API category** / Categoria de API
    - La API usada para acceder a los datos. Por defecto usa `v2.0`. En caso esta API no exponga los campos que necesitas, puedes seleccionar tu propia API.
- **Filter Query** / Consulta de filtro
    - Aplica un filtro de BC a los resultados que se obtendrán. `<field> <operator> <value>`. Ej: `age ge 40 and status eq 'hired'`

## Office 365 Outlook

[Enlace a la documentación oficial](https://learn.microsoft.com/es-es/connectors/office365/)

### Send an email (V2) / Enviar un correo electrónico (V2)

- El cuerpo del email acepta HTML como entrada. Para ello, cambiar a 'code view' con el botón `</>`
- Si el formato es complejo, es mejor generarlo desde afuera o guardarlo en una variable antes de añadirlo al cuerpo del correo.

## SharePoint

[Enlace a la documentación oficial](https://learn.microsoft.com/es-es/connectors/sharepointonline/)

### Get file properties / Obtener las propiedades de archivos

#### ➜\] Parametros

- **Id** `integer`

####  \]➜ Salidas

- **File Identifier** `string`

### Get file content / Obtener contenido de archivo

#### ➜\] Parametros

- **File Identifier** / Identificador de archivo `string`

####  \]➜ Salidas

- **File Content** / Contenido del archivo `binary`

### Update item / Actualizar elemento

#### ➜\] Parametros

- **Id** `Integer`

## Word Online (Business) / Word Online (Empresa)

[Enlace a la documentación oficial](https://learn.microsoft.com/es-es/connectors/wordonlinebusiness/)

### Populate a Microsoft Word template / Rellenar una plantilla de Microsoft Word

El documento deberá tener por lo menos un campo `control de contenido de texto sin formato`.

Estos campos solo pueden ser añadidos desde la versión de escritorio de Word, luego de activar "Programador" en la cinta de opciones. (`Archivo > Opciones > Personalizar lista de opciones`)

####  \]➜ Salidas

- **Microsoft Word document** `binary`

### Convert Word Documento to PDF / Convertir documento de Word en PDF

#### ➜\] Parametros

- **File** / Archivo `string`
    - Espera la ruta al documento en relación a la *Biblioteca de documentos* escogida
        - Si el archivo esta en la raiz de la biblioteca, basta con el nombre. ej: `documento.docx`
        - Si el archivo esta dentro de una carpeta usar la ruta. ej: `folder/documento.docx`
        - No encontrará el documento si se da una ruta absoluta. `Shared Documents/documento.docx`

####  \]➜ Salidas

- **PDF document** / Documento PDF`binary`