
# Lectura y escritura de archivos CSV con Pandas

Pandas es una biblioteca de Python que facilita la manipulación y el análisis de datos. Entre sus capacidades, permite leer y escribir datos en una variedad de formatos, incluyendo archivos CSV.

## Instalación de Pandas

Para instalar pandas, puedes utilizar pip:

```python
pip install pandas
```

## Importando Pandas

Una vez instalado, debes importar pandas en tu script de Python.

```python
import pandas as pd
```

## Leyendo un archivo CSV

Para leer un archivo CSV, utilizamos la función `read_csv()`.

```python
df = pd.read_csv('test.csv')
```

Puedes visualizar las primeras líneas del DataFrame utilizando `head()`.

```python
df.head()
```

## Escribiendo en un archivo CSV

Si quieres guardar tu DataFrame en un archivo CSV, puedes usar la función `to_csv()`.

```python
df.to_csv('new_test.csv', index=False)
```

El parámetro `index=False` se usa para evitar que pandas escriba los índices del DataFrame en el archivo.

## Caso Práctico

Supongamos que tienes el archivo `test.csv` del dataset del Titanic de Kaggle. Este archivo contiene datos de los pasajeros del Titanic, incluyendo edad, sexo, tarifa pagada, entre otros.

Primero, vamos a cargar el archivo en un DataFrame.

```python
titanic_df = pd.read_csv('test.csv')
```

Podemos revisar los primeros registros con `head()`.

```python
titanic_df.head()
```

Ahora, supongamos que queremos agregar una columna que indica si la tarifa pagada por el pasajero es superior a la media. Podemos hacer esto de la siguiente manera:

```python
titanic_df['Tarifa_Superior_Media'] = titanic_df['Fare'] > titanic_df['Fare'].mean()
```

Finalmente, vamos a guardar este nuevo DataFrame con la columna adicional en un nuevo archivo CSV.

```python
titanic_df.to_csv('titanic_tarifa_superior_media.csv', index=False)
```

¡Y eso es todo! Ahora sabes cómo leer y escribir archivos CSV con pandas. Recuerda que estos son solo los conceptos básicos. Pandas tiene muchas otras funcionalidades útiles para la manipulación y el análisis de datos. ¡Sigue explorando!
```
Espero que estas notas sean útiles para tu clase.