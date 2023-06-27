# Profundizando en la manipulación de archivos JSON con Pandas

Pandas es una biblioteca de Python especialmente diseñada para facilitar la manipulación y el análisis de datos. Es una herramienta esencial para cualquier científico de datos o analista de datos que trabaje con Python. Una de las características más útiles de Pandas es su capacidad para interactuar con una variedad de formatos de datos, incluyendo JSON (JavaScript Object Notation), que es un formato de intercambio de datos comúnmente utilizado en la web.

## Instalando Pandas

La instalación de pandas es una tarea sencilla gracias a pip, el sistema de gestión de paquetes de Python. Para instalar pandas, simplemente necesitas ejecutar el siguiente comando en tu terminal o prompt de comandos:

```python
pip install pandas
```

Este comando se encargará de instalar pandas junto con todas sus dependencias necesarias.

## Importando Pandas a tu script

Después de la instalación, debes importar pandas a tu script de Python para poder utilizar sus características. Por convención, pandas se suele importar como 'pd', lo que permite acceder a sus métodos de manera más concisa:

```python
import pandas as pd
```

Para el caso práctico que vamos a tratar, también necesitaremos la biblioteca `requests` de Python, que nos permite hacer peticiones HTTP. Puedes importarla de la siguiente manera:

```python
import requests
```

## Leyendo archivos JSON con Pandas

Pandas proporciona la función `read_json()` para leer datos de archivos JSON y convertirlos en un DataFrame, que es la principal estructura de datos en pandas. Aquí está un ejemplo de cómo hacerlo:

```python
df = pd.read_json('data.json')
```

En este ejemplo, 'data.json' es el nombre del archivo JSON que queremos leer. La función `read_json()` devuelve un DataFrame que se guarda en la variable df.

Para obtener una vista rápida de los datos, puedes usar el método `head()`, que muestra las primeras 5 filas del DataFrame:

```python
df.head()
```

## Escribiendo DataFrames en archivos JSON

Además de leer archivos JSON, pandas también puede escribir DataFrames en archivos JSON con el método `to_json()`. Aquí tienes un ejemplo:

```python
df.to_json('new_data.json')
```

En este caso, 'new_data.json' es el nombre del nuevo archivo JSON que queremos crear.

## Aplicación Práctica: Interactuando con APIs JSON

Para demostrar cómo trabajar con archivos JSON en pandas, vamos a obtener algunos datos en formato JSON de una API en línea llamada JSONPlaceholder.

Primero, haremos una petición GET a la API con la biblioteca `requests`:

```python
response = requests.get('https://jsonplaceholder.typicode.com/posts')
data = response.json()
```

Luego, convertiremos estos datos JSON en un DataFrame de pandas:

```python
df = pd.DataFrame(data)
```

Para inspeccionar nuestros datos, utilizaremos de nuevo el método `head()`:

```python
df.head()
```

Ahora, supongamos que queremos agregar una columna que indique si la longitud del título de cada post es mayor que la media de todas las longitudes de título. Podemos hacerlo con la siguiente línea de código:

```python
df['Titulo_Largo'] = df['title'].apply(lambda x: len(x)) > df['title'].apply(lambda x: len(x

)).mean()
```

Finalmente, vamos a guardar este DataFrame con la nueva columna en un nuevo archivo JSON:

```python
df.to_json('posts_con_titulo_largo.json')
```

Y ahí lo tienes: ahora sabes cómo leer y escribir archivos JSON con pandas, así como cómo interactuar con APIs JSON. Pero recuerda, estas son solo las operaciones básicas que puedes realizar con pandas. Esta potente biblioteca ofrece muchas otras funcionalidades que te ayudarán a manipular y analizar tus datos de manera efectiva. ¡Sigue explorando!
