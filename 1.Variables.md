# 🐍 TEORÍA PYTHON

## 📑 Tabla de Contenidos
- [Variables](#-variables)
- [Tipos de Datos](#-tipos-de-datos)
- [Funciones Importantes](#-funciones-importantes)
- [Ejemplo Real](#-ejemplo-real)
- [Errores Comunes](#-errores-comunes)
- [Resumen](#-resumen-final)

---

## 📋 VARIABLES

### ¿Qué es una variable?

Una variable es un **espacio en la memoria** donde guardas información. Piénsalo como una **caja con una etiqueta**.

```
┌─────────────────────┐
│   CAJA (Variable)   │
├─────────────────────┤
│  Nombre: dinero     │
│  Contenido: 50000   │
└─────────────────────┘
```

**Ejemplo práctico:**
```python
dinero = 50000
```

- `dinero` → Es la **etiqueta** (nombre de la variable)
- `50000` → Es lo que **guardamos adentro** (valor)

---

### ¿Por qué existen las variables?

Sin variables, el código sería **confuso y difícil de mantener**.

| Sin variables | Con variables |
|---|---|
| `print(50000 + 20000)` | `salario = 50000`<br>`bono = 20000`<br>`print(salario + bono)` |
| ❌ Nadie entiende qué es 50000 | ✅ Es claro: salario + bono |

**Las variables hacen el código legible y mantenible.**

---

### ¿Cómo crear una variable?

**Sintaxis básica:**
```python
nombre_variable = valor
```

**Ejemplos:**
```python
nombre = "Cristian"      # Texto (string)
edad = 20                # Número entero (int)
altura = 1.75            # Número decimal (float)
es_estudiante = True     # Verdadero o Falso (boolean)
```

---

### ⚠️ IMPORTANTE: El signo `=` NO es igualdad matemática

Este es el **error más común** de los principiantes.

| En Matemáticas | En Python |
|---|---|
| `x = 5` significa "x es igual a 5" | `x = 5` significa "Guarda 5 dentro de x" |

**Piénsalo así:**
- `=` es una **asignación** (guardar un valor)
- No es una comparación de igualdad

```python
x = 5       # Guarda 5 en x
x = 10      # Ahora x contiene 10 (el 5 se perdió)
print(x)    # Muestra: 10
```

---

### Reasignación: Las variables pueden cambiar

Una variable puede **cambiar su valor** múltiples veces:

```python
dinero = 100
print(dinero)    # Muestra: 100

dinero = 200     # Cambia el valor
print(dinero)    # Muestra: 200
```

**El valor anterior se reemplaza por el nuevo.**

---

### Reglas para nombrar variables

#### ✅ NOMBRES VÁLIDOS

```python
nombre = "Cristian"
edad = 20
numero_estudiantes = 35
dias_del_mes = 30
```

#### ❌ NOMBRES INVÁLIDOS

| Error | Razón |
|---|---|
| `2nombre = "Cristian"` | ❌ No puede empezar con números |
| `mi nombre = "Cristian"` | ❌ No puede tener espacios |
| `class = 10` | ❌ No puede usar palabras reservadas de Python |
| `nombre-completo = "Juan"` | ❌ No puede usar guiones (se interpretan como resta) |

---

### 🎯 ESTILO PROFESIONAL: snake_case

En Python se usa **snake_case** para nombrar variables:

| ✅ Correcto (snake_case) | ❌ Incorrecto |
|---|---|
| `precio_total` | `PrecioTotal` (camelCase) |
| `nombre_completo` | `precioTotal` (camelCase) |
| `cantidad_estudiantes` | `PRECIOTOTAL` (SCREAMING_SNAKE_CASE) |

**¿Por qué importa?**
- Es la **convención de Python**
- En proyectos grandes es **obligatorio**
- El equipo de trabajo lo requiere
- Un programador pasa más tiempo **leyendo código** que escribiéndolo

**Mal:**
```python
a = 100
b = 200
c = a + b
```
❌ Nadie entiende qué son a, b, c

**Bien:**
```python
precio_producto = 100
precio_envio = 200
precio_total = precio_producto + precio_envio
```
✅ Está claro qué calcula cada variable

---

## 🔢 TIPOS DE DATOS

Una variable puede guardar diferentes tipos de información. Python detecta automáticamente qué tipo de dato es.

### 1️⃣ TEXTO (str - String)

Cualquier texto va entre **comillas simples o dobles**.

```python
nombre = "Cristian"
ciudad = 'Medellín'
mensaje = "Hola, ¿cómo estás?"
```

✅ **Las comillas son obligatorias** para textos.

---

### 2️⃣ NÚMEROS ENTEROS (int - Integer)

Números sin decimales.

```python
edad = 20
cantidad = 150
temperatura = -5
dinero = 0
```

---

### 3️⃣ NÚMEROS DECIMALES (float - Floating Point)

Números con punto decimal.

```python
altura = 1.75
precio = 99.99
promedio = 4.5
temperatura = 36.5
```

---

### 4️⃣ BOOLEANOS (bool - Boolean)

Solo tienen **dos valores posibles**: `True` o `False`

```python
es_mayor_de_edad = True
tiene_descuento = False
es_estudiante = True
aprobó_examen = False
```

---

### Ver el tipo de una variable: `type()`

Para saber qué tipo de dato contiene una variable, usa `type()`:

```python
edad = 20
print(type(edad))
```

**Resultado:**
```
<class 'int'>
```

**Otros ejemplos:**
```python
print(type("Cristian"))           # <class 'str'>
print(type(1.75))                 # <class 'float'>
print(type(True))                 # <class 'bool'>
```

---

## 🛠️ FUNCIONES IMPORTANTES

Estas funciones son **esenciales** desde el primer día.

### 📤 `print()` - Mostrar información

Muestra valores en pantalla.

```python
print("Hola mundo")
print(20)
print(3.14)
```

**Resultado:**
```
Hola mundo
20
3.14
```

---

### 🔍 `type()` - Ver el tipo de dato

```python
print(type("texto"))     # <class 'str'>
print(type(20))          # <class 'int'>
print(type(3.14))        # <class 'float'>
```

---

### 📏 `len()` - Contar elementos

Cuenta caracteres en un texto o elementos en una lista.

```python
nombre = "Cristian"
print(len(nombre))       # 8
```

**Otros ejemplos:**
```python
texto = "Python"
print(len(texto))        # 6

frase = "Hola mundo"
print(len(frase))        # 11 (incluye el espacio)
```

---

### ⌨️ `input()` - Recibir entrada del usuario

Permite que el usuario escriba información desde el teclado.

```python
nombre = input("Escribe tu nombre: ")
print(nombre)
```

**Si el usuario escribe:** `Cristian`

**Python guardará:** `"Cristian"`

**Será un texto (str), no un número.**

---

## 📝 Mostrar variables con `print()`

### Opción 1: Concatenación simple

```python
nombre = "Cristian"
print("Hola " + nombre)
```

**Resultado:**
```
Hola Cristian
```

❌ **Funciona pero es viejo**

---

### Opción 2: f-strings (RECOMENDADO) ⭐

```python
nombre = "Cristian"
print(f"Hola {nombre}")
```

**Resultado:**
```
Hola Cristian
```

✅ **Esto es lo moderno. Úsalo siempre.**

**Más ejemplos con f-strings:**
```python
nombre = "Juan"
edad = 25
altura = 1.80

print(f"Mi nombre es {nombre}")
print(f"Tengo {edad} años")
print(f"Mido {altura} metros")

# Incluso puedes hacer operaciones dentro
print(f"El próximo año tendré {edad + 1} años")
```

---

## 💼 EJEMPLO REAL: Registrar un estudiante

Vamos a crear un programa que guarde información de un estudiante:

```python
# Guardamos la información
nombre = "Cristian"
edad = 20
promedio = 4.5
es_becado = True

# Mostramos la información
print(f"Nombre: {nombre}")
print(f"Edad: {edad}")
print(f"Promedio: {promedio}")
print(f"Becado: {es_becado}")
```

**Resultado:**
```
Nombre: Cristian
Edad: 20
Promedio: 4.5
Becado: True
```

---

## ❌ ERRORES COMUNES DE PRINCIPIANTES

### Error 1: Olvidar las comillas en textos

| ❌ Incorrecto | ✅ Correcto |
|---|---|
| `nombre = Cristian` | `nombre = "Cristian"` |

**Resultado del error:**
```
NameError: name 'Cristian' is not defined
```

Python cree que `Cristian` es una variable, no un texto.

---

### Error 2: Confundir texto con número

| ❌ Incorrecto | ✅ Correcto |
|---|---|
| `edad = "20"` | `edad = 20` |

**¿Por qué importa?**
```python
edad_texto = "20"
edad_numero = 20

# Esto da error:
print(edad_texto + 5)           # ❌ Error: no se puede sumar texto + número

# Esto funciona:
print(edad_numero + 5)          # ✅ Resultado: 25
```

---

### Error 3: Usar nombres confusos o muy cortos

| ❌ Malo | ✅ Bueno |
|---|---|
| `a = 100`<br>`b = 200`<br>`c = a + b` | `precio_producto = 100`<br>`precio_envio = 200`<br>`precio_total = precio_producto + precio_envio` |

**¿Cuál entiendes más rápido?** Obviamente el segundo.

---

### Error 4: Usar variables antes de crearlas

```python
print(dinero)        # ❌ Error: dinero no existe
dinero = 100         # Aquí la creamos
```

**Correcto:**
```python
dinero = 100         # Primero la creamos
print(dinero)        # ✅ Ahora sí funciona
```

---

## ⭐ RESUMEN FINAL

### Conceptos Clave

| Concepto | Explicación |
|---|---|
| **Variable** | Espacio en memoria que guarda información |
| **Nombre** | La etiqueta de la variable (debe ser descriptivo) |
| **Valor** | Lo que guardamos adentro de la variable |
| **Reasignación** | Cambiar el valor de una variable |
| **Tipo de dato** | El tipo de información que guarda (str, int, float, bool) |

---

### Lo que DEBES dominar

✅ **Crear variables:**
```python
nombre = "Juan"
edad = 25
precio = 19.99
```

✅ **Usar snake_case:**
```python
nombre_completo = "Juan Pérez"      # ✅ Correcto
nombreCompleto = "Juan Pérez"       # ❌ Incorrecto
```

✅ **Ver tipos de datos:**
```python
print(type(variable))
```

✅ **Mostrar con f-strings:**
```python
print(f"Texto {variable}")
```

✅ **Las funciones básicas:**
- `print()` - Mostrar
- `type()` - Ver tipo
- `len()` - Contar
- `input()` - Recibir entrada

---

### Reflexión final

> **Un programador pasa 90% del tiempo leyendo código y 10% escribiendo código.**
>
> Por eso los nombres de las variables deben ser **claros, descriptivos y fáciles de entender**.

---

**🎉 ¡Ya dominas las variables en Python! El siguiente paso es aprender operadores y estructuras de control.**
