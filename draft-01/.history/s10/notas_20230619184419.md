# Notas de clase: Estimadores Puntuales

## Estimadores Puntuales

Un estimador puntual es una estadística (una función de los datos) que se utiliza para inferir el valor de un parámetro desconocido de una población. En términos más formales, un estimador puntual es una función de las variables aleatorias que conforman una muestra y que produce un único valor que se utiliza como una "mejor suposición" del valor del parámetro desconocido. 

Los estimadores puntuales más comunes son la media, la mediana, la varianza y la desviación estándar.

### Media (Promedio)

Es la suma de todos los valores de los datos, dividida por el número total de valores. Se representa como μ para la población y x̄ para la muestra.

En Python, utilizando NumPy, podemos calcular la media de un conjunto de datos de la siguiente manera:

```python
import numpy as np

data = np.array([1, 2, 3, 4, 5])
mean = np.mean(data)
print(mean)
```

### Mediana

Es el valor que separa la mitad superior de un conjunto de datos de la mitad inferior. Si el número de observaciones es par, la mediana es el promedio de los dos valores centrales.

En Python, utilizando NumPy:

```python
import numpy as np

data = np.array([1, 2, 3, 4, 5])
median = np.median(data)
print(median)
```

### Varianza

Es la media de los cuadrados de las desviaciones de cada valor respecto a la media. Mide la dispersión de un conjunto de datos. Para la población, se representa como σ² y para la muestra se representa como s².

En Python, utilizando NumPy:

```python
import numpy as np

data = np.array([1, 2, 3, 4, 5])
variance = np.var(data)
print(variance)
```

### Desviación estándar

Es la raíz cuadrada de la varianza y se representa como σ para la población y s para la muestra. La desviación estándar es una medida de dispersión que es muy utilizada porque tiene la misma unidad de medida que los datos.

En Python, utilizando NumPy:

```python
import numpy as np

data = np.array([1, 2, 3, 4, 5])
std_dev = np.std(data)
print(std_dev)
```

Los estimadores puntuales son una parte fundamental de la estadística y del análisis de datos. Nos proporcionan una forma de obtener una única estimación del valor de un parámetro de población desconocido, lo que puede ser muy útil para resumir un conjunto de datos o para hacer inferencias sobre una población a partir de una muestra.