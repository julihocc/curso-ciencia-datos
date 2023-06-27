# Lectura y escritura de archivos CSV con Pandas

Pandas es una biblioteca de Python especialmente diseñada para el análisis de datos. Proporciona estructuras de datos y funciones potentes, y fáciles de usar, para manipular y analizar datos estructurados. Uno de los aspectos más útiles de Pandas es su capacidad para leer y escribir datos en una variedad de formatos de archivos, incluyendo archivos CSV (Comma Separated Values).

## Instalando Pandas

La instalación de pandas es sencilla gracias a pip, el gestor de paquetes de Python. Ejecuta el siguiente comando en tu terminal para instalar pandas:

```python
pip install pandas
```

Este comando instala pandas y sus dependencias, preparando tu entorno de Python para trabajar con esta útil biblioteca.

## Importando Pandas en tu script

Después de la instalación, necesitas importar pandas en tu script de Python para poder utilizar sus características. La convención común es importar pandas con el alias 'pd', lo que facilita el acceso a sus métodos y reduce la cantidad de código que tienes que escribir.

```python
import pandas as pd
```

## Leyendo archivos CSV con Pandas

La lectura de archivos CSV es un caso común en el análisis de datos. Pandas proporciona la función `read_csv()` para cargar datos desde archivos CSV en un DataFrame, que es la estructura de datos principal en Pandas y es muy similar a una tabla en una base de datos relacional.

```python
df = pd.read_csv('test.csv')
```

En este ejemplo, 'test.csv' es el nombre del archivo que queremos cargar. La función `read_csv()` devuelve un DataFrame que se asigna a la variable df.

Una vez que tienes tus datos en un DataFrame, puedes usar el método `head()` para obtener una vista rápida de las primeras filas de tus datos.

```python
df.head()
```

## Escribiendo DataFrames en archivos CSV

No sólo puedes leer archivos CSV con Pandas, sino que también puedes escribir DataFrames en archivos CSV. Para hacer esto, puedes usar el método `to_csv()` de un DataFrame.

```python
df.to_csv('new_test.csv', index=False)
```

En este caso, 'new_test.csv' es el nombre del nuevo archivo CSV que queremos crear. El parámetro `index=False` se utiliza para evitar que pandas escriba los índices del DataFrame en el archivo, lo que podría ser innecesario si los índices son sólo números secuenciales predeterminados.

## Aplicación Práctica

Para ilustrar cómo utilizar estas características de Pandas en un contexto práctico, supongamos que tienes el archivo `test.csv` que es parte del dataset del Titanic de Kaggle. Este archivo contiene datos de los pasajeros del Titanic, como la edad, el sexo, la tarifa pagada, entre otros.

Primero, podemos cargar estos datos en un DataFrame de Pandas utilizando `read_csv()`:

```python
titanic_df = pd.read_csv('test.csv')
```

Después de cargar los datos, puedes usar `head()` para obtener una vista rápida de los datos.

```python
titanic_df.head()
```

Imagina que quieres agregar una nueva columna al DataFrame que indique si la tarifa pagada por cada pasajero es superior a la media de todas las tarifas. Puedes hacer esto fácilmente con Pandas:

```python
titanic_df['Tarifa_Superior_Media'] = titanic_df['Fare'] > titanic_df['Fare'].mean()
```

Finalmente, puedes guardar el DataFrame con la nueva columna en un nuevo archivo CSV utilizando el método `to_csv()`.

```python
titanic_df.to_csv('titanic_tarifa_superior_media.csv', index=False)
```

¡Y eso es todo! Con estos conceptos y prácticas básicas, ya estás bien equipado para manejar archivos CSV con pandas. Sin embargo, recuerda que pandas tiene muchas más funcionalidades y capacidades útiles para el análisis y la manipulación de datos. ¡Continúa explorando y aprendiendo!
