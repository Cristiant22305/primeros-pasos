# DICCIONARIOS (VERSIÓN COMPLETA)

## 📑 Tabla de Contenidos
- [Introducción](#-introducción)
- [¿Qué es un diccionario?](#-qué-es-un-diccionario)
- [Por qué usar diccionarios](#por-qué-usar-diccionarios)
- [Sintaxis](#sintaxis)
- [Acceder a valores](#acceder-a-valores)
- [Modificar y agregar valores](#modificar-y-agregar-valores)
- [Eliminar elementos: del y pop()](#eliminar-elementos-del-y-pop)
- [Longitud y verificar existencia](#longitud-y-verificar-existencia)
- [get() (MUY IMPORTANTE)](#get-muy-importante)
- [Recorrer diccionarios: keys(), values(), items()](#recorrer-diccionarios)
- [Diccionarios anidados y listas dentro de diccionarios](#diccionarios-anidados-y-listas-dentro-de-diccionarios)
- [copy() y update()](#copy-y-update)
- [setdefault()](#setdefault)
- [Crear diccionarios rápidamente](#crear-diccionarios-rapidamente)
- [Comprensión de diccionarios](#comprensión-de-diccionarios)
- [Funciones útiles](#funciones-útiles)
- [Claves válidas y error común](#claves-válidas-y-error-común)
- [Truco profesional: contar letras](#truco-profesional-contar-letras)
- [JSON y uso real](#json-y-uso-real)
- [Mini proyecto: agenda simple](#mini-proyecto-agenda-simple)

---

## 📌 Introducción

Si las listas almacenan colecciones ordenadas, los diccionarios almacenan pares clave → valor. Son la estructura más utilizada en aplicaciones reales (APIs, JSON, bases de datos, web, ML, etc.). Dominar diccionarios es obligatorio.

---

## ❓ ¿Qué es un diccionario?

Un diccionario guarda datos en pares:

```python
persona = {
    "nombre": "Cristian",
    "edad": 20,
    "ciudad": "Medellín"
}
```

Visualmente:

```
nombre → Cristian
edad   → 20
ciudad → Medellín
```

---

## Por qué usar diccionarios

Con una lista no es claro qué significa cada posición:

```python
persona = ["Cristian", 20, "Medellín"]
```

Con un diccionario accedes por clave:

```python
persona["nombre"]  # mucho más claro
```

---

## Sintaxis

```python
diccionario = {
    clave: valor,
    clave: valor
}

estudiante = {
    "nombre": "Ana",
    "promedio": 4.8,
    "activo": True
}
```

---

## Acceder a valores

```python
persona = {"nombre": "Cristian", "edad": 20}
print(persona["nombre"])  # 'Cristian'
print(persona["edad"])    # 20
```

Evita acceder con `persona["telefono"]` si no estás seguro; puede lanzar KeyError.

---

## Modificar y agregar valores

Modificar:

```python
persona["edad"] = 21
```

Agregar nueva clave:

```python
persona["carrera"] = "Ingeniería"
```

---

## Eliminar elementos: del y pop()

Usando `del`:

```python
del persona["edad"]
```

Usando `pop()` (elimina y devuelve):

```python
edad = persona.pop("edad")  # devuelve 20
```

---

## Longitud y verificar existencia

```python
len(persona)  # número de pares clave-valor

if "telefono" in persona:
    print("Existe")
```

---

## get() (MUY IMPORTANTE)

Forma segura de acceder sin causar error:

```python
persona.get("nombre")       # 'Cristian'
persona.get("telefono")    # None (no error)
persona.get("telefono", "No registrado")  # 'No registrado'
```

---

## Recorrer diccionarios

Solo claves:

```python
for clave in persona:
    print(clave)
```

Usando `keys()` (equivalente):

```python
for clave in persona.keys():
    print(clave)
```

Solo valores:

```python
for valor in persona.values():
    print(valor)
```

Clave y valor (MUY IMPORTANTE — profesional):

```python
for clave, valor in persona.items():
    print(clave, valor)
```

---

## Diccionarios anidados y listas dentro de diccionarios

Diccionario dentro de diccionario:

```python
estudiante = {
    "nombre": "Cristian",
    "notas": {
        "matematicas": 4.5,
        "fisica": 4.2
    }
}

print(estudiante["notas"]["matematicas"])  # 4.5
```

Listas dentro de diccionarios:

```python
persona = {"nombre": "Cristian", "hobbies": ["fútbol","programación"]}
print(persona["hobbies"][0])  # 'fútbol'
```

Diccionarios dentro de listas (muy frecuente):

```python
estudiantes = [
    {"nombre": "Ana", "edad": 20},
    {"nombre": "Luis", "edad": 22}
]
print(estudiantes[1]["nombre"])  # 'Luis'
```

---

## copy() y update()

Evita hacer `b = a` si quieres una copia; ambos apuntarán al mismo objeto.

```python
a = {"x": 1}
b = a  # apunta al mismo diccionario
b["x"] = 2
# a también cambia
```

Copia correcta:

```python
b = a.copy()
```

`update()` actualiza varios valores:

```python
persona.update({"edad": 21, "ciudad": "Medellín"})
```

---

## setdefault()

Muy útil para asegurar claves con valor por defecto:

```python
persona.setdefault("telefono", "No registrado")
# si no existe, la crea con el valor por defecto
```

Si ya existe, no la modifica.

---

## Crear diccionarios rápidamente

```python
persona = dict(nombre="Cristian", edad=20)
```

---

## Comprensión de diccionarios

Versión concisa para construir diccionarios:

```python
cuadrados = {x: x**2 for x in range(5)}
# {0:0, 1:1, 2:4, 3:9, 4:16}
```

---

## Funciones útiles

- `keys()`, `values()`, `items()`
- `get()`
- `update()`
- `pop()`

---

## Claves válidas y error común

Las claves pueden ser strings, números o booleanos. Normalmente usarás strings.

Error común: repetir la misma clave — la última sobrescribe:

```python
persona = {"nombre": "Cristian", "nombre": "Ana"}
# resultado: {'nombre': 'Ana'}
```

Las claves deben ser únicas.

---

## Truco profesional: contar letras

Contar ocurrencias de caracteres con un diccionario:

```python
texto = "banana"
contador = {}
for letra in texto:
    contador[letra] = contador.get(letra, 0) + 1
print(contador)
# {'b':1, 'a':3, 'n':2}
```

Este patrón aparece muchísimo.

---

## JSON y uso real

Los datos que recibes de APIs o la web suelen ser JSON, que se mapea naturalmente a diccionarios en Python:

```python
usuario = {"id":1, "nombre":"Cristian", "email":"correo@gmail.com"}
```

Si dominas diccionarios, aprender JSON es muy sencillo.

---

## Mini proyecto: Agenda simple

```python
contactos = {
    "Ana": "12345",
    "Luis": "67890",
    "Cristian": "54321"
}

nombre = input("Buscar contacto: ")
if nombre in contactos:
    print(contactos[nombre])
else:
    print("No encontrado")
```

---

**Listo.** Añadí `diccionarios.md` con la lección completa sobre diccionarios: definiciones, ejemplos, métodos, trucos y un mini proyecto.
