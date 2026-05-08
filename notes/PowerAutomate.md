# Power Automate

## Conceptos

- **Flujos** Secuencias de instrucciones que realizan una tarea.
- **Acciones** Operaciones como 'enviar un email', 'descargar un archivo' o 'crear una variable'
- **Conectores** Conjunto de acciones relacionadas que proporciona un *publisher*
- **Soluciones** Paquetes que contienen todos los flujos, conectores, variables, etc. que necesitan para funcionar en un entorno.
	- **Administradas** Destinadas a producción. Como una *release* oficial o código compilado
	- **No administradas** Destinadas a desarrollo. Como una rama *dev* o el código fuente de tu aplicación
- **Entornos** Espacios independientes donde existen y se ejecutan las soluciones.
- **Variables de entorno** Datos configurables que se deben definir al implantarse en un entorno.

## Objetos y acceso a datos

Automate trabaja por detrás con objetos json y sigue una sintaxis propia para acceder a su información. La formula es:
`<donde buscar>('<nombre del obj>')`

Algunos ejemplos:
- **Variables** `variables('mi variable')`
- **Variables de entorno** `parameters('my display name (unique name)')`
- **Salidas del trigger** `triggerOutputs()` o `triggerBody()`
- **Salidas de una acción** `outputs('mi acción')`

También se puede añadir `?['mi clave']` para buscar valores específicos dentro del objeto.
Ej: `variables('Persona 1')?['info_contacto']?['telefonos']?['casa']`

### Sinónimos

`body('mi accion')` es un sinónimo de `outputs('mi accion')?['body']`
Esto es util en algunas acciones porque así podemos ignorar `statusCode`, `headers`, etc. Casi siempre, lo que nos interesa estará dentro de `body`.

## Serialización de carácteres especiales

Cuando se trabaja con HTTP (Ej: Conectores de Share Point y Business Central), algunos carácteres como `%`, ` `, `:` pueden ser cifrados a XML (`_x0025_`, `_x0020_`, `_x003A_`) cuando se traducen a strings.

El valor que tomen se puede calcular [consultando este documento](https://www.w3.org/Style/XSL/TestSuite/results/4/XEP/symbol.pdf) o usando sus valores unicode y esta regla de conversión:
`U+<number>` → `_x<number>_`