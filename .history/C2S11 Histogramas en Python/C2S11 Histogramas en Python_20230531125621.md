
# Creación de Histogramas en Python

Un histograma es una representación gráfica que organiza un grupo de datos en una serie de intervalos (también llamados "bins").

## Usando Matplotlib

Matplotlib es una biblioteca de trazado en 2D en Python que produce figuras de calidad en una variedad de formatos impresos y entornos interactivos.

```python
import matplotlib.pyplot as plt

data = [1, 1.1, 1.3, 2.2, 2.9, 3.0, 3.2, 3.3, 3.5, 4.0, 4.2, 4.2, 4.5]

plt.hist(data, bins=10, edgecolor='black')
plt.title('Histograma con Matplotlib')
plt.xlabel('Valores')
plt.ylabel('Frecuencia')
plt.show()
```

## Usando Seaborn

Seaborn es una biblioteca de visualización de datos en Python basada en Matplotlib. Proporciona una interfaz de alto nivel para dibujar gráficos estadísticos atractivos e informativos.

```python
import seaborn as sns

sns.histplot(data, bins=10, kde=False)
plt.title('Histograma con Seaborn')
plt.xlabel('Valores')
plt.ylabel('Frecuencia')
plt.show()
```

## Usando Pandas

Pandas también proporciona una manera fácil de trazar un histograma a partir de un DataFrame o una Serie.

```python
import pandas as pd

data = pd.Series(data)
data.plot(kind='hist', bins=10, edgecolor='black', rwidth=0.8)
plt.title('Histograma con Pandas')
plt.xlabel('Valores')
plt.ylabel('Frecuencia')
plt.show()
```

## Usando Numpy y Matplotlib

Numpy tiene una función `histogram` que crea los datos del histograma, pero no los traza. Para trazar los datos, se puede utilizar la función `bar` de Matplotlib.

```python
import numpy as np

hist, bins = np.histogram(data, bins=10)
plt.bar(bins[:-1], hist, width = 0.1, color='#0504aa',alpha=0.7)
plt.title('Histograma con Numpy y Matplotlib')
plt.xlabel('Valores')
plt.ylabel('Frecuencia')
plt.show()
```

## Usando Bokeh

Bokeh es una biblioteca de visualización de Python que permite la creación de gráficos interactivos que se pueden visualizar en los navegadores.

```python
from bokeh.plotting import figure, show
from bokeh.io import output_notebook
from bokeh.models import ColumnDataSource
from bokeh.transform import factor_cmap
from bokeh.palettes import Spectral6
from bokeh.models import HoverTool
from bokeh.layouts import row
from math import pi
from bokeh.models import FuncTickFormatter

output_notebook()

source = ColumnDataSource(data=dict(height=data, weight=data))

p = figure(height = 600, width = 600, 
           title = 'Histograma con Bokeh',
          x_axis_label = 'Valores', 
          y_axis_label = 'Frecuencia')

p.vbar(x='weight', top='height', width=0.9, source=source, line_color='white', 
       fill_color=factor_cmap('weight', palette=Spectral6, factors

=data))

hover = HoverTool()
hover.tooltips = [("Valores", "@weight"), ("Frecuencia", "@height")]
hover.mode = 'vline'

p.add_tools(hover)

show(p)
```

Por favor, ten en cuenta que estos ejemplos son bastante básicos. Cada una de estas bibliotecas ofrece mucha más flexibilidad y opciones de personalización para crear histogramas.
