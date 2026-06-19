# 🔧 OPERADORES: Hacer cosas con los datos

## 📑 Tabla de Contenidos
- [Introducción](#-introducción)
- [Operadores Aritméticos](#-operadores-aritméticos)
- [Operadores de Comparación](#-operadores-de-comparación)
- [Operadores Lógicos](#-operadores-lógicos)
- [Buenas Prácticas](#-buenas-prácticas)
- [Ejercicios](#-ejercicios-para-practicar)
- [Resumen](#-resumen-de-la-lección)

---

## 📌 Introducción

Piensa en las variables como **cajas que guardan información**.

Los operadores son las **herramientas** que usamos para modificar, comparar o combinar lo que hay dentro de esas cajas.

Existen tres grupos que debes dominar:

1. **Operadores aritméticos** (matemáticas)
2. **Operadores de comparación** (comparar valores)
3. **Operadores lógicos** (combinar condiciones)

---

## 🔢 OPERADORES ARITMÉTICOS

Son los más familiares porque vienen de las matemáticas.

### ➕ Suma (+)

```python
a = 10
b = 5

resultado = a + b

print(resultado)
```

**Salida:**
```
15
```

---

### ➖ Resta (-)

```python
a = 10
b = 5

print(a - b)
```

**Salida:**
```
5
```

---

### ✖️ Multiplicación (*)

```python
print(10 * 5)
```

**Salida:**
```
50
```

---

### ➗ División (/)

```python
print(10 / 5)
```

**Salida:**
```
2.0
```

⚠️ **Observa algo curioso:**

Aunque el resultado es 2, Python devuelve:

```
2.0
```

Porque `/` **siempre produce un decimal (float)**.

---

### 🔹 División entera (//)

A veces solo quieres la parte entera.

```python
print(10 // 3)
```

**Resultado:**
```
3
```

¿Por qué?

```
10 ÷ 3 = 3.333...

Python se queda con: 3
```

---

### 🔄 Módulo o residuo (%)

Devuelve el **sobrante de una división**.

```python
print(10 % 3)
```

**Resultado:**
```
1
```

¿Por qué?

```
10 ÷ 3 = 3

Sobró: 1
```

#### ¿Para qué sirve?

Muchísimo. Por ejemplo, **saber si un número es par**:

```python
numero = 8

print(numero % 2)
```

**Resultado:**
```
0
```

✅ Si el residuo es 0, es par.

---

### ⚡ Potencia (**)

```python
print(2 ** 3)
```

**Resultado:**
```
8
```

¿Por qué?

```
2 × 2 × 2 = 8
```

---

### 🎯 Jerarquía de operaciones

Python sigue las reglas matemáticas.

```python
resultado = 2 + 3 * 4
```

❌ No hace:
```
(2 + 3) * 4 = 20
```

✅ Hace:
```
2 + (3 * 4) = 14
```

**Resultado:**
```
14
```

---

### 🏗️ Usa paréntesis

Siempre que puedas.

| ❌ Mal | ✅ Bien |
|---|---|
| `resultado = 20 + 10 * 3 - 5` | `resultado = (20 + 10) * 3 - 5` |

Es más fácil de leer.

---

### ⚙️ Atajos que usan los programadores

Supongamos:

```python
contador = 10
```

Quieres sumarle 1.

Muchos hacen:

```python
contador = contador + 1
```

Funciona. Pero existe una forma más elegante:

```python
contador += 1
```

✅ **Es exactamente lo mismo.**

También:

```python
contador -= 1
contador *= 2
contador /= 2
```

**Ejemplo:**

```python
dinero = 100

dinero += 50

print(dinero)
```

**Resultado:**
```
150
```

---

## ⚖️ OPERADORES DE COMPARACIÓN

Estos responden una pregunta:

**¿Es verdadero o falso?**

Siempre devuelven:

- `True` ✅
- `False` ❌

---

### 🟰 Igual que (==)

```python
print(5 == 5)
```

**Resultado:**
```
True
```

⚠️ **Mucho cuidado:**

| `=` | `==` |
|---|---|
| Asignación | Comparación |

**Error común:**

```python
edad = 18  # ✅ Correcto: asignamos 18 a edad
edad == 18 # ✅ Pregunta: ¿edad es igual a 18?
```

---

### 🚫 Diferente de (!=)

```python
print(5 != 3)
```

**Resultado:**
```
True
```

---

### ⬆️ Mayor que (>)

```python
print(10 > 5)
```

**Resultado:**
```
True
```

---

### ⬇️ Menor que (<)

```python
print(3 < 8)
```

**Resultado:**
```
True
```

---

### ⬆️➡️ Mayor o igual (>=)

```python
print(10 >= 10)
```

**Resultado:**
```
True
```

---

### ⬇️➡️ Menor o igual (<=)

```python
print(8 <= 10)
```

**Resultado:**
```
True
```

---

### 💼 Ejemplo real

```python
edad = 20

print(edad >= 18)
```

**Resultado:**
```
True
```

✅ **Esto será la base para los futuros `if`.**

---

## 🧠 OPERADORES LÓGICOS

Aquí empezamos a pensar como programadores.

Permiten **combinar varias condiciones**.

---

### ✋ AND (y)

Significa: **Todo debe ser verdadero.**

**Ejemplo:**

```python
edad = 20
tiene_cedula = True

print(edad >= 18 and tiene_cedula)
```

**Resultado:**
```
True
```

✅ Porque ambas condiciones son verdaderas.

**Tabla mental:**

```
True  and True  → True
True  and False → False
False and True  → False
False and False → False
```

---

### 👆 OR (o)

Significa: **Basta con que una sea verdadera.**

**Ejemplo:**

```python
llueve = True
tengo_paraguas = False

print(llueve or tengo_paraguas)
```

**Resultado:**
```
True
```

✅ Porque al menos una es verdadera.

**Tabla mental:**

```
True  or True  → True
True  or False → True
False or True  → True
False or False → False
```

---

### 🔄 NOT (no)

**Invierte el valor.**

**Ejemplo:**

```python
es_estudiante = True

print(not es_estudiante)
```

**Resultado:**
```
False
```

---

### 🎬 Un ejemplo completo

Imagina una **discoteca**.

Para entrar debes:

✅ Ser mayor de edad.
✅ Tener documento.

```python
edad = 20
tiene_documento = True

puede_entrar = edad >= 18 and tiene_documento

print(puede_entrar)
```

**Resultado:**
```
True
```

---

## 💡 BUENAS PRÁCTICAS

### 📌 Espacios

| ❌ Mal | ✅ Bien |
|---|---|
| `resultado=10+5` | `resultado = 10 + 5` |

Mucho más legible.

---

### 📝 Variables descriptivas

| ❌ Mal | ✅ Bien |
|---|---|
| `a = 20`<br>`b = 18`<br>`print(a > b)` | `edad_cristian = 20`<br>`edad_minima = 18`<br>`print(edad_cristian > edad_minima)` |

---

## 🏋️ EJERCICIOS PARA PRACTICAR

Intenta **predecir el resultado** antes de ejecutar:

```python
edad = 20
promedio = 4.2

print(edad >= 18)
print(promedio > 4.0)
print(edad >= 18 and promedio > 4.0)
print(edad < 18 or promedio > 4.0)
print(not (edad < 18))
```

Si puedes **explicar por qué sale cada resultado**, entonces ya entiendes los operadores a un nivel muy sólido. ✅

---

## ⭐ RESUMEN DE LA LECCIÓN

### Operadores Aritméticos

```
+   suma
-   resta
*   multiplicación
/   división
//  división entera
%   residuo
**  potencia
```

### Operadores de Comparación

```
==  igual
!=  diferente
>   mayor
<   menor
>=  mayor o igual
<=  menor o igual
```

### Operadores Lógicos

```
and   todas las condiciones verdaderas
or    al menos una condición verdadera
not   invierte el valor
```

---

**🎉 ¡Ahora dominas los operadores! El siguiente paso es usar esto con estructuras de control como `if`, `else` y `elif`.**
