Por supuesto, aquí están las notas para una clase sobre DataFrames en pandas. Para el caso práctico, usaré el conjunto de datos `iris` preconstruido en seaborn, que es una biblioteca para visualización de datos en Python que se basa en matplotlib.

```markdown
# Trabajando con DataFrames en Pandas

Los DataFrames son una estructura de datos bidimensional en Pandas que pueden ser modificados de tamaño y que potencialmente almacenan datos de diferentes tipos.

## Instalación de Pandas y Seaborn

Para instalar pandas y seaborn, puedes utilizar pip:

```python
pip install pandas seaborn
```

## Importando Pandas y Seaborn

Una vez instalado, debes importar pandas y seaborn en tu script de Python.

```python
import pandas as pd
import seaborn as sns
```

## Cargando un DataFrame preconstruido

Vamos a cargar el conjunto de datos 'iris' utilizando seaborn.

```python
df = sns.load_dataset('iris')
```

Puedes visualizar las primeras líneas del DataFrame utilizando `head()`.

```python
df.head()
```

## Inspección de DataFrames

Existen varias formas de inspeccionar tu DataFrame.

### shape

Esta propiedad te permite ver la cantidad de filas y columnas.

```python
df.shape
```

### columns

Esta propiedad te da los nombres de las columnas.

```python
df.columns
```

### dtypes

Esta propiedad te permite ver el tipo de datos en cada columna.

```python
df.dtypes
```

### describe()

Este método te proporciona un resumen estadístico del DataFrame.

```python
df.describe()
```

## Selección de Datos

Puedes seleccionar datos en el DataFrame de diversas formas.

### Selección de Columnas

```python
df['species']
```

### Selección de Filas

```python
df[10:20]
df[df['sepal_length'] > 5.0]
```

## Modificación de DataFrames

Puedes modificar DataFrames añadiendo columnas o modificando valores existentes.

```python
df['double_sepal_length'] = df['sepal_length'] * 2
df.loc[df['species'] == 'setosa', 'species'] = 'SETOSA'
```

## Caso Práctico

Supongamos que queremos agregar una columna que indique si la longitud del sépalo es superior a la media. Podemos hacerlo de la siguiente manera:

```python
df['sepal_length_above_average'] = df['sepal_length'] > df['sepal_length'].mean()
```

¡Y eso es todo! Ahora sabes cómo trabajar con DataFrames en pandas. Recuerda que estos son solo los conceptos básicos. Pandas tiene muchas otras funcionalidades útiles para la manipulación y el análisis de datos. ¡Sigue explorando!
```

Espero que estas notas sean útiles para tu clase.
