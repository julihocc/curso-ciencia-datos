# Optimización del proceso de análisis de datos mediante la limpieza de datos con Pandas y NumPy

La limpieza de datos es una etapa crucial y a menudo subestimada en el proceso de análisis de datos. Los datos sucios o incorrectos pueden llevar a conclusiones erróneas y decisiones de negocio mal informadas. Pandas y NumPy son dos bibliotecas de Python extremadamente potentes que nos permiten manejar, limpiar y transformar datos de manera eficiente.

## Instalación de las bibliotecas Pandas y NumPy

El primer paso para trabajar con Pandas y NumPy es instalar estas bibliotecas. Para hacerlo, puedes utilizar pip, que es el sistema de gestión de paquetes utilizado por Python. Aquí tienes el comando que necesitarás para instalar ambas bibliotecas:

```python
pip install pandas numpy
```

## Importación de Pandas y NumPy a tu entorno de trabajo

Una vez instaladas, debes importar las bibliotecas Pandas y NumPy en tu script de Python. Por convención, importamos Pandas como `pd` y NumPy como `np`.

```python
import pandas as pd
import numpy as np
```

## Carga de los datos

Para demostrar el proceso de limpieza de datos, necesitaremos un conjunto de datos para trabajar. Vamos a utilizar el conjunto de datos 'train.csv' del concurso Titanic de Kaggle.

```python
df = pd.read_csv('train.csv')
```

Este comando cargará los datos del archivo 'train.csv' en un DataFrame de Pandas, que es una estructura de datos bidimensional etiquetada con filas y columnas.

## Inspección inicial de los datos

Una vez que los datos están cargados en el DataFrame, es útil echar un vistazo a los primeros registros para obtener una idea general de los datos con los que estamos trabajando.

```python
df.head()
```

También es útil obtener un resumen estadístico de los datos. Podemos utilizar el método `describe()` para obtener información como el conteo, la media, la desviación estándar, los valores mínimo y máximo, y los cuartiles de las columnas numéricas.

```python
df.describe()
```

## Manejo de los valores perdidos

Uno de los problemas más comunes que encontrarás al trabajar con conjuntos de datos del mundo real es la presencia de valores perdidos. Podemos utilizar el método `isnull()` combinado con `sum()` para obtener una lista de las columnas y la cantidad de valores perdidos que tienen.

```python
df.isnull().sum()
```

Una vez que sabemos dónde están nuestros valores perdidos, podemos decidir cómo manejarlos. Existen varias estrategias para esto, y la elección depende de la naturaleza de tus datos y de tu objetivo de análisis.

### Eliminar registros con valores perdidos

Una opción es simplemente eliminar cualquier fila que contenga al menos un valor perdido. Esto se puede hacer con el método `dropna()`.

```python
df = df.dropna()
```

### Llenar valores perdidos con un valor determinado

Otra opción es rellenar los valores perdidos con algún valor. Una estrategia común es rellenar con la mediana de la columna, que es menos sensible a los outliers que la media.

```python
df = df.fillna(df.median())
```

## Conversión de tipos de datos

Otro paso común en la

 limpieza de datos es la conversión de tipos de datos. Por ejemplo, puede que quieras convertir la columna 'Survived', que actualmente es una variable numérica, en una variable booleana. Para hacerlo, puedes usar el método `astype()`.

```python
df['Survived'] = df['Survived'].astype(bool)
```

## Eliminación de columnas innecesarias

Es posible que tu conjunto de datos contenga columnas que no son necesarias para tu análisis. En tal caso, puedes optar por eliminar estas columnas. Por ejemplo, podríamos querer eliminar la columna 'Cabin' si decidimos que no es relevante para nuestro análisis.

```python
df = df.drop(columns=['Cabin'])
```

## Detección y manejo de outliers

Los outliers son valores que son significativamente diferentes de los demás. Estos pueden sesgar o distorsionar los resultados y pueden ser debido a variabilidad en los datos o errores de entrada. Un método común para detectar outliers es el método del rango intercuartílico (IQR).

```python
Q1 = df.quantile(0.25)
Q3 = df.quantile(0.75)
IQR = Q3 - Q1
outliers = (df < (Q1 - 1.5 * IQR)) | (df > (Q3 + 1.5 * IQR))
```

Una vez que hemos detectado los outliers, podríamos querer eliminarlos de nuestro conjunto de datos.

```python
df = df[~outliers.any(axis=1)]
```

¡Felicidades! Ahora tienes un sólido punto de partida para limpiar tus propios conjuntos de datos con pandas y NumPy. Recuerda que los pasos exactos y las técnicas utilizadas en la limpieza de datos pueden variar dependiendo de la naturaleza de tus datos y de tu objetivo de análisis. No dudes en explorar más técnicas de limpieza de datos para expandir tu conjunto de herramientas.
