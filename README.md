# Planetas en el universo


Nos piden armar parte del modelo de un juego galáctico que incluye a los planetas y a sus habitantes.

## Personas.

De cada **persona** deben poder obtenerse: los _recursos_, la _inteligencia_ y si es o no _destacado_. 
En principio, corresponden estas definiciones:
- la _inteligencia_ es de 12 para las personas de entre 20 y los 40 años, y de 8 para las otras.
- los _recursos_ es son las monedas que tiene una persona, inicialmente 20 para cualquier de ellas, pero puede ir variando con el tiempo.
- una persona _es destacada_ si tiene exactamente 25 años o más de 30 de recursos. 
Además, a las personas le puede pasar : 
- ganar o gastar monedas, en una cantidad dada.
- cumplir años

## Planetas.

De cada **planeta** se conocen los habitantes, que son personas. También se lleva el registro de las construcciones que se fueron efectuando en él.
 
Se tiene que poder obtener, para cada planeta
- la _delegación diplomática_, que está formada por todos los habitantes destacados y el habitante que tenga más recursos. Si llegara a coincidir que el habitante con más recursos fuera tambien destacado, mantiene su pertenencia a la delegación. 
- el _promedio de inteligencia_, que es el promedio de inteligencia de todos sus habitantes.
- si _valioso_: la condición es que el total del valor de todas las construcciones sea mayor a 100 unidades.

## Construcciones

Las construcciones que puede haber en un planeta son:
- _murallas_: su valor depende de su longitud, a razón de 10 monedas por unidad de medida.
- _museo_: su valor se calcula como su superficie cubierta multiplicada por un indice de importancia, que va de 1 a 5. 


### Pruebas
Considerar un planeta con cuatro personas como habitantes, dos murallas y un museo. Verificar que:
- la delegación diplomática está formada por tres de ellas
- el promedio de inteligencia es 10
- es valioso

Hacer que algunos de sus habitantes gane o gaste monedas y/o cumpla años y cambien algunas de las respuestas anteriores.


## Personas especiales

Además de estas definiciones que sirven para la generalidad de las personas se definen algunas personas con características especiales. En principio vamos a contemplar a productores y constructores.

De cada **productor** se registran las técnicas que conoce (inicialmente todos saben "cultivo"). 
Los _recursos_ de un productor es su cantidad de monedas, como para todas las personas, por la cantidad de técnicas que conoce.
Un productor _es destacado_ si cumple la condición común para todas las personas, o bien, conoce más de 5 técnicas.
 
Definir las siguientes acciones para los productores:
- _realizar_ una técnica durante una cantidad de tiempo: el efecto es ganar 3 monedas por cada unidad de tiempo, pero sólo en caso que conozca dicha técnica. P.ej. el efecto de realizar un cultivo durante un tiempo 5, es ganar 15 monedas. En caso que le pidan realizar uan tarea que no conoce, pierde una unidad de sus recursos básicos.
- _aprender_: hace que el productor conozca una nueva técnica.
- _trabajar_ durante una cantidad de tiempo en un planeta: implica realizar la última tecnica aprendida durante dicho tiempo, pero solo en caso que sea el planeta en que vive. 

De cada **constructor** se conoce la cantidad de construcciones realizadas y la region donde vive dentro del planeta. 
Los _recursos_ de un constructor son sus monedas, como toda persona, más 10 monedas por cada costrucción realizada.
Un constructor _es destacado_ si realizó más de 5 construcciones, independientemente de su edad. 

Sus acciones son:
- _trabajar_ una determinada cantidad de tiempo en un planeta: Construye una construcción en el planeta dado, sin importar que sea el que vive, de la siguiente manera:
	- si vive en la montaña, construye murallas. Su largo será igual a la mitad de las horas que trabaje.
	- si vive en la costa, construye museos. Su superficie será igual a la cantidad de horas que trabaje y con nivel 1.
	- si vive en la llanura, depende: si no es destacado, construye una muralla (igual largo que los que viven en la montaña), pero si es destacado contruye un museo (igual superficie que los que viven en la costa, pero con un nivel mayor, proporcional a sus recursos)
	- agregar una nueva región y que lo que construya dependa de la inteligencia del constructor

## La historia del planeta
- Hacer que todos los habitantes del planeta trabajen durante un determinado tiempo en su planeta
- Hacer que un planeta invada a otro y obligue a los habitantes del planeta invadido a trabajar para el propio planeta.

