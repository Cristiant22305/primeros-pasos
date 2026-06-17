# ARCHIVOS (FILE HANDLING)

## 📑 Tabla de Contenidos
- [Introducción](#-introducción)
- [¿Qué es un archivo?](#-qué-es-un-archivo)
- [Abrir un archivo: open()](#abrir-un-archivo)
- [Leer archivos: read, readline, readlines](#leer-archivos)
- [Cerrar archivos y el problema de olvidar close()](#cerrar-archivos-y-el-problema-de-olvidar-close)
- [with (forma profesional)](#with-forma-profesional)
- [Modos de apertura (r, w, a, x, r+)](#modos-de-apertura)
- [Escribir archivos: write, append](#escribir-archivos)
- [Crear archivos automáticamente](#crear-archivos)
- [Verificar si existe un archivo (try/except)](#verificar-si-existe-un-archivo)
- [Codificación UTF-8](#codificación-utf-8)
- [Guardar y leer listas desde archivos](#guardar-y-leer-listas-desde-archivos)
- [strip() y archivos](#strip-y-archivos)
- [Mini proyectos](#mini-proyectos)
- [Manejo de errores con archivos](#manejo-de-errores-con-archivos)
- [Buenas prácticas](#buenas-prácticas)
- [Errores comunes](#errores-comunes)

---

## 📌 Introducción

Hasta ahora nuestros datos desaparecen cuando termina el programa. En aplicaciones reales necesitamos persistir información (usuarios, configuraciones, registros). Para eso se usan archivos.

---

## ❓ ¿Qué es un archivo?

Es información almacenada permanentemente en el disco. Ejemplos:

- notas.txt
- datos.csv
- usuarios.json
- config.txt

---

## Abrir un archivo: open()

La función principal es `open()`:

```python
archivo = open("archivo.txt")
```

---

## Leer archivos: read, readline, readlines

Leer todo el contenido:

```python
with open("archivo.txt") as archivo:
    contenido = archivo.read()
    print(contenido)
```

Leer una sola línea:

```python
with open("archivo.txt") as archivo:
    print(archivo.readline())
```

Leer varias líneas (devuelve lista):

```python
with open("archivo.txt") as archivo:
    lineas = archivo.readlines()
    print(lineas)  # ['Ana\n', 'Luis\n', 'Cristian\n']
```

Recorrer un archivo línea por línea:

```python
with open("archivo.txt") as archivo:
    for linea in archivo:
        print(linea)
```

---

## Cerrar archivos y el problema de olvidar close()

Después de usar un archivo debes cerrarlo con `archivo.close()`. Si ocurre un error antes de cerrar el archivo, éste puede quedar abierto, por eso se recomienda `with`.

---

## with (forma profesional)

Usa `with` para manejar archivos: cierra automáticamente al salir del bloque.

```python
with open("archivo.txt") as archivo:
    contenido = archivo.read()
    print(contenido)
```

---

## Modos de apertura

Debes indicar qué quieres hacer:

- Lectura: `open("archivo.txt", "r")` — `r` por defecto.
- Escritura: `open("archivo.txt", "w")` — borra el contenido anterior.
- Append: `open("archivo.txt", "a")` — añade al final.
- Crear: `open("archivo.txt", "x")` — crea y falla si ya existe.
- Leer y escribir: `open("archivo.txt", "r+")`

---

## Escribir archivos: write, escribir varias líneas

Escribir (modo `w` borra contenido previo):

```python
with open("archivo.txt", "w") as archivo:
    archivo.write("Hola mundo")
```

Escribir varias líneas:

```python
with open("archivo.txt", "w") as archivo:
    archivo.write("Ana\n")
    archivo.write("Luis\n")
    archivo.write("Cristian\n")
```

---

## Modo append

Añadir al final sin borrar:

```python
with open("archivo.txt", "a") as archivo:
    archivo.write("\nLuis")
```

Diferencia entre `w` y `a`:

- `w` borra y escribe desde cero.
- `a` conserva el contenido y añade al final.

---

## Crear archivos

Si el archivo no existe, `w` lo crea automáticamente:

```python
with open("nuevo.txt", "w") as archivo:
    archivo.write("Hola")
```

---

## Verificar si existe un archivo

Usa try/except para manejar `FileNotFoundError`:

```python
try:
    with open("datos.txt") as archivo:
        print(archivo.read())
except FileNotFoundError:
    print("Archivo no encontrado")
```

---

## Codificación UTF-8

Importante para caracteres en español:

```python
with open("archivo.txt", "r", encoding="utf-8") as archivo:
    texto = archivo.read()
```

Esto evita problemas con `á é í ó ú ñ`.

---

## Guardar y leer listas desde archivos

Guardar una lista en un archivo (una línea por elemento):

```python
nombres = ["Ana", "Luis", "Cristian"]
with open("nombres.txt", "w", encoding="utf-8") as archivo:
    for nombre in nombres:
        archivo.write(nombre + "\n")
```

Leer una lista desde un archivo:

```python
nombres = []
with open("nombres.txt", encoding="utf-8") as archivo:
    for linea in archivo:
        nombres.append(linea.strip())
# ['Ana', 'Luis', 'Cristian']
```

---

## strip() y archivos

Las líneas suelen traer el carácter de nueva línea `"\n"`. Usa `linea.strip()` para limpiar espacios y saltos.

---

## Mini proyectos

Bloc de notas (añadir nota):

```python
nota = input("Escriba una nota: ")
with open("notas.txt", "a", encoding="utf-8") as archivo:
    archivo.write(nota + "\n")
```

Contador de líneas:

```python
contador = 0
with open("archivo.txt", encoding="utf-8") as archivo:
    for linea in archivo:
        contador += 1
print(contador)
```

---

## Manejo de errores con archivos

Ejemplo con try/except:

```python
try:
    with open("datos.txt") as archivo:
        print(archivo.read())
except FileNotFoundError:
    print("El archivo no existe")
```

---

## Buenas prácticas

- Siempre usa `with` para abrir archivos.
- Especifica `encoding="utf-8"` cuando trabajes con texto.
- Usa `try/except` cuando el archivo pueda no existir.

---

## Errores comunes

1) Abrir en `"w"` sin saber que borra el contenido.
2) Olvidar `"\n"` al escribir varias líneas.
3) No usar `strip()` al leer líneas.
4) No cerrar archivos cuando no se usa `with`.

---

**Listo.** Añadí `archivos.md` con una guía completa sobre manejo de archivos en Python: abrir/leer/escribir, modos, encoding, buenas prácticas y mini proyectos.
