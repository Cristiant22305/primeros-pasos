# Condicionales (if, elif, else)

## 📑 Tabla de Contenidos
- [Introducción](#-introducción)
- [¿Qué significa if?](#-qué-significa-if)
- [Sintaxis y dos puntos](#-sintaxis-y-dos-puntos)
- [Indentación (MUY IMPORTANTE)](#indentación-muy-importante)
- [else](#else)
- [elif](#elif)
- [Operadores lógicos dentro de if](#operadores-lógicos-dentro-de-if)
  - [and](#and)
  - [or](#or)
  - [not](#not)
- [Comparar textos](#comparar-textos)
- [Anidación](#anidación)
- [Buenas prácticas](#buenas-prácticas)
- [Ejemplo real completo](#ejemplo-real-completo)
- [Ejercicios y respuestas](#ejercicios-y-respuestas)
- [Resumen: Lo que debes dominar](#resumen-lo-que-debes-dominar)

---

## 📌 Introducción

Imagina que llegas a una discoteca. Hay una regla:

Si eres mayor de edad, puedes entrar.

En lenguaje humano sería:

Si edad >= 18
    puede entrar

En Python:

```python
edad = 20

if edad >= 18:
    print("Puedes entrar")
```

Resultado:

```
Puedes entrar
```

---

## ❓ ¿Qué significa if?

`if` significa: "Si esta condición es verdadera, ejecuta este bloque de código." 

Sintaxis básica:

```python
if condicion:
    instrucciones
```

Observa los dos puntos `:` — son obligatorios.

---

## Indentación (MUY IMPORTANTE)

Los espacios antes de las líneas no son decoración: se llaman indentación. Python usa la indentación para saber qué instrucciones pertenecen al `if`.

Correcto:

```python
if edad >= 18:
    print("Puedes entrar")
```

Incorrecto (error de indentación):

```python
if edad >= 18:
print("Puedes entrar")
```

Ejemplo visual:

```python
if condicion:
    linea_1
    linea_2
    linea_3
```

Todo lo que esté indentado pertenece al `if`.

---

## else

¿Qué pasa si queremos hacer algo cuando la condición sea falsa? Usamos `else`.

```python
edad = 15

if edad >= 18:
    print("Puedes entrar")
else:
    print("No puedes entrar")
```

Resultado:

```
No puedes entrar
```

Traducción mental:

Si edad >= 18 → entra
Si no → no entra

---

## elif

Cuando hay más de dos opciones usamos `elif` (else if). Ejemplo de una escala de notas:

```python
nota = 4.5

if nota >= 5:
    print("Excelente")

elif nota >= 4:
    print("Bueno")

elif nota >= 3:
    print("Aprobado")

else:
    print("Reprobado")
```

Resultado:

```
Bueno
```

Cómo lo evalúa Python: pregunta por la primera condición; si es falsa pasa a la siguiente; cuando encuentra la primera verdadera ejecuta su bloque y termina.

> Error común: usar varios `if` independientes cuando las opciones son excluyentes — esto puede imprimir varias respuestas.

Incorrecto ejemplo:

```python
nota = 4.5

if nota >= 5:
    print("Excelente")

if nota >= 4:
    print("Bueno")

if nota >= 3:
    print("Aprobado")
```

Salida:

```
Bueno
Aprobado
```

Por eso se usa `if` / `elif` / `else` cuando las condiciones son mutuamente excluyentes.

---

## Operadores lógicos dentro de if

Puedes combinar condiciones con `and`, `or` y `not`.

### and

Ambas condiciones deben ser verdaderas.

```python
edad = 20
tiene_documento = True

if edad >= 18 and tiene_documento:
    print("Puede entrar")
```

### or

Basta con que una condición sea verdadera.

```python
es_profesor = False
es_director = True

if es_profesor or es_director:
    print("Acceso permitido")
```

### not

Invierte el valor booleano.

```python
es_banado = False

if not es_banado:
    print("Puede ingresar")
```

---

## Comparar textos

También puedes comparar `str`.

```python
nombre = "Cristian"

if nombre == "Cristian":
    print("Bienvenido")
```

Resultado:

```
Bienvenido
```

Ojo: las comparaciones son sensibles a mayúsculas/minúsculas:

```python
print("Cristian" == "cristian")  # False
```

---

## Anidación

Puedes tener un `if` dentro de otro `if`.

```python
edad = 20
tiene_entrada = True

if edad >= 18:
    if tiene_entrada:
        print("Puedes ingresar")
    else:
        print("Necesitas entrada")
else:
    print("Eres menor de edad")
```

---

## Buenas prácticas

- Usa nombres descriptivos para las variables.
  - Mal: `x = 20`
  - Bien: `edad = 20`

- No escribas condiciones redundantes:
  - Mal: `if tiene_carnet == True:`
  - Bien: `if tiene_carnet:`

- Evita bloques muy largos; extrae lógica a funciones cuando sea necesario.

---

## Ejemplo real completo

```python
usuario = input("Usuario: ")
clave = input("Contraseña: ")

if usuario == "admin" and clave == "1234":
    print("Acceso concedido")
else:
    print("Acceso denegado")
```

---

## Ejercicios y respuestas

Ejercicio 1:

```python
edad = 17

if edad >= 18:
    print("Adulto")
else:
    print("Menor")
```

Respuesta:

```
Menor
```

Ejercicio 2:

```python
nota = 3.8

if nota >= 4.5:
    print("Excelente")

elif nota >= 3:
    print("Aprobado")

else:
    print("Reprobado")
```

Respuesta:

```
Aprobado
```

---

## ✅ Resumen: Lo que debes dominar

- Estructuras: `if condicion:`, `if condicion: else:`, `if condicion: elif condicion: else:`
- Operadores: `==`, `!=`, `>`, `<`, `>=`, `<=`, `and`, `or`, `not`
- Indentación: define los bloques de código en Python — es fundamental.

---

**Listo.** Este archivo explica condicionales con ejemplos y ejercicios. Pronto puedo añadir más ejercicios, soluciones comentadas o integrar este tema en una lección más amplia sobre estructuras de control.
