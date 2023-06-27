# Métodos de Agrupación en Pandas con ejemplos

En Pandas, una biblioteca de manipulación de datos en Python, la agrupación de datos es un método comúnmente utilizado que nos permite dividir los datos en grupos específicos, aplicar funciones y combinar los resultados de manera efectiva. Esta técnica permite llevar a cabo análisis de datos en profundidad y proporciona resultados útiles de conjuntos de datos grandes.

## Importación de la biblioteca pandas

Para empezar a trabajar con los datos, es esencial importar la biblioteca pandas. En Python, las bibliotecas se importan usando la declaración `import`. Usamos la convención `pd` para abreviar pandas por simplicidad y eficiencia.

```python
import pandas as pd
```

## Carga de Datos

Para ilustrar la agrupación de datos, vamos a cargar un conjunto de datos de ejemplo. Usaremos 'train.csv', que es el conjunto de datos proporcionado en el famoso concurso Titanic de Kaggle. Pandas nos proporciona el método `read_csv` para cargar archivos CSV.

```python
df = pd.read_csv('train.csv')
```

## Uso del Método GroupBy

Para realizar agrupaciones, pandas proporciona el método `groupby`. Este método es útil para dividir los datos en grupos específicos basados en ciertos criterios, en este caso, dividimos los datos basados en el sexo.

```python
grouped = df.groupby('Sex')
```

Una vez que hemos dividido los datos, podemos aplicar funciones de agregación a estos grupos para extraer información útil.

## Aplicando Operaciones de Agregación

Pandas nos proporciona una variedad de funciones de agregación que podemos aplicar a nuestros grupos de datos. Vamos a explorar algunas de las más comunes:

### Suma

La función `sum` devuelve la suma total de los valores numéricos en cada grupo.

```python
grouped.sum()
```

### Media

La función `mean` nos da la media de los valores numéricos en cada grupo.

```python
grouped.mean()
```

### Mínimo

La función `min` nos permite identificar el valor mínimo en cada grupo.

```python
grouped.min()
```

### Máximo

De manera similar, la función `max` proporciona el valor máximo en cada grupo.

```python
grouped.max()
```

### Cantidad

La función `count` proporciona el número total de entradas en cada grupo.

```python
grouped.count()
```

## Agrupación por Múltiples Columnas

Pandas también nos permite agrupar datos por múltiples columnas. En este caso, podemos agrupar los datos tanto por 'Sex' como por 'Pclass'.

```python
grouped = df.groupby(['Sex', 'Pclass'])
```

## Uso de Agregaciones Personalizadas

Una de las ventajas de Pandas es que podemos aplicar funciones de agregación personalizadas a nuestros grupos. Esto se puede hacer usando el método `agg`.

Por ejemplo, podríamos querer encontrar la edad mínima, máxima y media de cada grupo, así como la suma total de los que sobrevivieron.

```python
grouped.agg({'Age': ['min', 'max', 'mean'], 'Survived': 'sum'})
```

## Método de Transformación

El método `transform` es útil cuando queremos agregar datos transformados de vuelta al DataFrame original. Este método devuelve un objeto

 que tiene el mismo índice que el original. Por ejemplo, podríamos querer agregar una columna 'Age_zscore' que contenga los valores z-score de la 'Age' para cada grupo.

```python
df['Age_zscore'] = grouped.transform(lambda x: (x - x.mean()) / x.std())['Age']
```

## Método Apply

El método `apply` es especialmente útil cuando queremos aplicar una función más compleja o específica a nuestros grupos. Por ejemplo, podríamos querer identificar los tres pasajeros con el mayor número de sobrevivientes para cada grupo.

```python
def top_survived(df):
    return df.sort_values(by='Survived', ascending=False).head(3)

grouped.apply(top_survived)
```

Con estos métodos y técnicas, tienes una sólida base para comenzar a explorar y analizar tus propios conjuntos de datos. ¡Feliz análisis de datos!
