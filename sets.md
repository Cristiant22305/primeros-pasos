# SETS (CONJUNTOS)

## 📑 Tabla de Contenidos
- [Introducción](#-introducción)
- [¿Qué es un Set?](#-qué-es-un-set)
- [Crear un set y la característica más importante](#crear-un-set-y-la-característica-más-importante)
- [Set vacío](#crear-set-vacío)
- [Longitud y añadir elementos](#longitud-y-añadir-elementos)
- [Eliminar elementos: remove, discard, pop, clear](#eliminar-elementos)
- [Verificar existencia y recorrer sets](#verificar-existencia-y-recorrer-sets)
- [Convertir entre estructuras](#convertir-entre-estructuras)
- [Operaciones matemáticas: unión, intersección, diferencia](#operaciones-matemáticas)
- [Subconjuntos, superconjuntos y disjuntos](#subconjuntos-superconjuntos-y-disjuntos)
- [frozenset (set inmutable)](#frozenset-set-inmutable)
- [Comprensión de sets](#comprensión-de-sets)
- [Diferencias con listas y cuándo usar cada uno](#diferencias-con-listas)
- [Trucos profesionales](#trucos-profesionales)
- [Errores comunes](#errores-comunes)
- [Mini proyecto](#mini-proyecto)

---

## 📌 Introducción

Los `set` (conjuntos) son una estructura de datos poderosa y muy útil, especialmente en ciencia de datos, ML y análisis. Son rápidos para búsquedas y operaciones de conjuntos.

---

## ❓ ¿Qué es un Set?

Un `set` es una colección de elementos con estas características:

- Sin duplicados
- Desordenada (no mantiene posiciones garantizadas)
- Muy rápida para búsquedas

---

## Crear un set y la característica más importante

```python
numeros = {1, 2, 3, 4}
frutas = {"manzana", "pera", "uva"}
```

Si intentas crear con duplicados:

```python
numeros = {1, 2, 2, 3, 3, 3}
# Resultado: {1, 2, 3}
```

Python elimina automáticamente duplicados.

---

## Crear set vacío

❌ Incorrecto (crea un dict):

```python
vacio = {}
```

✅ Correcto:

```python
vacio = set()
```

---

## Longitud y añadir elementos

```python
len(numeros)  # cuenta elementos únicos

# Añadir un elemento
numeros.add(5)

# Añadir varios
numeros.update([6,7,8])
```

Si el elemento ya existe, `add()` no hace nada.

---

## Eliminar elementos

- `remove(x)` elimina `x` pero lanza `KeyError` si no existe.
- `discard(x)` elimina si existe; no lanza error si no existe (más seguro).
- `pop()` elimina y devuelve un elemento arbitrario (los sets no tienen orden).
- `clear()` vacía el set.

```python
numeros.remove(3)
numeros.discard(10)  # no error si 10 no está
el = numeros.pop()
numeros.clear()
```

---

## Verificar existencia y recorrer sets

Las búsquedas en sets son muy rápidas:

```python
if "Ana" in nombres:
    print("Existe")

for elemento in conjunto:
    print(elemento)  # el orden puede variar
```

---

## Convertir entre estructuras

- Lista → Set: elimina duplicados

```python
lista = [1,2,2,3]
conjunto = set(lista)  # {1,2,3}
```

- Set → Lista:

```python
lista = list(conjunto)
```

---

## Operaciones matemáticas

- Unión: elementos de ambos conjuntos

```python
a = {1,2,3}
b = {3,4,5}
print(a | b)           # {1,2,3,4,5}
print(a.union(b))      # equivalente
```

- Intersección: elementos comunes

```python
print(a & b)           # {3}
print(a.intersection(b))
```

- Diferencia: en A pero no en B

```python
print(a - b)           # {1,2}
print(a.difference(b))
```

- Diferencia simétrica: no comparten

```python
print(a ^ b)           # {1,2,4,5}
print(a.symmetric_difference(b))
```

---

## Subconjuntos, superconjuntos y disjuntos

```python
a = {1,2}
b = {1,2,3,4}
print(a.issubset(b))   # True
print(b.issuperset(a)) # True

c = {5,6}
print(a.isdisjoint(c)) # True (sin elementos en común)
```

---

## frozenset (set inmutable)

Existe una versión inmutable:

```python
f = frozenset([1,2,3])
# f.add(4) -> AttributeError
```

Útil cuando necesitas sets como claves en otros dicts o como elementos inmutables.

---

## Comprensión de sets

Similar a las listas:

```python
cuadrados = {x**2 for x in range(5)}  # {0,1,4,9,16}
pares = {x for x in range(20) if x%2==0}
```

---

## Diferencias con listas y cuándo usar cada uno

- Lista: mantiene orden, permite repetidos, tiene índices.
- Set: sin duplicados, sin índices, búsquedas muy rápidas.

Usa listas cuando importa el orden o necesitas índices. Usa sets cuando quieras eliminar duplicados, buscar rápidamente o hacer operaciones de conjuntos.

---

## Trucos profesionales

Eliminar duplicados rápidamente:

```python
numeros = [1,2,2,3,3,4]
numeros = list(set(numeros))
```

Encontrar comunes entre dos colecciones:

```python
materias_juan = {"Matemáticas","Física","Programación"}
materias_ana = {"Física","Química","Programación"}
comunes = materias_juan & materias_ana
# {'Física','Programación'}
```

---

## Errores comunes

- `vacio = {}` crea un `dict`, no un `set`.
- Intentar acceder por índice: `set[0]` → Error.
- Confiar en el orden de iteración: el orden puede cambiar.

---

## MINI PROYECTO: Contar palabras únicas

```python
texto = input("Ingrese una frase: ")
palabras = texto.lower().split()
unicas = set(palabras)
print(f"Palabras únicas: {len(unicas)}")
print(unicas)
```

---

**Listo.** Añadí `sets.md` con explicación, ejemplos, operaciones y un mini proyecto.
