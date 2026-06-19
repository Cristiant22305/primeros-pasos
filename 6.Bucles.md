# BUCLES (FOR Y WHILE)

## 📑 Tabla de Contenidos
- [Introducción](#-introducción)
- [¿Qué es un bucle?](#-qué-es-un-bucle)
- [Tipos de bucles en Python](#tipos-de-bucles-en-python)
- [WHILE](#while)
  - [Ejemplo y explicación](#ejemplo-y-explicación)
  - [Error más común: bucle infinito](#error-más-común-bucle-infinito)
  - [Operadores de asignación](#operadores-de-asignación)
- [FOR](#for)
  - [¿Qué es range()?](#qué-es-range)
  - [range(inicio, fin) y range con pasos](#rangeinicio-fin-y-range-con-pasos)
  - [Recorrer strings](#recorrer-strings)
  - [Recorrer listas](#recorrer-listas)
- [BREAK](#break)
- [CONTINUE](#continue)
- [PASS](#pass)
- [ENUMERATE() (MUY IMPORTANTE)](#enumerate-muy-importante)
- [ELSE en bucles](#else-en-bucles)
- [Bucles anidados](#bucles-anidados)
- [Tablas de multiplicar (ejemplo)](#tablas-de-multiplicar-ejemplo)
- [Comprensión de listas (introducción)](#comprensión-de-listas-introducción)
- [¿Cuándo usar for y cuándo while?](#cuándo-usar-for-y-cuándo-while)
- [Errores típicos de principiantes](#errores-típicos-de-principiantes)
- [Mini proyecto](#mini-proyecto)

---

## 📌 Introducción

Los bucles son una de las herramientas más importantes de toda la programación. Sirven para repetir tareas automáticamente y evitar repetir código manualmente.

Ejemplo rápido: si quieres imprimir "Hola" 3 veces:

```python
for i in range(3):
    print("Hola")
```

Resultado:

```
Hola
Hola
Hola
```

---

## ❓ ¿Qué es un bucle?

Un bucle es una estructura que ejecuta el mismo bloque de código varias veces.

Pensamiento mental:

Repite:
    saluda

Repite:
    saluda

Repite:
    saluda

---

## TIPOS DE BUCLES EN PYTHON

Los principales son `while` y `for`.

---

## WHILE

`while` significa: mientras una condición sea verdadera, sigue ejecutando.

Sintaxis:

```python
while condicion:
    codigo
```

### Ejemplo y explicación

```python
contador = 1

while contador <= 5:
    print(contador)
    contador += 1
```

Resultado:

```
1
2
3
4
5
```

Cómo funciona: empieza con `contador = 1`, pregunta `contador <= 5`. Si es cierto ejecuta el bloque y actualiza la variable (aquí `contador += 1`). Vuelve a preguntar y repite hasta que la condición sea falsa.

### Error más común: bucle infinito

Si olvidas actualizar la variable, la condición nunca cambia y el bucle nunca termina.

Ejemplo problemático:

```python
contador = 1

while contador <= 5:
    print(contador)
    # falta contador += 1
```

Salida: imprime `1` repetidamente hasta que detengas el programa (bucle infinito).

### Operadores de asignación útiles

En vez de `contador = contador + 1` puedes escribir `contador += 1`. Otros ejemplos:

```python
x -= 1
x *= 2
x /= 2
```

---

## FOR

`for` es el bucle más usado en Python.

Sintaxis:

```python
for variable in secuencia:
    codigo
```

Ejemplo:

```python
for i in range(5):
    print(i)
```

Resultado:

```
0
1
2
3
4
```

### ¿Qué es range()?

`range()` genera una secuencia de números. `range(5)` produce `0 1 2 3 4` — no incluye el último.

### range(inicio, fin)

```python
for i in range(1, 6):
    print(i)
```

Resultado:

```
1
2
3
4
5
```

Regla: `range(inicio, fin)` incluye `inicio` y NO incluye `fin`.

### range con pasos

```python
for i in range(0, 11, 2):
    print(i)
```

Resultado:

```
0
2
4
6
8
10
```

Sintaxis: `range(inicio, fin, salto)`.

### Recorrer strings

Los `str` son secuencias:

```python
nombre = "Cristian"
for letra in nombre:
    print(letra)
```

Resultado:

```
C
r
i
s
t
i
a
n
```

### Recorrer listas

```python
frutas = ["manzana", "pera", "uva"]
for fruta in frutas:
    print(fruta)
```

Resultado:

```
manzana
pera
uva
```

---

## BREAK

`break` detiene un bucle inmediatamente.

```python
for i in range(10):
    if i == 5:
        break
    print(i)
```

Resultado:

```
0
1
2
3
4
```

Cuando `i == 5` se ejecuta `break` y el bucle termina.

---

## CONTINUE

`continue` salta la iteración actual y sigue con la siguiente.

```python
for i in range(5):
    if i == 2:
        continue
    print(i)
```

Resultado:

```
0
1
3
4
```

El `2` se omite.

---

## PASS

`pass` es un marcador de posición que no hace nada. Se usa cuando aún no implementaste el código.

```python
if True:
    pass
```

---

## ENUMERATE() (MUY IMPORTANTE)

En vez de usar `range(len(lista))`, usa `enumerate()` para obtener índice y valor:

```python
frutas = ["pera", "uva", "manzana"]
for indice, fruta in enumerate(frutas):
    print(indice, fruta)
```

Resultado:

```
0 pera
1 uva
2 manzana
```

Es más profesional y claro.

---

## ELSE EN BUCLES

Los bucles pueden llevar `else`. Se ejecuta cuando el bucle termina sin `break`.

```python
for i in range(5):
    print(i)
else:
    print("Bucle terminado")
```

Resultado:

```
0
1
2
3
4
Bucle terminado
```

Si el bucle termina con `break`, la cláusula `else` no se ejecuta.

---

## BUCLES ANIDADOS

Un bucle dentro de otro:

```python
for i in range(3):
    for j in range(2):
        print(i, j)
```

Resultado:

```
0 0
0 1
1 0
1 1
2 0
2 1
```

---

## TABLAS DE MULTIPLICAR (EJEMPLO)

```python
for i in range(1, 11):
    print(f"5 x {i} = {5*i}")
```

Resultado:

```
5 x 1 = 5
5 x 2 = 10
...
```

---

## COMPRENSIÓN DE LISTAS (INTRODUCCIÓN)

Construir listas con sintaxis concisa:

Normal:

```python
cuadrados = []
for i in range(5):
    cuadrados.append(i**2)
```

Pythonico:

```python
cuadrados = [i**2 for i in range(5)]
```

Resultado:

```
[0, 1, 4, 9, 16]
```

Más adelante veremos esto en detalle.

---

## ¿CUÁNDO USAR FOR Y CUÁNDO WHILE?

- Usa `for` cuando sabes cuántas veces repetir (p. ej. `for i in range(100)`).
- Usa `while` cuando no sabes cuántas repeticiones hasta que cambie una condición (p. ej. `while contraseña != correcta`).

---

## ERRORES TÍPICOS DE PRINCIPIANTES

Error 1 — indentación engañosa:

```python
for i in range(5):
    print(i)

    print("Hola")
```

Aquí el segundo `print` está dentro del bucle por la indentación.

Error 2 — olvidar actualizar contador en `while` → bucle infinito.

Error 3 — `range(1, 10)` no incluye `10`.

---

## MINI PROYECTO

Contador de números pares:

```python
for numero in range(0, 21, 2):
    print(numero)
```

Salida:

```
0
2
4
6
8
10
12
14
16
18
20
```

---

**Listo.** Añadí el contenido sobre bucles organizado en secciones, con ejemplos y explicaciones. Puedes pedirme que lo formatee con emojis y estilo igual a los otros archivos, añadir más ejercicios, o integrarlo en un índice general del curso.
