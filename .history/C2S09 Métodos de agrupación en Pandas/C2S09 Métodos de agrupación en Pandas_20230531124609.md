
# Métodos de Agrupación en Pandas

En pandas, la agrupación de datos se refiere a una operación que involucra una combinación de dividir los datos en grupos, aplicar una función (como suma, media, etc.) y combinar los resultados.

## Importando Pandas

Primero, necesitamos importar la biblioteca pandas.

```python
import pandas as pd
```

## Cargando los Datos

Para los propósitos de esta lección, vamos a utilizar el conjunto de datos 'train.csv' del concurso Titanic de Kaggle.

```python
df = pd.read_csv('train.csv')
```

## El Método GroupBy

El método `groupby` es la función principal para agrupar en pandas. Este método divide los datos en grupos según algún criterio, aplica una función a cada grupo y luego combina los resultados.

```python
grouped = df.groupby('Sex')
```

## Operaciones de Agregación

Una vez que hemos dividido los datos en grupos, podemos aplicar funciones de agregación a estos grupos para obtener información resumida. Algunas de las funciones de agregación más comunes son `sum`, `mean`, `min`, `max` y `count`.

### Suma

```python
grouped.sum()
```

### Media

```python
grouped.mean()
```

### Mínimo

```python
grouped.min()
```

### Máximo

```python
grouped.max()
```

### Cantidad

```python
grouped.count()
```

## Agrupación por Múltiples Columnas

También podemos agrupar por más de una columna. Simplemente pasamos una lista de nombres de columnas al método `groupby`.

```python
grouped = df.groupby(['Sex', 'Pclass'])
```

## Agregaciones Personalizadas

Pandas también nos permite aplicar funciones de agregación personalizadas a nuestros grupos. Podemos hacer esto usando el método `agg`.

```python
grouped.agg({'Age': ['min', 'max', 'mean'], 'Survived': 'sum'})
```

## Método de Transformación

La transformación devuelve un objeto que es indexado de la misma manera que el original. Esto es útil cuando queremos agregar datos transformados al DataFrame original.

```python
df['Age_zscore'] = grouped.transform(lambda x: (x - x.mean()) / x.std())['Age']
```

## Método Apply

El método `apply` nos permite aplicar una función arbitraria a los grupos.

```python
def top_survived(df):
    return df.sort_values(by='Survived', ascending=False).head(3)

grouped.apply(top_survived)
```

¡Y eso es todo! Ahora tienes una buena idea de cómo usar los métodos de agrupación en pandas. ¡Feliz análisis de datos!
