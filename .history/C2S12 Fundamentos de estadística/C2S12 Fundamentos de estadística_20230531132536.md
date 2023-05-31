
# Fundamentos de Estadística con NumPy

NumPy es una biblioteca de Python que se utiliza ampliamente en el ámbito de la ciencia de datos y proporciona una serie de funciones estadísticas.

## Importando NumPy

Para usar NumPy, primero necesitamos importarlo.

```python
import numpy as np
```

## Datos

Vamos a utilizar una matriz aleatoria para ilustrar las funciones estadísticas de NumPy.

```python
data = np.random.randn(1000)
```

## Medidas de Centralización

### Media

La media es el valor promedio de los datos. NumPy proporciona la función `mean()` para calcularla.

```python
np.mean(data)
```

### Mediana

La mediana es el valor que divide los datos en dos mitades iguales. NumPy proporciona la función `median()` para calcularla.

```python
np.median(data)
```

## Medidas de Dispersión

### Desviación Estándar

La desviación estándar mide la cantidad de variación o dispersión de un conjunto de valores. Una baja desviación estándar indica que los valores tienden a estar cerca de la media. NumPy proporciona la función `std()` para calcularla.

```python
np.std(data)
```

### Varianza

La varianza es una medida de la dispersión que muestra cuánto se alejan los valores del conjunto del valor medio. NumPy proporciona la función `var()` para calcularla.

```python
np.var(data)
```

## Medidas de Posición

### Mínimo y Máximo

Las funciones `min()` y `max()` nos permiten encontrar el valor mínimo y máximo de los datos, respectivamente.

```python
np.min(data)
np.max(data)
```

### Cuartiles

Los cuartiles son valores que dividen tus datos en cuartos. NumPy proporciona la función `quantile()` para calcularlos.

```python
np.quantile(data, [0.25, 0.5, 0.75])
```

## Correlación

La correlación mide la relación entre dos variables. La función `corrcoef()` devuelve la matriz de correlación de Pearson.

```python
data2 = np.random.randn(1000)
np.corrcoef(data, data2)
```

Estos son sólo algunos de los conceptos fundamentales de la estadística que puedes calcular utilizando NumPy. Para un análisis más detallado, puedes usar bibliotecas como SciPy o StatsModels.
```

Espero que estas notas te sean útiles para tu clase. ¡Feliz enseñanza!
