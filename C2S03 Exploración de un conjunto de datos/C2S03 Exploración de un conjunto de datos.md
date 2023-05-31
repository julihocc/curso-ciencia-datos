
# Exploración de conjuntos de datos con Pandas

Pandas es una poderosa biblioteca de Python que se utiliza para la manipulación y el análisis de datos. Vamos a aprender cómo explorar nuestros conjuntos de datos con esta herramienta.

## Instalación de Pandas

```python
pip install pandas
```

## Importando Pandas

Para usar pandas en tu programa, primero necesitas importarlo.

```python
import pandas as pd
```

## Creando un DataFrame

Pandas puede leer muchos tipos de archivos, pero para este ejemplo crearemos un DataFrame a partir de un diccionario.

```python
data = {
    'frutas': ['manzanas', 'naranjas', 'plátanos', 'kiwis'],
    'cantidad': [10, 6, 3, 8]
}
df = pd.DataFrame(data)
```

## Visualización de los datos

Pandas ofrece múltiples formas de explorar y visualizar datos. Veamos algunas de ellas.

### head()

Este método nos muestra las primeras N filas de nuestro DataFrame. Por defecto, N es 5.

```python
df.head()
```

### tail()

Este método nos muestra las últimas N filas de nuestro DataFrame. Por defecto, N es 5.

```python
df.tail()
```

### shape

Esta propiedad nos muestra la cantidad de filas y columnas de nuestro DataFrame.

```python
df.shape
```

### columns

Esta propiedad nos devuelve los nombres de las columnas.

```python
df.columns
```

### dtypes

Este método nos devuelve el tipo de datos de cada columna.

```python
df.dtypes
```

## Selección de Datos

Con pandas, podemos seleccionar ciertos datos para enfocar nuestro análisis.

### Selección de Columnas

```python
df['frutas']
```

### Selección de Filas

Podemos seleccionar filas por índice o por alguna condición.

```python
df[1:3]
df[df['cantidad'] > 5]
```

## Resumen de los Datos

Pandas proporciona métodos que nos dan resúmenes de nuestros datos.

### describe()

Este método proporciona un resumen estadístico del DataFrame.

```python
df.describe()
```

### value_counts()

Este método cuenta la frecuencia de los valores en una columna.

```python
df['frutas'].value_counts()
```

## Manejo de Datos Faltantes

En el mundo real, los conjuntos de datos suelen tener datos faltantes. Pandas nos proporciona métodos para manejar estos casos.

### isnull()

Este método retorna True si el valor es nulo.

```python
df.isnull()
```

### dropna()

Este método elimina las filas con valores nulos.

```python
df.dropna()
```

### fillna()

Este método llena los valores nulos con un valor especificado.

```python
df.fillna(value)
```

¡Eso es todo por ahora! Esta es solo una pequeña parte de lo que pandas puede hacer. ¡Sigan explorando!

