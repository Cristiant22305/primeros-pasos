# MANEJO DE ERRORES (try, except) (VERSIÓN COMPLETA)

## 📑 Tabla de Contenidos
- [Introducción](#-introducción)
- [¿Qué es una excepción?](#-qué-es-una-excepción)
- [try y except](#try-y-except)
- [Capturar errores específicos](#capturar-errores-específicos)
- [Errores más comunes](#errores-más-comunes)
- [Varios except](#varios-except)
- [Capturar la excepción](#capturar-la-excepción)
- [else y finally](#else-y-finally)
- [Estructura completa](#estructura-completa)
- [Ejemplo real](#ejemplo-real)
- [raise: lanzar errores manualmente](#raise-lanzar-errores-manualmente)
- [Crear excepciones personalizadas](#crear-excepciones-personalizadas)
- [Buenas prácticas](#buenas-prácticas)
- [Patrón profesional](#patrón-profesional)
- [Errores comunes de principiantes](#errores-comunes-de-principiantes)
- [Mini proyecto: calculadora segura](#mini-proyecto-calculadora-segura)
- [Truco profesional: agrupar excepciones](#truco-profesional-agruparexcepciones)

---

## 📌 Introducción

Hasta ahora hemos escrito programas suponiendo que todo sale bien. En la vida real los usuarios pueden ingresar datos inesperados, dividir entre cero, o intentar abrir archivos que no existen. Si no manejamos esos casos, el programa se rompe. Para evitarlo existe el manejo de excepciones.

---

## ❓ ¿Qué es una excepción?

Una excepción es un error que ocurre durante la ejecución del programa. Por ejemplo:

```python
numero = int(input("Número: "))
```

Si el usuario escribe `hola`, Python lanza `ValueError` y el programa termina.

---

## try y except

`try` le dice a Python "intenta ejecutar este código". `except` dice "si ocurre un error, ejecuta esto".

Ejemplo sin manejo:

```python
numero = int(input("Número: "))
print(numero)
```

Con manejo básico:

```python
try:
    numero = int(input("Número: "))
    print(numero)
except:
    print("Debes ingresar un número")
```

Flujo mental: Python ejecuta `try`; si ocurre una excepción salta al `except`.

---

## Capturar errores específicos

Evita usar `except:` genérico porque captura todo. Mejor:

```python
try:
    numero = int(input("Número: "))
except ValueError:
    print("Eso no es un número")
```

---

## Errores más comunes

- ValueError — valor inválido (`int("hola")`)
- ZeroDivisionError — división por cero (`10 / 0`)
- IndexError — índice inexistente (`lista[10]`)
- KeyError — clave inexistente (`diccionario["edad"]`)
- TypeError — operación entre tipos incompatibles (`"5" + 5`)
- FileNotFoundError — archivo inexistente (`open("archivo.txt")`)

---

## Varios except

Puedes manejar distintos errores con bloques `except` separados:

```python
try:
    numero = int(input())
except ValueError:
    print("No es un número")
except TypeError:
    print("Tipo incorrecto")
```

---

## Capturar la excepción

Puedes guardar la excepción para examinarla o imprimirla:

```python
try:
    numero = int(input())
except ValueError as error:
    print(error)  # ayuda a depurar
```

---

## else y finally

- `else`: se ejecuta solo si NO hubo excepción.
- `finally`: se ejecuta siempre (hubo error o no).

```python
try:
    numero = int(input())
except ValueError:
    print("Error")
else:
    print("Todo salió bien")
finally:
    print("Fin del programa")
```

---

## Estructura completa

```python
try:
    codigo
except TipoError:
    manejar_error
else:
    si_todo_sale_bien
finally:
    siempre
```

---

## Ejemplo real

```python
try:
    a = int(input("Número 1: "))
    b = int(input("Número 2: "))
    resultado = a / b
except ValueError:
    print("Debes ingresar números")
except ZeroDivisionError:
    print("No puedes dividir por cero")
else:
    print(resultado)
finally:
    print("Proceso terminado")
```

---

## raise: lanzar errores manualmente

Puedes crear errores con `raise` para validar datos:

```python
edad = -5
if edad < 0:
    raise ValueError("La edad no puede ser negativa")
```

También dentro de funciones:

```python
def retirar(saldo, cantidad):
    if cantidad > saldo:
        raise ValueError("Fondos insuficientes")
    return saldo - cantidad
```

---

## Crear excepciones personalizadas

Nivel avanzado: definir clases de excepción propias.

```python
class EdadInvalidaError(Exception):
    pass

if edad < 0:
    raise EdadInvalidaError("Edad inválida")
```

No es obligatorio para empezar, pero existe.

---

## Buenas prácticas

- No uses `except:` genérico. Captura errores concretos.
- No ocultes errores con `except: pass` — silenciar excepciones dificulta depuración.
- Ofrece mensajes claros al usuario (`"Debes ingresar un número entero"`).

---

## Patrón profesional

Pedir datos hasta que sean correctos:

```python
while True:
    try:
        edad = int(input("Edad: "))
        break
    except ValueError:
        print("Ingrese un número válido")
```

Aparece mucho en programas reales.

---

## Errores comunes de principiantes

- Creer que `try` evita errores: solo los maneja.
- Usar `except:` para todo.
- Olvidar que `finally` siempre se ejecuta.
- Usar `except ValueError:` esperando capturar otros errores.

---

## Mini proyecto: Calculadora segura

```python
while True:
    try:
        a = float(input("Número 1: "))
        b = float(input("Número 2: "))
        print(a / b)
        break
    except ValueError:
        print("Debes ingresar números")
    except ZeroDivisionError:
        print("No puedes dividir por cero")
```

---

## Truco profesional: agrupar excepciones

Puedes capturar varios tipos en una sola cláusula:

```python
try:
    ...
except (ValueError, TypeError):
    print("Dato inválido")
```

Python capturará cualquiera de los dos.

---

**Listo.** Añadí `manejo_errores.md` con explicación completa sobre try/except, ejemplos, raise, buenas prácticas y un mini proyecto.
