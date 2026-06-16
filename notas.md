# TEORIA PYTHON

## 📋 VARIABLES
# 1. ¿Qué es una variable?
Imagina que tienes varias cajas en tu habitación.

- Una caja guarda dinero.
- Otra guarda cuadernos.
- Otra guarda ropa.

Para saber qué hay en cada una, les pones una etiqueta.
dinero = 50000

Aquí: dinero es la etiqueta de la caja (nombre de la variable).
50000 es lo que guardamos dentro.

Visualmente:
┌─────────┐
│ dinero  │
├─────────┤
│ 50000   │
└─────────┘
Una variable es simplemente un espacio en memoria que almacena información.

# 2. ¿Por qué existen?
Porque sería imposible trabajar escribiendo directamente todos los valores. Por ejemplo:
Sin variables:
print(50000 + 20000)

Con variables:
salario = 50000
bono = 20000
print(salario + bono)

Ahora el código tiene sentido para cualquier persona que lo lea.

# 3. ¿Cómo crear una variable?

La sintaxis es:
nombre_variable = valor

Ejemplos:
nombre = "Cristian"
edad = 20
altura = 1.75
es_estudiante = True

# ""IMPORTANTE"" El signo (=) NO significa igualdad
Este es uno de los errores más comunes.

En matemáticas:
x = 5
significa:
x es igual a 5

En Python:
x = 5
significa:
Guarda 5 dentro de x.

# 4. Reasignación

Una variable puede cambiar de valor.
dinero = 100
dinero = 200
print(dinero)

Resultado:
200
El 100 se reemplaza por 200.

# 5. Reglas para nombrar variables
Correcto
nombre = "Cristian"
edad = 20
numero_estudiantes = 35

Incorrecto
2nombre = "Cristian"
No puede empezar por número.

mi nombre = "Cristian"
No puede contener espacios.

class = 10
No puede usar palabras reservadas de Python.

Estilo profesional (muy importante)
Muchos principiantes escriben así:

A = 20
B = 30
C = A + B

Funciona Pero es mala práctica.
Mejor:
precio_producto = 20
precio_envio = 30
precio_total = precio_producto + precio_envio

Un programador pasa más tiempo leyendo código que escribiéndolo, por eso los nombres deben explicar qué contienen.

snake_case
Python usa una convención llamada snake_case.

Correcto:
precio_total
nombre_completo
cantidad_estudiantes

Incorrecto:
PrecioTotal
precioTotal
PRECIOTOTAL

Cuando llegues a trabajar en proyectos grandes esto será obligatorio.

## Tipos de datos

# 1. Una variable puede guardar distintos tipos de información.

-Texto (str)
nombre = "Cristian"
La palabra debe ir entre comillas.

-Enteros (int)
edad = 20
cantidad = 150

-Decimales (float)
altura = 1.75
precio = 99.99

-Booleanos (bool)
Solo tienen dos valores:
True
False

Ejemplo:
es_mayor_de_edad = True
tiene_descuento = False

# 2. Ver el tipo de una variable

La función: type() sirve para saber qué tipo de dato contiene.
Ejemplo:

edad = 20
print(type(edad))

Resultado:
<class 'int'>

# 3. Mostrar variables

Usamos: print()
Ejemplo:
nombre = "Cristian"
print(nombre)

Resultado:
Cristian
Mostrar texto y variables

Mucha gente hace esto:

nombre = "Cristian"

print("Hola " + nombre)

Funciona.

Pero hoy se usa mucho más:

nombre = "Cristian"

print(f"Hola {nombre}")

Resultado:

Hola Cristian

Esto se llama f-string y la vas a usar muchísimo.

Funciones importantes que debes aprender desde ya
print()

Muestra información.

print("Hola")
type()

Muestra el tipo de dato.

print(type(20))
len()

Cuenta elementos.

nombre = "Cristian"

print(len(nombre))

Resultado:

8
input()

Permite que el usuario escriba información.

nombre = input("Escribe tu nombre: ")

print(nombre)

Si escribes:

Cristian

Python guarda ese valor en la variable.

Ejemplo real

Supongamos que queremos registrar un estudiante.

nombre = "Cristian"
edad = 20
promedio = 4.5
es_becado = True

print(f"Nombre: {nombre}")
print(f"Edad: {edad}")
print(f"Promedio: {promedio}")
print(f"Becado: {es_becado}")

Salida:

Nombre: Cristian
Edad: 20
Promedio: 4.5
Becado: True
Errores típicos de principiantes
1. Olvidar las comillas

Mal:

nombre = Cristian

Bien:

nombre = "Cristian"
2. Confundir texto con número
edad = "20"

Esto es texto, no número.

edad = 20

Esto sí es un entero.

3. Usar nombres sin sentido

Mal:

a = 100

b = 200

c = a + b

Bien:

precio_producto = 100

precio_envio = 200

precio_total = precio_producto + precio_envio
Lo que debes recordar de esta lección

Una variable:

Guarda información.
Tiene un nombre.
Puede cambiar de valor.
Debe tener nombres descriptivos.
Puede almacenar texto, números o booleanos.

Las funciones que debes dominar desde ya:

print()
type()
len()
input()

Y la herramienta más importante para mostrar datos:

f"Texto {variable}"



