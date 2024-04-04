# Beatrix-statistics

*Beatrix-statistics* es un proyecto de Python para el área de estadística que proporciona una variedad de herramientas y funciones para el análisis de datos. Este proyecto se desarrolló con el objetivo de programar lo visto en clases y llevarlo a un nivel funcional y fácil de usar para las tareas comunes de estadística.

## Funcionalidades principales

- **Detectar tipos de variables:** Identifica automáticamente variables cualitativas y cuantitativas en conjuntos de datos.
- **Calcular estadísticas descriptivas:** Calcula la media, mediana, moda, varianza, desviación estándar, percentiles, cuartiles y otros estadísticos básicos.
- **Generar tablas y gráficos:** Produce tablas de frecuencias, histogramas, gráficos de barras, gráficos de pastel y más para visualizar datos.
- **Aplicar teoremas estadísticos:** Utiliza la regla empírica, el teorema de Chebyshev y otros conceptos estadísticos para analizar conjuntos de datos.

## Descripcion de funcionalidades
**Detectar tipos de variables:** Para detectar que las variables son cuantitativas o cualitativas simplemente se pregunta por consola si se van a ingresar datos de tipo numérico o de tipo texto:
~~~
desicion= int(input("Que tipo de datos va a ingresar?  1.Numericos  2. De texto o nombres\n"))
~~~
De esta manera si los datos son numéricos entonces los datos son cuantitativos y si son de tipo texto seran cualitativos.
Esto es útil para saber si se puede o no calcular la mediana, media, cuartiles, etc, ya que si son de tipo texto no se pueden hacer esos cálculos.
~~~
Cuartil 1: No es posible definir un dato como cuartil, los datos son de tipo texto
Cuartil 2: No es posible definir un dato como cuartil, los datos son de tipo texto
Cuartil 3: No es posible definir un dato como cuartil, los datos son de tipo texto
Cuartil 4: No es posible definir un dato como cuartil, los datos son de tipo texto
~~~
**Calcular estadisticas descriptivas:**
Para el calculo de la media,mediana, moda, y los cuartiles 1,2,3,y 4, se tiene una clase 'Controlador_vista_medidas_de_tendencia_central' que se encarga de controlar la interaccion entre la vista y el modelo de datos permitiendo la presentacion del modelo de las medidas de tendencia central.
Para el calculo del rango, rango intercuartlílico, media muestral, varianza , desviacion estandar, los puntos z y el porcentaje basado en el teorema de Chevyshev se tiene la clase 'Controlador_vista_medidas_de_variabilidad' la cual tiene los metodos necesarios para hacer cada uno de los calculos y mostrarlos.
## Explicación general del código
Para la codificación de este proyecto se optó por usar el paradigma orientado a objetos(POO) y la arquitectura MVC(Modelo vista controlador) por lo que se tienen las *clases modelo*:
~~~
Cuadro_de_frecuencias_intervalos
Cuadro_de_frecuencias_datos_individuales
Medidas_de_tendencia_central
Medidas_de_variabilidad
~~~
Que se encargan de obtener y actualizar los datos mediante metodos get y set.

Las *clases vista*: 
~~~
Vista_cuadro_de_frecuencias_intervalos
Vista_cuadro_de_frecuencias
Vista_medidas_de_tendencia_central
Vista_medidas_de_variabilidad
Vista_seleccion_tipo_cuadro_de_frecuencias
~~~
Que básicamente se encargan de lo que es la interacción con el usuario y de mostrar los datos de manera estética comprensible y organizada.
Las *clases controlador*:
~~~
Controlador_vista_cuadro_de_frecuencias_intervalos
Controlador_vista_cuadro_de_frecuencias
Controlador_vista_medidas_de_tendencia_central
Controlador_vista_medidas_de_variabilidad
Controlador_vista_seleccion_tipo_cuadro_de_frecuencias
~~~
Que son las clases que se encargan de ser las intermediarias entre la vista y el modelo, son las clases que mas lógica, tienen dado que son las que hacen los calculos más grandes.
y claramente un *metodo main* para que se encargue de hacer el llamado a las clases y se pueda ejecutar el programa.
~~~
def main(): 
    #Creacion del objeto Vista_seleccion_tipo_cuadro_de_frecuencias para poder iniciar el programa 
    vistaa = Vista_seleccion_tipo_cuadro_de_frecuencias()
    vistaa.vista_seleccion_tipo_de_datos_a_ingresar()

main()
~~~
# Ejemplos Prácticos
Vamos a ver un ejemplo de la funcionalidad del programa, para ellos usaremos los siguientes datos:

***sueldo mensual inicial***: 3450 3550 3650 3480 3355 3310 3490 3730 3540 3925 3520 3480
Estos datos fueron tomados de la primer parte de la guia 'Medidas de tendencia central'
## Paso 1 : Ejecutar el programa
Al ejecutar el programa aparecera lo siguiente:
~~~
Por favor ingrese una opción:
1. Ingresar datos para analisis individual
2. Ingresar datos para analizarlos en intérvalos
~~~
## paso 2 : Escoger una de las opciones
En este caso escogeremos la opcion 1, que nos pide otra opción:
~~~
Que tipo de datos va a ingresar?  1.Numericos  2. De texto o nombres
~~~
Para el cual escogeremos la opción 1
## paso 3 : rellenar
Ahora simplemente llenamos todos los datos, tal que asi:
~~~
Por favor ingrese los datos que desee analizar:  3450

Desea agregar otro dato? 1.Si  2.No
1
Por favor ingrese los datos que desee analizar:  3550

Desea agregar otro dato? 1.Si  2.No
1
Por favor ingrese los datos que desee analizar:  3650
.
.
.
.
Por favor ingrese los datos que desee analizar:  3480

Desea agregar otro dato? 1.Si  2.No
2
~~~
Y listo, automaticamente hace todos los calculos  y nos muestra los resultados.
Solo es cuestion de terminar de escribir las opciones que nos pide por consola:
~~~
Desea agregar otro dato? 1.Si  2.No
2
Datos |  F   |   Fr   |   FrA  |   F%   |   F%A  |   F°  |
 3310        1     0.08     0.08      8.0     8.0   28.8
 3355        1     0.08     0.16      8.0     16.0   28.8
 3450        1     0.08     0.24      8.0     24.0   28.8
 3480        2     0.17     0.41      17.0     41.0   61.2
 3490        1     0.08     0.49      8.0     49.0   28.8
 3520        1     0.08     0.57      8.0     57.0   28.8
 3540        1     0.08     0.65      8.0     65.0   28.8
 3550        1     0.08     0.73      8.0     73.0   28.8
 3650        1     0.08     0.81      8.0     81.0   28.8
 3730        1     0.08     0.89      8.0     89.0   28.8
 3925        1     0.08     0.97      8.0     97.0   28.8

Desea conocer la ubicación de algún dato con base a su porcentaje?: 1.Si  2.No
: 2

Media: 3540.0
Mediana: 3505.0
Moda: La moda es 3480 con 2 repeticiones

Cuartil 1: 3465.0
Cuartil 2: 3505.0
Cuartil 3: 3600.0
Cuartil 4: 3925

Datos_en_el_cuartil_1: 3310, 3355, 3450,
Datos_en_el_cuartil_2: 3480, 3480, 3490,
Datos_en_el_cuartil_3: 3520, 3540, 3550,
Datos_en_el_cuartil_4: 3650, 3730, 3925,

El dato que se encuentra en ese percentil es: No se ingresó ningun percentil
¿Que tipo de varianza desea que se emplee? 1.Poblacional  2.Muestral
2
Por favor ingrese el numero menor que desee que se analice con el teorema de chevyshev: 3310
Por favor ingrese el numero mayor que desee que se analice con el teorema de chevyshev: 3925

¿Desea conocer a cuantas desviaciones estandar de la media muestral se encuentra algún numero en específico?  1.Si  2.No
2

El rango es: 615
El rango intercuartilico es: 135.0

|  Xi  |  media_muestral(Xˉ) | (Xi - Xˉ )^2 |
   3310                3540.0            52900.0
   3355                3540.0            34225.0
   3450                3540.0            8100.0
   3480                3540.0            3600.0
   3480                3540.0            3600.0
   3490                3540.0            2500.0
   3520                3540.0            400.0
   3540                3540.0            0.0
   3550                3540.0            100.0
   3650                3540.0            12100.0
   3730                3540.0            36100.0
   3925                3540.0            148225.0

La varianza muestral es de: 27440.91
La desviacion estandar es de: 165.65
 el porcentaje en el que se encuentra el rango ingresado anteriormente segun la media muestral es de: 65
~~~
y como se puede observar los resultados de los cuartiles y de la media concuerddan con los de la guia.
