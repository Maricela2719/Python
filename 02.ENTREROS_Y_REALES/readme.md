## En Python encontraremos dos tipos de datos:

* Tipos de datos básicos
* Tipos de datos complejos (Colecciones) 

## Tipos de datos básicos
Los tipos de datos básicos en Python son los siguientes:

* Número Entero (int)

Este tipo de dato se corresponde con números enteros, es decir, sin parte decimal.

* Número Decimal (float)

Este tipo de dato se corresponde con números reales con parte decimal. Cabe destacar que el separador decimal en Python es el punto (.) y no la coma (,).

* Caracter (chr)

Este tipo de dato se corresponde con un símbolo tipográfico, es decir, una letra, número, coma, espacio, signo de punutación, etc.

* Cadena de Texto (str)

Este tipo de datos se corresponde con una cadena de caracteres.

* Booleano (bool)

Este tipo de dato reconoce solamente dos valores: Verdadero (True) y Falso (False)

## Números enteros y reales.
### Números enteros
Son aquellos números positivos o negativos que no tienen decimales (además del cero).

En Python se pueden representar mediante el tipo int (de integer, entero) o el tipo long (largo). La única diferencia es que el tipo long permite almacenar números más grandes. Es aconsejable no utilizar el tipo long a menos que sea necesario, para no malgastar memoria.

El tipo int de Python se implementa a bajo nivel mediante un tipo long de C. Y dado que Python utiliza C por debajo, como C, y a diferencia de Java, el rango de los valores que puede representar depende de la plataforma. En la mayor parte de las máquinas el long de C se almacena utilizando 32 bits, es decir, mediante el uso de una variable de tipo int de Python podemos almacenar números de -231 a 231 - 1, o lo que es lo mismo, de -2.147.483.648 a 2.147.483.647. En plataformas de 64 bits, el rango es de - 9.223.372.036.854.775.808 hasta 9.223.372.036.854.775.807.

El tipo long de Python permite almacenar números de cualquier precisión, estando limitados solo por la memoria disponible en la máquina. Al asignar un número a una variable esta pasará a tener tipo int, a menos que el número sea tan grande como para requerir el uso del tipo long.

### Reales
Los números reales son los que tienen decimales. En Python se expresan mediante el tipo float.

En otros lenguajes de programación, como C, tenemos también el tipo double, similar a float pero de mayor precisión (double = doble precisión). Python, sin embargo, implementa su tipo float a bajo nivel mediante una variable de tipo double de C, es decir, utilizando 64 bits, luego en Python siempre se utiliza doble precisión, y en concreto se sigue el estándar IEEE 754: 1 bit para el signo, 11 para el exponente, y 52 para la mantisa. Esto significa que los valores que podemos representar van desde ±2,2250738585072020 x 10-308 hasta ±1,7976931348623157×10308.

La mayor parte de los lenguajes de programación siguen el mismo esquema para la representación interna. Pero como muchos sabréis esta tiene sus limitaciones, impuestas por el hardware.

Por eso desde Python 2.4 contamos también con un nuevo tipo Decimal, para el caso de que se necesite representar fracciones de forma más precisa. Sin embargo, este tipo está fuera del alcance de este taller, y sólo es necesario para el ámbito de la programación científica y otros relacionados. Para aplicaciones normales podemos utilizar el tipo float sin miedo, como ha venido haciéndose desde hace años, aunque teniendo en cuenta que los números en coma flotante no son precisos (ni en este ni en otros lenguajes de programación). Para representar un número real en Python se escribe primero la parte entera, seguido de un punto y por último la parte decimal

## Trabajar con números en Python

Más allá de la aritmética central, puedes hacer uso de otras operaciones con números. Es posible que debas realizar el redondeo o convertir cadenas en números.

En el escenario de este módulo, deseas aceptar la entrada de un usuario. La entrada será una cadena en lugar de un número, por lo que deberás convertirla en un número. Además, el usuario puede introducir valores que le den una respuesta negativa, que no querrás mostrar. Es posible que debas convertir la respuesta a su valor absoluto (Recordemos que el valor absoluto hace refencia al valor sin signos, es decir sin negativo). 

Afortunadamente, Python proporciona utilidades para estas operaciones.

### Convertir cadenas en números
Python admite dos tipos principales de números: enteros (o ``int``) y coma flotante (o ``float``). La diferencia clave entre los dos es la existencia de un punto decimal; los enteros son números enteros, mientras que los floats contienen un valor decimal.

Cuando conviertes cadenas en números, indicamos el tipo de número que deseamos crear. Debemos decidir si necesitamos un punto decimal. Se utiliza ``int`` para convertir a un número entero y ``float`` para convertir a un número de coma flotante.

```
demo_int = int('215')
print(demo_int)
```
*Salida: 215*

```
demo_float = float('215.3')
print(demo_float)
```
*Salida: 215.3*

Si utilizas un valor no válido para cualquiera de los dos ``int`` o ``float``, obtendrás un error.

### Valores absolutos

Un valor absoluto en matemáticas es el número no negativo sin su signo. El uso de un valor absoluto puede ser útil en diferentes situaciones, incluido nuestro ejemplo de buscar determinar la distancia entre dos planetas. Considera las siguientes matemáticas:

```
a = 39 - 16
b = 16 - 39
```
Observa que la diferencia entre las dos ecuaciones es que los números se invierten. Las respuestas son ``23`` y ``-23``, respectivamente. Cuando estás determinando la distancia entre dos planetas, el orden en el que ingresas los números no importa, porque la respuesta absoluta es la misma.

Convertimos el valor negativo en su valor absoluto utilizando ``abs``. Si realiza la misma operación utilizando ``abs`` (e imprimes las respuestas), notarás que se muestra ``23`` para ambas ecuaciones.

```
print(abs(39 - 16))
print(abs(16 - 39))
```
*Salida: 23, 23*

### Redondeo
La función de python incorporada llamada ``round`` también es útil. Usada para redondear al entero más cercano si el valor decimal ``.5`` es mayor o mayor, o hacia abajo si es menor que ``.5``. 

```
print(round(14.5))
```
*Salida: 15*

### Biblioteca Math
Python tiene bibliotecas para proporcionar operaciones y cálculos más avanzados. Una de las más comunes es la biblioteca ``math``. ``math`` te permite realizar el redondeo con ``floor`` y ``ceil``, proporcionar el valor de pi, y muchas otras operaciones. Veamos cómo usar esta biblioteca para redondear hacia arriba o hacia abajo.

El redondeo de números permite quitar la parte decimal de un flotador. Puedes elegir redondear siempre hacia arriba al número entero más cercano usando ``ceil``, o hacia abajo usando ``floor``.

```
from math import ceil, floor

round_up = ceil(12.5)
print(round_up)

round_down = floor(12.5)
print(round_down)
```
*Salida: 13, 12*


---

# VARIABLES
Asignar un valor a una variable en Python, para asignar un valor (un dato) a una variable se utiliza el operador de asignación =.

En la operación de asignación se ven involucradas tres partes:

El operador de asignación = Un identificador o nombre de variable, a la izquierda del operador Un literal, una expresión, una llamada a una función o una combinación de todos ellos a la derecha del operador de asignación

          # Asigna a la variable <a> el valor 1
          a = 1

          # Asigna a la variable <a> el resultado de la expresión 3 * 4
          a = 3 * 4

          # Asigna a la variable <a> la cadena de caracteres 'Pythonista'
          a = 'Pythonista'
        
### Un programa Python
Para crear un programa en Python, debes almacenarlo en un archivo. El archivo debe tener la extensión .py.

La idea de un programa es hacer algo, llevar a cabo una tarea. Para que el programa haga algo, debe agregar instrucciones de código que realicen instrucciones. Una instrucción podría imprimir algún texto o calcular algo, por ejemplo. Un programa de ejemplo puede tener un aspecto similar al siguiente:

      # program.py
          sum = 1 + 2
          print(sum)
     
salida
         
       3

### Ejecutar un programa

Supongamos que has creado un programa que consta de instrucciones. Para ejecutarlo hay que invocar el programa ejecutable de Python, seguido del nombre del programa. Aquí hay un ejemplo de tal invocación:

     python3 program.py

### La función print()
Una de las primeras cosas que es probable que hagas es imprimir en una consola. Una consola es una aplicación de línea de comandos que te permite interactuar con el sistema operativo. En la consola, puedes ejecutar comandos y programas. También puedes ingresar información y mostrar información como texto en la pantalla.

Para escribir información en la consola, puedes utilizar la función e implementarla como función principal. Debido a que es una función central, tendrás acceso a ella si Python está instalado. Para usarla dale un argumento: print()

      print('Hola usuarios PILARES')
      Hola usuarios PILARES
      suma = 5 + 5 
          producto = suma * 2
          print(producto)
          
salida

       20
       
¿Cómo sabes qué tipo tiene algo? Si ve los datos asignados a la variable como se muestra en el código siguiente, puede detectarlos:

        distancia_al_metro = 8.346 # Parece un decimal flotante

        La otra forma es usar la función:type()

        type(distancia_a_metro)

        distancia_al_metro = 8.346
        type(distancia_al_metro)
        
salida

        float

### Recopilar información
Puede codificarlo para que el programa le diga al usuario que ingrese información. Guarde los datos introducidos en el programa y, a continuación, actúe en consecuencia.

Para capturar información del usuario, utilice la función input()

          print("Bienvenido al programa de bienvenida") 
          name = input("Introduzca su nombre ") 
          print("Saludos: " + name)


