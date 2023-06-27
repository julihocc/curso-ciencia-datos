# Manipulación y análisis de DataFrames con Pandas

Los DataFrames son una estructura de datos bidimensional en la biblioteca de Pandas, similar a una hoja de cálculo de Excel o una tabla SQL. Son extremadamente flexibles, ya que permiten almacenar y manipular datos de diferentes tipos (enteros, flotantes, strings, etc.) y también pueden cambiar de tamaño, lo que permite agregar y eliminar filas o columnas.

## Configuración e instalación de Pandas y Seaborn

Pandas es la principal biblioteca que usaremos para manipular nuestros DataFrames. Seaborn, por otro lado, es una biblioteca de visualización de datos basada en Matplotlib que proporciona una interfaz de alto nivel para crear gráficos estadísticos atractivos.

Para instalar pandas y seaborn, debemos utilizar pip, el sistema de gestión de paquetes de Python. Puedes hacerlo ejecutando el siguiente comando en tu terminal o en la línea de comandos de tu entorno de desarrollo integrado (IDE):

```python
pip install pandas seaborn
```

## Importación de Pandas y Seaborn a tu script

Una vez que se han instalado ambas bibliotecas, debemos importarlas en nuestro script de Python para poder utilizar sus funciones y métodos. Por convención, pandas se importa como 'pd' y seaborn como 'sns':

```python
import pandas as pd
import seaborn as sns
```

## Carga de un DataFrame predefinido

Seaborn viene con algunos conjuntos de datos predefinidos para ayudar a los usuarios a practicar la manipulación de datos y la creación de gráficos. Uno de estos conjuntos de datos es 'iris', que contiene información sobre varias características de las flores de iris. Para cargar este conjunto de datos en un DataFrame de pandas, utilizamos el método `load_dataset()` de seaborn:

```python
df = sns.load_dataset('iris')
```

Para echar un vistazo rápido a las primeras líneas de nuestro DataFrame, utilizamos el método `head()`:

```python
df.head()
```

## Inspección de DataFrames

Es crucial familiarizarse con nuestros datos antes de comenzar a manipularlos o analizarlos. Pandas proporciona varias formas de inspeccionar un DataFrame.

### Forma de un DataFrame

La propiedad `shape` nos da una tupla que representa la cantidad de filas y columnas en el DataFrame:

```python
df.shape
```

### Nombres de las columnas

La propiedad `columns` nos proporciona una lista con los nombres de todas las columnas en el DataFrame:

```python
df.columns
```

### Tipos de datos

La propiedad `dtypes` nos muestra el tipo de datos almacenados en cada columna:

```python
df.dtypes
```

### Resumen estadístico

El método `describe()` nos proporciona un resumen estadístico del DataFrame, que incluye la media, la desviación estándar, los valores mínimos y máximos, y los percentiles de cada columna numérica:

```python
df.describe()
```

## Selección de datos

Pandas ofrece varias formas de seleccionar datos específicos dentro de un DataFrame.

### Selección de columnas

Podemos seleccionar una columna específica utilizando su nombre:

```python
df['species']
```

### Selección de filas

También podemos seleccionar un rango de filas utilizando índices de inicio y fin:

```python
df[10:

20]
```

O podemos seleccionar filas que cumplan con una condición específica:

```python
df[df['sepal_length'] > 5.0]
```

## Modificación de DataFrames

Los DataFrames de pandas son mutables, lo que significa que podemos modificarlos agregando nuevas columnas o cambiando los valores existentes.

Por ejemplo, podemos agregar una nueva columna que contenga el doble de la longitud del sépalo:

```python
df['double_sepal_length'] = df['sepal_length'] * 2
```

También podemos cambiar los valores en una columna que cumplan con una cierta condición. En este caso, vamos a cambiar todas las instancias de 'setosa' en la columna 'species' por 'SETOSA':

```python
df.loc[df['species'] == 'setosa', 'species'] = 'SETOSA'
```

## Ejemplo Práctico

Para ilustrar algunas de estas operaciones, vamos a agregar una columna a nuestro DataFrame que indique si la longitud del sépalo de cada flor es superior a la media de todas las longitudes del sépalo:

```python
df['sepal_length_above_average'] = df['sepal_length'] > df['sepal_length'].mean()
```

Esto es solo una breve introducción a cómo trabajar con DataFrames en pandas. Recuerda que esta biblioteca es extremadamente poderosa y versátil, y ofrece muchas más funcionalidades que las que hemos cubierto aquí. Te animo a que sigas explorando y practicando para convertirte en un experto en la manipulación de datos con pandas. ¡Buena suerte!
