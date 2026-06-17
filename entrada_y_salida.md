# Entrada y salida de datos (input() y print())

## 📑 Tabla de Contenidos
- [Introducción](#-introducción)
- [Salida de datos: print()](#salida-de-datos-print)
  - [Mostrar varias cosas](#mostrar-varias-cosas)
  - [La forma profesional: f-strings](#la-forma-profesional-f-strings)
  - [Operaciones dentro de f-strings](#operaciones-dentro-de-f-strings)
- [Entrada de datos: input()](#entrada-de-datos-input)
  - [¿Qué devuelve input() siempre?](#qué-devuelve-input-siempre)
  - [Error clásico y solución](#error-clásico-y-solución)
  - [Datos decimales](#datos-decimales)
  - [Regla para memorizar](#regla-para-memorizar)
- [Ejemplo práctico](#ejemplo-práctico)
- [Formato visual de salida y secuencias de escape](#formato-visual-de-salida-y-secuencias-de-escape)
  - [Secuencias útiles](#secuencias-útiles)
- [Buenas prácticas con input()](#buenas-prácticas-con-input)
- [Ejemplo realista](#ejemplo-realista)
- [Mini proyectos](#mini-proyectos)
- [Estilo profesional](#estilo-profesional)
- [Lo que debes dominar de esta lección](#lo-que-debes-dominar-de-esta-lección)
- [Ejercicio para pensar](#ejercicio-para-pensar)

---

Hasta ahora hemos hecho esto:

```python
nombre = "Cristian"
print(nombre)
```

El problema es que el valor ya está escrito en el código. Si otra persona ejecuta el programa, seguirá apareciendo:

```
Cristian
```

No importa quién lo use. Lo interesante es que el usuario pueda ingresar sus propios datos.

---

## Salida de datos: print()

La función `print()` sirve para mostrar información en pantalla.

Ejemplo:

```python
print("Hola mundo")
```

Resultado:

```
Hola mundo
```

También puede mostrar números:

```python
print(20)
```

Resultado:

```
20
```

Y variables:

```python
nombre = "Cristian"
print(nombre)
```

Resultado:

```
Cristian
```

### Mostrar varias cosas

```python
nombre = "Cristian"
edad = 20
print(nombre, edad)
```

Resultado:

```
Cristian 20
```

Observa que Python agrega un espacio automáticamente.

### El problema de este enfoque

```python
nombre = "Cristian"
edad = 20
print("Mi nombre es", nombre, "y tengo", edad, "años")
```

Funciona. Pero cuando el programa crece se vuelve difícil de leer.

### La forma profesional: f-strings

La vas a usar constantemente.

```python
nombre = "Cristian"
edad = 20
print(f"Mi nombre es {nombre} y tengo {edad} años")
```

Resultado:

```
Mi nombre es Cristian y tengo 20 años
```

¿Qué significa la `f`? La letra `f` significa: "Python, dentro de las llaves habrá variables o expresiones."

```python
nombre = "Cristian"
print(f"Hola {nombre}")
```

Python reemplaza automáticamente `{nombre}` por el valor almacenado.

#### También puedes hacer operaciones

```python
a = 10
b = 5
print(f"La suma es {a + b}")
```

Resultado:

```
La suma es 15
```

---

## Entrada de datos: input()

Ahora viene la parte interesante. `input()` permite que el usuario escriba información.

```python
nombre = input("¿Cuál es tu nombre? ")
```

Si el usuario escribe `Cristian`, Python guarda:

```python
nombre = "Cristian"
```

Luego podemos usarlo:

```python
nombre = input("¿Cuál es tu nombre? ")
print(f"Hola {nombre}")
```

Si escribe `Cristian` el resultado será:

```
Hola Cristian
```

### ¿Qué devuelve siempre input()?

Esto es MUY importante. Siempre devuelve un `str` (string). Siempre.

Ejemplo:

```python
edad = input("Edad: ")
print(type(edad))
```

Si escribes `20`, Python muestra:

```
<class 'str'>
```

No es un número. Es texto.

### Error clásico de principiantes

```python
edad = input("Edad: ")
print(edad + 5)
```

Si escribes `20`, Python intenta hacer `"20" + 5` y aparece un error.

### La solución: convertir el dato

```python
edad = int(input("Edad: "))
print(edad + 5)
```

Ahora sí, si escribes `20` el resultado será:

```
25
```

### Datos decimales

Si esperas un decimal:

```python
altura = float(input("Altura: "))
```

Si escribes `1.75`, Python guarda `1.75` como número decimal.

### Una regla que debes memorizar

Cuando uses `input()` piensa:

- Texto → `input()`
- Número entero → `int(input())`
- Número decimal → `float(input())`

---

## Ejemplo práctico

Supongamos que quieres calcular la edad dentro de 10 años.

```python
edad = int(input("¿Qué edad tienes? "))
print(f"En 10 años tendrás {edad + 10} años")
```

---

## Formato visual de salida

Puedes imprimir líneas vacías:

```python
print("Hola")
print()
print("Mundo")
```

Resultado:

```
Hola

Mundo
```

También puedes usar `\n`:

```python
print("Hola\nMundo")
```

Resultado:

```
Hola
Mundo
```

### Secuencias de escape útiles

- Salto de línea: `\n`

Ejemplo:

```python
print("Python\nIA")
```

Resultado:

```
Python
IA
```

- Tabulación: `\t`

Ejemplo:

```python
print("Nombre\tEdad")
```

Resultado aproximado:

```
Nombre	Edad
```

---

## Buenas prácticas con input()

Mal:

```python
a = int(input("Ingrese valor: "))
```

Bien:

```python
edad = int(input("Ingrese su edad: "))
```

La variable debe describir qué contiene.

---

## Ejemplo realista

```python
nombre = input("Nombre: ")
edad = int(input("Edad: "))
carrera = input("Carrera: ")

print()
print("Información registrada")
print("-----------------------")
print(f"Nombre: {nombre}")
print(f"Edad: {edad}")
print(f"Carrera: {carrera}")
```

Salida posible:

```
Información registrada
-----------------------
Nombre: Cristian
Edad: 20
Carrera: Ingeniería
```

---

## Mini proyecto 1: Calculadora de suma

```python
numero1 = float(input("Primer número: "))
numero2 = float(input("Segundo número: "))
resultado = numero1 + numero2
print(f"La suma es {resultado}")
```

## Mini proyecto 2: Calculadora de IMC

Fórmula:

```
IMC = peso / altura²
```

Código:

```python
peso = float(input("Peso en kg: "))
altura = float(input("Altura en metros: "))
imc = peso / (altura ** 2)
print(f"Tu IMC es {imc}")
```

---

## Estilo profesional

En programas grandes suele verse así:

```python
nombre = input("Nombre: ").strip()
```

Aún no necesitas usar `.strip()`, pero debes saber que elimina espacios al inicio y al final.

Ejemplo: si alguien escribe `   Cristian`, Python lo convierte en `Cristian`.

---

## Lo que debes dominar de esta lección

- Funciones: `print()`, `input()`
- Conversiones: `int(input())`, `float(input())`
- Formato moderno: `f"{variable}"`
- Secuencias útiles: `\n`, `\t`

---

## Ejercicio para pensar

Sin ejecutar el código, ¿qué mostrará?

```python
nombre = input("Nombre: ")
edad = int(input("Edad: "))
print(f"Hola {nombre}")
print(f"El próximo año tendrás {edad + 1} años")
```

Si el usuario escribe:

```
Cristian
20
```

¿Cuál será exactamente la salida?
