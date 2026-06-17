# 3. Tipos de datos (int, float, str, bool)

Si las variables son cajas, los tipos de datos nos dicen qué hay dentro de la caja.

No es lo mismo guardar:

- Un número.
- Un texto.
- Una respuesta de sí o no.

Python necesita saber qué tipo de información está manejando para poder trabajar correctamente.

## ¿Por qué son importantes?

Mira este ejemplo:

```python
edad = 20
```

Python entiende:

"edad es un número"

Pero si haces:

```python
edad = "20"
```

Python entiende:

"edad es un texto"

Aunque para nosotros se vean iguales.

## 1. int (números enteros)

Son números sin decimales.

**Ejemplos:**

```python
edad = 20
cantidad_estudiantes = 35
temperatura = -5
```

Puedes hacer operaciones matemáticas:

```python
a = 10
b = 5
print(a + b)
```

**Resultado:**
```
15
```

## 2. float (números decimales)

Son números que tienen parte decimal.

**Ejemplos:**

```python
altura = 1.75
precio = 19.99
pi = 3.1416
```

**Operaciones:**

```python
altura = 1.75
crecimiento = 0.05
print(altura + crecimiento)
```

**Resultado:**
```
1.8
```

### Diferencia entre int y float

`10` es un entero.

`10.0` es un decimal.

Verifícalo:

```python
print(type(10))
print(type(10.0))
```

**Salida:**
```
<class 'int'>
<class 'float'>
```

## 3. str (texto)

Todo lo que esté entre comillas es texto.

```python
nombre = "Cristian"
apellido = 'Triana'
```

Python acepta:

- `"texto"` o
- `'texto'`

### Concatenar textos

Concatenar significa unir.

```python
nombre = "Cristian"
apellido = "Triana"
print(nombre + " " + apellido)
```

**Resultado:**
```
Cristian Triana
```

### Repetir texto

```python
print("Hola " * 3)
```

**Resultado:**
```
Hola Hola Hola
```

## 4. bool (booleanos)

Solo tienen dos valores:

- `True`
- `False`

Observa que empiezan con mayúscula.

**Correcto:**
```python
True
False
```

**Incorrecto:**
```python
true
false
```

**Ejemplos:**

```python
es_estudiante = True
esta_lloviendo = False
```

Se usan muchísimo en condiciones:

```python
edad = 20
print(edad >= 18)
```

**Resultado:**
```
True
```

## Cómo saber el tipo de una variable

Usamos:

```python
type()
```

**Ejemplo:**

```python
nombre = "Cristian"
print(type(nombre))
```

**Resultado:**
```
<class 'str'>
```

## Conversiones de tipos

Aquí es donde los principiantes suelen cometer errores.

Python permite convertir datos.

### int()

Convierte a entero.

```python
numero = "25"
numero = int(numero)
print(numero)
```

**Resultado:**
```
25
```

Ahora sí es un número.

**Verificación:**
```python
print(type(numero))
```

**Salida:**
```
<class 'int'>
```

### float()

Convierte a decimal.

```python
precio = "19.99"
precio = float(precio)
print(precio)
```

**Resultado:**
```
19.99
```

### str()

Convierte a texto.

```python
edad = 20
edad = str(edad)
print(type(edad))
```

**Resultado:**
```
<class 'str'>
```

### bool()

Convierte a booleano.

```python
print(bool(1))
```

**Resultado:**
```
True
```

```python
print(bool(0))
```

**Resultado:**
```
False
```

## El error más común con input()

Mira esto:

```python
edad = input("Escribe tu edad: ")
print(edad)
```

Si escribes:

```
20
```

Python guarda:

```
"20"
```

NO guarda:

```
20
```

Por eso ocurre este error:

```python
edad = input("Edad: ")
print(edad + 5)
```

**Error.**

Porque Python intenta hacer:

```
"20" + 5
```

y no sabe sumar texto con número.

**La solución:**

```python
edad = int(input("Edad: "))
print(edad + 5)
```

Ahora sí:

```
20 + 5
```

**Resultado:**
```
25
```

## Truco profesional

En vez de:

```python
edad = input("Edad: ")
edad = int(edad)
```

Se suele escribir:

```python
edad = int(input("Edad: "))
```

Más corto y elegante.

## F-strings (muy importantes)

Muchos principiantes hacen:

```python
nombre = "Cristian"
print("Hola " + nombre)
```

Funciona.

Pero hoy se usa:

```python
nombre = "Cristian"
print(f"Hola {nombre}")
```

Con varias variables:

```python
nombre = "Cristian"
edad = 20
print(f"Me llamo {nombre} y tengo {edad} años.")
```

**Resultado:**
```
Me llamo Cristian y tengo 20 años.
```

## Funciones útiles para strings

### len()

Cuenta caracteres.

```python
nombre = "Cristian"
print(len(nombre))
```

**Resultado:**
```
8
```

### upper()

Mayúsculas.

```python
nombre = "cristian"
print(nombre.upper())
```

**Resultado:**
```
CRISTIAN
```

### lower()

Minúsculas.

```python
nombre = "CRISTIAN"
print(nombre.lower())
```

**Resultado:**
```
cristian
```

### capitalize()

Primera letra en mayúscula.

```python
nombre = "cristian"
print(nombre.capitalize())
```

**Resultado:**
```
Cristian
```

## Error típico de principiantes

Esto:

```python
nombre = Cristian
```

genera error.

Porque Python piensa que Cristian es una variable.

Debe ser:

```python
nombre = "Cristian"
```

## Mini proyecto

Haz un programa que pregunte:

- Nombre
- Edad
- Estatura

Y luego muestre:

```python
nombre = input("Nombre: ")
edad = int(input("Edad: "))
altura = float(input("Altura: "))

print(f"Hola {nombre}")
print(f"Tienes {edad} años")
print(f"Mides {altura} metros")
```

## Lo que debes dominar antes de avanzar

Debes entender perfectamente:

- `int`
- `float`
- `str`
- `bool`

Y saber usar:

- `type()`
- `int()`
- `float()`
- `str()`
- `bool()`
- `len()`

Además de esto:

```python
f"Texto {variable}"
```

porque lo usarás prácticamente todos los días.

## Desafío rápido

Sin ejecutar el código, intenta decir qué mostrará:

```python
edad = "20"
altura = 1.75

print(int(edad) + 5)
print(str(altura))
print(type(edad))
print(type(int(edad)))
print(len("Python"))
```

**Respuestas:**
```
25
1.75
<class 'str'>
<class 'int'>
6
```
