Por supuesto, aquí están las notas para una clase sobre cómo trabajar con archivos JSON en pandas. Para este caso práctico, usaré datos obtenidos de JSONPlaceholder, que es un servicio en línea gratuito que genera datos JSON de prueba.

```markdown
# Trabajando con archivos JSON en Pandas

Pandas es una biblioteca de Python que facilita la manipulación y el análisis de datos. Entre sus funcionalidades, permite trabajar con archivos JSON, un formato común para el intercambio de datos.

## Instalación de Pandas

Para instalar pandas, puedes utilizar pip:

```python
pip install pandas
```

## Importando Pandas

Una vez instalado, debes importar pandas en tu script de Python.

```python
import pandas as pd
```

Además, para este caso práctico, necesitaremos la biblioteca `requests` para hacer una petición a la API de JSONPlaceholder.

```python
import requests
```

## Leyendo un archivo JSON

Para leer un archivo JSON, utilizamos la función `read_json()`.

```python
df = pd.read_json('data.json')
```

Puedes visualizar las primeras líneas del DataFrame utilizando `head()`.

```python
df.head()
```

## Escribiendo en un archivo JSON

Si quieres guardar tu DataFrame en un archivo JSON, puedes usar la función `to_json()`.

```python
df.to_json('new_data.json')
```

## Caso Práctico

Vamos a obtener algunos datos en formato JSON de la API de JSONPlaceholder.

```python
response = requests.get('https://jsonplaceholder.typicode.com/posts')
data = response.json()
```

Ahora, convertiremos estos datos a un DataFrame.

```python
df = pd.DataFrame(data)
```

Puedes revisar los primeros registros con `head()`.

```python
df.head()
```

Supongamos que queremos agregar una columna que indique si la longitud del título del post es mayor que la media. Podemos hacer esto de la siguiente manera:

```python
df['Titulo_Largo'] = df['title'].apply(lambda x: len(x)) > df['title'].apply(lambda x: len(x)).mean()
```

Finalmente, vamos a guardar este nuevo DataFrame con la columna adicional en un nuevo archivo JSON.

```python
df.to_json('posts_con_titulo_largo.json')
```

¡Y eso es todo! Ahora sabes cómo leer y escribir archivos JSON con pandas. Recuerda que estos son solo los conceptos básicos. Pandas tiene muchas otras funcionalidades útiles para la manipulación y el análisis de datos. ¡Sigue explorando!
