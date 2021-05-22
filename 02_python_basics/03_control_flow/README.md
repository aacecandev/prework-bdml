---
title: Control Flow
description: Pensando el flujo y la estructura de nuestros programas en Python
weight: 30
---

# Control Flow

En la sección anterior sobre los tipos básicos de Python, hemos visto que cada tipo tiene sus particularidades y sus proprias funciones. En la parte práctica, además de eso, hemos probado también los condicionales y los bucles. En esta sección pensaremos más en detalle sobre la importancia de estas herramientas.

## Control Flow

En computación, cuando hablamos de `Control Flow`, estamos hablando de la manera y del orden que se ejecuta nuestro programa. Todo este proceso está basado en los bucles y los condicionales.

Hay un antiguo chiste de programación en el cual dice su pareja a un programador:

\- Ve al supermercado, trae una caja de cervezas y si hay huevos, trae seis.

En media hora vuelve el programador, cargando seis cajas de cerveza y nada más. Le indaga su pareja:

\- ¿Y eso?

\- Había huevos

![](img/beer.jpeg)

Bromas aparte, lo que nos ilustra esta anécdota es un claro problema de `Control Flow`, donde, por lo menos en la percepción del programador, el condicional "hay huevos" hace referencia a la instrucción equivocada "trae seis (cajas de cerveza)" y no a la instrucción correcta "trae seis (huevos)".

Aunque podamos fácilmente evitar ese tipo de ambigüedad en la programación, también podemos encontrarnos con problemas de ese tipo y es importante que prestemos siempre mucha atención las estructuras de control (`if,for,while`) para lograr el mejor funcionamiento de nuestro programa, incluso en el sentido de protegerle de situaciones inesperadas (un valor fuera del normal, un dato mal insertado). También es importante, según avancemos, para que podamos programar con mejor control de los recursos.

## Guided Example

Imaginemos el siguiente problema: tenemos una lista aleatoria de 1000 números y queremos encontrar de entre ellos el número más grande que además sea un palíndromo, i.e.: que se lea igual en ambos sentidos, e.g.: 2002, 1991, etc.

Podemos empezar recorriendo los números de la lista y separando solo aquellos que cumplan la condición de palíndromo. De la lista resultante, el mayor será nuestro resultado.

Pero esa no es la única solución. Podríamos, al contrario, primero ordenar todos los números de la lista original (de manera descendiente) y empezar por la lista ordenada a buscar palíndromos, al primero que encontráramos, paramos de buscar pues ya tendremos la respuesta.

Y tú, ¿cómo procederías?

Ambas respuestas son válidad y correctas, pero como cada operación tarda un intervalo de tiempo diferente: en este caso, la segunda opción tiende a ser más rápida pues ejecuta menos operaciones.

En el `punto 2.1` del Google Colab, encontrarás el código que ejecuta ambos abordajes con una función de los jupyter notebooks para medir el tiempo de ejecución. ¿Está de acuerdo con lo esperado?

Obviamente, no podemos hablar de optimización o eficiencia de un programa que no funciona. Nuestra prioridad debe ser siempre el funcionamiento. Pero si tuviéramos nuestro programa en un servidor cloud y pagáramos por tiempo de procesamiento (práctica bastante común), todos elegiríamos lo mismo. 😂

Lo mismo se puede decir de la manera en la que estructuramos los datos. Si seguimos una buena organización, con claridad y usando los tipos de datos adecuados, tenemos más posibilidades de que nuestro programa funcione y de la mejor manera. Sobre todo cuando nuestro trabajo depende de otras personas y otros programadores, `una estructura clara es esencial`.

¡Revisamos las estructuras de control y partimos a los ejercicios!

## Conditionals

Los condicionales son herramienta esencial para el control de un programa, pues deciden si determinadas operaciones se ejecutan o no. O, de entre un grupo de posibilidades, cuál de ellas se ejecutará.

> ### if
>
> El `if` es el condicional más básico, tiene que ir seguido de alguna condición que se verificará y `:`. El bloque de código que esté sujeto a esa condición debe ser un bloque de código identado.
>
> ```Python
> x = 7
> if x < 10:
>    print("Less than ten")
> ```
>
> Output:
>
> ```
> Less than ten
> ```
>
> `Ifs` seguidos no se afectan mutuamente, i.e.: si tenemos más de un if seguidos, se verifica separadamente la condición sobre cada uno.
>
> ```Python
> x = 7
> if x < 10:
>    print("Less than ten")
> if x < 8:
>    print("Less than eight")
> if x < 6:
>    print("Less than six")
> ```
>
> Output:
>
> ```
> Less than ten
> Less than eight
> ```

> ### else
>
> Si queremos verificar una condición mutuamente excluyente, debemos combinar el bloque `if` con un bloque `else`. De esta manera uno de los dos bloques siempre se ejecutará dependiendo del resultado de la condición verificada. En el caso de que haya más de un bloque `if`, el `else` se ejuejecutarácuta solamente en el caso de que la condición del if inmediatamente anterior sea `False`.
>
> ```Python
> x = 7
> if type(x) == float:
>    print("X is a float.")
> if type(x) == int:
>    print(f"x**2 = {x**2}")
> else:
>    print("Not a valid type, please use int.")
> ```
>
> Output:
>
> ```
> x**2 = 49
> ```
>
> En ese caso la primera condición no se cumple, por lo tanto no se ejecuta. Y como la segunda se cumple y ejecuta, el bloque else se salta. Sería diferente en el caso:
>
> ```Python
> x = 7.5
> if type(x) == float:
>    print("X is a float.")
> if type(x) == int:
>    print(f"x**2 = {x**2}")
> else:
>    print("Not a valid type, please use int.")
> ```
>
> Output:
>
> ```
> X is a float.
> Not a valid type, please use int.
> ```
>
> La primera condición se cumple y aun así se ejecuta el else, pues ese solo se referia al segundo if.

> ### elif
>
> Para utilizar más de una condición mutuamente excluyente, debemos utilizar el bloque `elif` (else if).
> Esa condición solo se verificará cuando las condiciones anteriores fallen. Podemos tener una secuencia de `if..elif..elif..elif` de cualquier longitud y pueden o no tener un `else`.
>
> ```Python
> x = 7.5
> if type(x) == int:
>    print(f"x**2 = {x**2}")
> elif type(x) == float:
>    print("X is a float. Using only integer part.")
>    print(f"x**2 = {int(x)**2}")
> else:
>    print("Not a valid type, please use int or float")
> ```
>
> Output:
>
> ```
> X is a float. Using only integer part.
> x**2 = 49
> ```

## Loops

La otra herramienta que utilizamos para controlar el flujo del programa son los bucles, que tratan de cuidar de las repeticiones de bloques de código. Son de dos tipos:

> ### for
>
> El bucle `for` es cuando iteramos (pasamos por los valores uno a uno) por un objeto iterable. Ese objeto puede ser una lista, tupla, string, la función range y otra serie de objetos que se llaman iterables.
>
> En ese tipo de bucle sabemos a priori cuantas veces se ejecutará el bucle (salvo en el caso de que sea interrumpido) y se repetirá tantas veces cuanto sea la longitud del iterable, i.e.: Si iteramos una lista de 10 elementos, el código se repetirá 10 veces.
>
> ```Python
> x = 0
> for i in range(11):
>    x += i
> print(x)
> ```
>
> Output:
>
> ```
> 55
> ```

> ### while
>
> La otra posibilidad de bucle es el bucle `while`, que no se basa en una secuencia de valores sino que en una condición que se verificará antes de la ejecución del bloque. Por lo tanto, en el caso de los bucles while, la variable de la condición debe cambiar en algun momento dentro del código. En caso contrario, el código del bucle se ejecutará eternamente en un `loop infinito`.
>
> ```Python
> x = 0
> i = 1
> while i < 11:
>    x += i
>    i += 1
> print(x)
> ```
>
> Output:
>
> ```
> 55
> ```

> ### break
>
> En el caso de que queramos interrumpir un bucle antes de que llegue a su fin, debemos usar la palabra `break`. Cuando la ejecución del programa llegue al `break`, el bucle terminará y avanzaremos a la siguiente línea de código inmediatamente posterior al loop.
>
> En el caso de bucles anidados (uno dentro del otro), el `break` solo interrumpirá el que inmediatamente le contenga.
>
> ```Python
> x = 0
> for i in range(11):
>    x += i
>    if i == 3:
>        break
>    print(x, "After the 'break'")
> print(x)
> ```
>
> Output:
>
> ```
> 0 After the 'break'
> 1 After the 'break'
> 3 After the 'break'
> 6
> ```

En el colab `Python_basics.ipynb`, encontrarás 3 ejercícios más de nuestra preparación en Python.

```
CODE. ENJOY. REPEAT
```
