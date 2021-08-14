# Todo List

**Todolist** es el proyecto llevado a cabo en el curso de **Flask** en platzi.

## Proyecto TodoList

### Estructura del proyecto

![Estructura](https://static.platzi.com/media/user_upload/estructura_carpetas-203e5935-fb26-4503-875d-ff88afc8d239.jpg)

## Documentación

### Flask

**Flask** es un framework minimalista escrito en **Python** que permite crear aplicaciones web rápidamente y con un mínimo de líneas de código, busca que su infraestructura inicial sea lo más simple posible y pueda personalizarse fácilmente, puedes extender sus funcionalidades con las llamadas **Flask Extensions**.

#### Iniciando Flask:

- ** virtualenv:** es una herramienta para crear entornos aislados de Python.

- **pip:** es el instalador de paquetes para Python.

- **requirements.txt:** es el archivo en donde se colocará todas las dependencias a instalar en nuestra aplicación.

- **FLASK_APP:** es la variable para identificar el archivo donde se encuentra la aplicación.

- **Debugging**: es el proceso de identificar y corregir errores de programación.

- **Logging**: es una grabación secuencial en un archivo o en una base de datos de todos los eventos que afectan a un proceso particular.

#### Ciclos Request y Response

**Request-Response**: es uno de los métodos básicos que usan las computadoras para comunicarse entre sí, en el que la primera computadora envía una solicitud de algunos datos y la segunda responde a la solicitud.

Por lo general, hay una serie de intercambios de este tipo hasta que se envía el mensaje completo.

Por ejemplo: navegar por una página web es un ejemplo de comunicación de **request-response.**

**Request-response** se puede ver como una llamada telefónica, en la que se llama a alguien y responde a la llamada; es decir hacemos una petición y recibimos una respuesta.

**Macro**: son un conjunto de comandos que se invocan con una palabra clave, opcionalmente seguidas de parámetros que se utilizan como código literal. Los **Macros** son manejados por el compilador y no por el ejecutable compilado.

Los **macros** facilitan la actualización y mantenimiento de las aplicaciones debido a que su re-utilización minimiza la cantidad de código escrito necesario para escribir un programa.

En este ejemplo nuestra **macro** se vería de la siguiente manera:

    {% macro nav_link(endpoint, text) %}
        {% if request.endpoint.endswith(endpoint) %}
            <li class="active"><a href="{{ url_for(endpoint) }}">{{text}}</a></li>
        {% else %}
            <li><a href="{{ url_for(endpoint) }}">{{text}}</a></li>
        {% endif %}
    {% endmacro %}

Un ejemplo de uso de **macros** en Flask:

    {% from "macros.html" import nav_link with context %}
    <!DOCTYPE html>
    <html lang="en">
        <head>
        {% block head %}
            <title>My application</title>
        {% endblock %}
        </head>
        <body>
            <ul class="nav-list">
                {{ nav_link('home', 'Home') }}
                {{ nav_link('about', 'About') }}
                {{ nav_link('contact', 'Get in touch') }}
            </ul>
        {% block body %}
        {% endblock %}
        </body>
    </html>

Como podemos observar en la primera línea estamos llamando a **macros.html** que contiene todos nuestros macros, pero queremos uno en específico así que escribimos `import nav_link` para traer el macro deseado y lo renderizamos de esta manera en nuestro menú `{{ nav_link('home', 'Home') }}`.

#### Códigos de error

- **100:** no son **errores** sino mensajes informativos. Como usuario nunca los verás, sino que entre bambalinas indica que la petición se ha recibido y se continúa el proceso.

- **200:** estos **códigos** también indican que todo ha ido correctamente. La petición se ha recibido, se ha procesado y se ha devuelto satisfactoriamente. Por tanto, nunca los verás en tu navegador, pues significan que todo ha ido bien.

- **300:** están relacionados con **redirecciones**. Los servidores usan estos códigos para indicar al navegador que la página o recurso que han pedido se ha movido de sitio. Como usuario, no verás estos **códigos**, aunque gracias a ellos una página te podría redirigir automáticamente a otra.

- **400:** corresponden a **errores** del cliente y con frecuencia sí los verás. Es el caso del conocido **error 404**, que aparece cuando la página que has intentado buscar no existe. Es, por tanto, un **error** del cliente (la dirección web estaba mal).

- **500:** mientras que los **códigos** de estado 400 implican **errores** por parte del cliente (es decir, de parte tuya, tu navegador o tu conexión), los errores 500 son **errores** desde la parte del servidor. Es posible que el servidor tenga algún problema temporal y no hay mucho que puedas hacer salvo probar de nuevo más tarde.

#### Framework

**Framework**: es un conjunto estandarizado de conceptos, prácticas y criterios para enfocar un tipo de problemática particular que sirve como referencia, para enfrentar y resolver nuevos problemas de índole similar.

#### Session

**SESSION:** es un intercambio de información interactiva semipermanente, también conocido como diálogo, una conversación o un encuentro, entre dos o más dispositivos de comunicación, o entre un ordenador y usuario.

#### Flask-testing

La etapa de pruebas se denomina **testing** y se trata de una investigación exhaustiva, no solo técnica sino también empírica, que busca reunir información objetiva sobre la calidad de un proyecto de software, por ejemplo, una aplicación móvil o un sitio web.

El objetivo del **testing** no solo es encontrar _fallas_ sino también aumentar la confianza en la calidad del producto, facilitar información para la toma de decisiones y detectar oportunidades de mejora.
