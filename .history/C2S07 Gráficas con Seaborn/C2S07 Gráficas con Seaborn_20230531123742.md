Mis disculpas por el error anterior. Aquí está la versión corregida de las notas donde definimos `df` utilizando el conjunto de datos `iris` preconstruido en seaborn:

```markdown
# Creación de gráficos con Seaborn

Seaborn es una biblioteca de visualización de datos en Python basada en matplotlib. Proporciona una interfaz de alto nivel para dibujar gráficos estadísticos atractivos e informativos.

## Instalación de Seaborn

Para instalar seaborn, puedes utilizar pip:

```python
pip install seaborn
```

## Importando Seaborn

Una vez instalado, debes importar seaborn en tu script de Python.

```python
import seaborn as sns
```

## Definición de un DataFrame con Seaborn

Antes de poder crear gráficos con Seaborn, necesitamos un conjunto de datos para visualizar. En este caso, vamos a utilizar el conjunto de datos 'iris' incorporado en Seaborn, que es un DataFrame que contiene medidas para varias flores de iris.

```python
df = sns.load_dataset('iris')
```

## Gráficos de dispersión

El gráfico de dispersión es un diagrama en el que se representan los valores de dos variables.

```python
sns.scatterplot(data=df, x='sepal_length', y='sepal_width', hue='species')
```

## Histogramas

Un histograma es una representación gráfica de una variable en forma de barras, donde la superficie de cada barra es proporcional a la frecuencia de los valores representados.

```python
sns.histplot(data=df, x='sepal_length', kde=True)
```

## Gráficos de caja (Box plots)

Un gráfico de caja es un método para representar gráficamente grupos de datos numéricos a través de sus cuartiles.

```python
sns.boxplot(data=df, x='species', y='sepal_length')
```

## Gráficos de violín (Violin plots)

Los gráficos de violín combinan un gráfico de caja con un gráfico de densidad de kernel.

```python
sns.violinplot(data=df, x='species', y='sepal_length')
```

## Gráficos de correlación (Pair plots)

Los gráficos de correlación muestran las relaciones de par a par en un conjunto de datos.

```python
sns.pairplot(df, hue='species')
```

¡Y eso es todo! Ahora sabes cómo crear gráficos con seaborn. La visualización de datos es una habilidad muy valiosa en ciencia de datos, por lo que te recomendamos seguir explorando las capacidades de seaborn y otras bibliotecas de visualización en Python.
```
Espero que estas notas sean útiles para tu clase.