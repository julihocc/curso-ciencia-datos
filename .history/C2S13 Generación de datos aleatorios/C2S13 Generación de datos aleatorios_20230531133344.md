¡Claro! Aquí te dejo algunas notas sobre la generación de datos aleatorios en Python, utilizando la biblioteca NumPy.

```markdown
# Generación de Datos Aleatorios con NumPy

NumPy ofrece varias funciones para generar datos aleatorios, que son muy útiles en simulaciones, pruebas de hipótesis, creación de muestras, etc.

Primero, importemos la biblioteca NumPy.

```python
import numpy as np
```

## Números Aleatorios Uniformes

Podemos generar números aleatorios con una distribución uniforme utilizando la función `random()`.

```python
# Genera un solo número aleatorio
print(np.random.random())

# Genera una lista de 5 números aleatorios
print(np.random.random(5))

# Genera una matriz 2x2 de números aleatorios
print(np.random.random((2, 2)))
```

## Números Aleatorios Enteros

La función `randint()` genera números aleatorios enteros dentro de un rango específico.

```python
# Genera un número aleatorio entre 0 y 10
print(np.random.randint(10))

# Genera cinco números aleatorios entre 10 y 20
print(np.random.randint(10, 20, 5))
```

## Números Aleatorios Normales

La función `randn()` genera números aleatorios que siguen una distribución normal estándar.

```python
# Genera un solo número aleatorio
print(np.random.randn())

# Genera una lista de 5 números aleatorios
print(np.random.randn(5))

# Genera una matriz 2x2 de números aleatorios
print(np.random.randn(2, 2))
```

## Elección Aleatoria

La función `choice()` permite seleccionar aleatoriamente un elemento de una lista.

```python
# Crea una lista de opciones
options = ['red', 'blue', 'green']

# Selecciona aleatoriamente un elemento de la lista
print(np.random.choice(options))
```

## Barajando Listas

La función `shuffle()` permite desordenar aleatoriamente los elementos de una lista.

```python
# Crea una lista
list = [1, 2, 3, 4, 5]

# Desordena la lista
np.random.shuffle(list)

print(list)
```

## Semilla Aleatoria

La función `seed()` permite establecer la semilla del generador de números aleatorios para reproducir resultados.

```python
np.random.seed(0)

# Genera una lista de 5 números aleatorios
print(np.random.random(5))
```

Repetir la celda anterior producirá los mismos números aleatorios cada vez debido a la semilla fijada.

Estos son solo algunos ejemplos de cómo generar datos aleatorios con NumPy. Consulta la documentación de NumPy para más detalles y opciones.
```

Espero que estas notas sean de utilidad para tu clase. ¡Buena suerte enseñando!
