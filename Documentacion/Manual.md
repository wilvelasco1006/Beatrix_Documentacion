# Beatrix-statistics

*Beatrix-statistics* es un proyecto de Python para el área de estadística que proporciona una variedad de herramientas y funciones para el análisis de datos. Este proyecto se desarrolló con el objetivo de programar lo visto en clases y llevarlo a un nivel funcional y fácil de usar para las tareas comunes de estadística.

## Funcionalidades principales

- **Detectar tipos de variables:** Identifica automáticamente variables cualitativas y cuantitativas en conjuntos de datos.
- **Calcular estadísticas descriptivas:** Calcula la media, mediana, moda, varianza, desviación estándar, percentiles, cuartiles y otros estadísticos básicos.
- **Generar tablas y gráficos:** Produce tablas de frecuencias, histogramas, gráficos de barras, gráficos de pastel y más para visualizar datos.
- **Aplicar teoremas estadísticos:** Utiliza la regla empírica, el teorema de Chebyshev y otros conceptos estadísticos para analizar conjuntos de datos.

## Descripcion de funcionalidades
**Detectar tipos de variables:** Para detectar que las variables son cuantitativas o cualitativas simplemente se pregunta por consola si se van a ingresar datos de tipo numérico o de tipo texto:
```python
desicion= int(input("Que tipo de datos va a ingresar?  1.Numericos  2. De texto o nombres\n"))
```
De esta manera si los datos son numéricos entonces los datos son cuantitativos y si son de tipo texto seran cualitativos.
Esto es útil para saber si se puede o no calcular la mediana, media, cuartiles, etc, ya que si son de tipo texto no se pueden hacer esos cálculos.

saldrian estos mensajes:
```bash
Cuartil 1: No es posible definir un dato como cuartil, los datos son de tipo texto
Cuartil 2: No es posible definir un dato como cuartil, los datos son de tipo texto
Cuartil 3: No es posible definir un dato como cuartil, los datos son de tipo texto
Cuartil 4: No es posible definir un dato como cuartil, los datos son de tipo texto
```
**Calcular estadisticas descriptivas:**
Para el calculo de la media,mediana, moda, y los cuartiles 1,2,3,y 4, se tiene una clase `Controlador_vista_medidas_de_tendencia_central` que se encarga de controlar la interaccion entre la vista y el modelo de datos permitiendo la presentacion del modelo de las medidas de tendencia central.
Para el cálculo del rango, rango intercuartlílico, media muestral, varianza , desviacion estandar, los puntos z y el porcentaje basado en el teorema de Chevyshev se tiene la clase `Controlador_vista_medidas_de_variabilidad` la cual tiene los métodos necesarios para hacer cada uno de los cálculos y mostrarlos.
## Explicación general del código
Para la codificación de este proyecto se optó por usar el paradigma orientado a objetos(POO) y la arquitectura MVC(Modelo vista controlador) por lo que se tienen las *clases modelo*:
```
Cuadro_de_frecuencias_intervalos 
Cuadro_de_frecuencias_datos_individuales
Medidas_de_tendencia_central
Medidas_de_variabilidad
```
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
Que son las clases que se encargan de ser las intermediarias entre la vista y el modelo, son las clases que mas lógica tienen dado que son las que hacen los calculos más grandes.
Y claramente un *metodo main* para que se encargue de hacer el llamado a las clases y se pueda ejecutar el programa.
```python
def main(): 
    #Creacion del objeto Vista_seleccion_tipo_cuadro_de_frecuencias para poder iniciar el programa 
    vistaa = Vista_seleccion_tipo_cuadro_de_frecuencias()
    vistaa.vista_seleccion_tipo_de_datos_a_ingresar()

main()
```
# Ejemplos Prácticos
Veamos un ejemplo de la funcionalidad del programa, para ellos usaremos los siguientes datos:

| #   | Sueldo Mensual Inicial |
|-----|------------------------|
|  1  | 3450                   |
|  2  | 3550                   |
|  3  | 3650                   |
|  4  | 3480                   |
|  5  | 3355                   |
|  6  | 3310                   |
|  7  | 3490                   |
|  8  | 3730                   |
|  9  | 3540                   |
| 10  | 3925                   |
| 11  | 3520                   |
| 12  | 3480                   |

Estos datos fueron tomados de la primer parte de la guia ```Medidas de tendencia central```
## Paso 1 : Ejecutar el programa
Al ejecutar el programa aparecera lo siguiente:
```bash
  _______________________________________________________________________________________________  
 |                                                                                               | 
 |                \     /¯\     /  |¯¯¯   |    |¯¯¯  |¯¯¯|   /¯\   /¯\   |¯¯¯                    | 
 |                 \   /   \   /   |---   |    |     |   |  /   \_/   \  |---                    | 
 |                  \_/     \_/    |___   |___ |___  |___| /           \ |___                    | 
 |                                                                                               | 
 |                                                                                               | 
 |                                       ¯¯¯|¯¯¯ |¯¯¯|                                           | 
 |                                          |    |   |                                           | 
 |                                          |    |___|                                           | 
 |                                                                                               | 
 |                                                                                               | 
 |                         |¯¯¯|  |¯¯¯    /¯\   ¯¯¯|¯¯¯ |¯¯¯|  ¯¯¯|¯¯¯   \  /                    | 
 |                         |---|  |---   / _ \     |    |___|     |       \                      | 
 |                         |___|  |___  /     \    |    |  \   ___|___   /  \                    | 
 |                                                                                               | 
 | --------------------------------------------------------------------------------------------- | 
 |                                                                                               | 
 |                                                                                               | 
 |                               Ingrese el numero 1 para iniciar                                | 
 |                                                                                               | 
 |                                                                                               | 
  ¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯  
```
```bash
1
Bienvenido a la sección para crear una tabla de frecuencias

Por favor ingrese una opción:
1. Ingresar datos para analisis individual
2. Ingresar datos para analizarlos en intérvalos
```
## paso 2 : Escoger una de las opciones
En este caso escogeremos la opcion 1, que nos pide otra opción:
```bash
Que tipo de datos va a ingresar?  1.Numericos  2. De texto o nombres
```
Para el cual escogeremos la opción 1
## paso 3 : Ingresar los datos 
Ahora simplemente llenamos todos los datos que queramos, para el ejemplo, los datos anteriormente nombrados, tal que asi:
```bash
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
```
Y listo, automáticamente, el programa hace todos los cálculos  y nos muestra los resultados.
Solo es cuestión de terminar de escribir las opciones que nos pide por consola:
```bash
Desea agregar otro dato? 1.Si  2.No
2
  __________________________________________________________________________________________  
 |            |            |            |            |            |            |            | 
 |  INTERVALO | FRECUENCIA |     FR     |     FRA    |     FRP    |     FRPA   |      F°    | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |    3310    |      1     |     0.08   |     0.08   |      8.0   |      8.0   |     28.8   | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |    3355    |      1     |     0.08   |     0.16   |      8.0   |     16.0   |     28.8   | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |    3450    |      1     |     0.08   |     0.24   |      8.0   |     24.0   |     28.8   | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |    3480    |      2     |     0.17   |     0.41   |     17.0   |     41.0   |     61.2   | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |    3490    |      1     |     0.08   |     0.49   |      8.0   |     49.0   |     28.8   | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |    3520    |      1     |     0.08   |     0.57   |      8.0   |     57.0   |     28.8   | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |    3540    |      1     |     0.08   |     0.65   |      8.0   |     65.0   |     28.8   | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |    3550    |      1     |     0.08   |     0.73   |      8.0   |     73.0   |     28.8   | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |    3650    |      1     |     0.08   |     0.81   |      8.0   |     81.0   |     28.8   | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |    3730    |      1     |     0.08   |     0.89   |      8.0   |     89.0   |     28.8   | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |    3925    |      1     |     0.08   |     0.97   |      8.0   |     97.0   |     28.8   | 
  ------------------------------------------------------------------------------------------  
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
```
y como se puede observar los resultados de los cuartiles y de la media concuerdan con los que se plantean en la guía.

Ahora veamos un ejemplo con datos mediante intervalos, el diagrama de caja y veamos el teorema Chevyshev siguiendo las mismas instrucciones que al principio.
```bash
  _______________________________________________________________________________________________  
 |                                                                                               | 
 |                \     /¯\     /  |¯¯¯   |    |¯¯¯  |¯¯¯|   /¯\   /¯\   |¯¯¯                    | 
 |                 \   /   \   /   |---   |    |     |   |  /   \_/   \  |---                    | 
 |                  \_/     \_/    |___   |___ |___  |___| /           \ |___                    | 
 |                                                                                               | 
 |                                                                                               | 
 |                                       ¯¯¯|¯¯¯ |¯¯¯|                                           | 
 |                                          |    |   |                                           | 
 |                                          |    |___|                                           | 
 |                                                                                               | 
 |                                                                                               | 
 |                         |¯¯¯|  |¯¯¯    /¯\   ¯¯¯|¯¯¯ |¯¯¯|  ¯¯¯|¯¯¯   \  /                    | 
 |                         |---|  |---   / _ \     |    |___|     |       \                      | 
 |                         |___|  |___  /     \    |    |  \   ___|___   /  \                    | 
 |                                                                                               | 
 | --------------------------------------------------------------------------------------------- | 
 |                                                                                               | 
 |                                                                                               | 
 |                               Ingrese el numero 1 para iniciar                                | 
 |                                                                                               | 
 |                                                                                               | 
  ¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯  
1
Bienvenido a la sección para crear una tabla de frecuencias

Por favor ingrese una opción:
1. Ingresar datos para analisis individual
2. Ingresar datos para analizarlos en intérvalos

2
Que tipo de numeros va a ingresar?  1.Enteros  2.Decimales o reales
1
Por favor ingrese los datos que desee analizar:  23

Desea agregar otro dato? 1.Si  2.No
1
Por favor ingrese los datos que desee analizar:  32

Desea agregar otro dato? 1.Si  2.No
1
Por favor ingrese los datos que desee analizar:  7

Desea agregar otro dato? 1.Si  2.No
1
Por favor ingrese los datos que desee analizar:  23

Desea agregar otro dato? 1.Si  2.No
1
Por favor ingrese los datos que desee analizar:  8

Desea agregar otro dato? 1.Si  2.No
1
Por favor ingrese los datos que desee analizar:  9

Desea agregar otro dato? 1.Si  2.No
1
Por favor ingrese los datos que desee analizar:  32

Desea agregar otro dato? 1.Si  2.No
2
Por favor ingrese la cantidad de intervalos para evaluar los datos(de 5 a 10): 5
  __________________________________________________________________________________________  
 |            |            |            |            |            |            |            | 
 |  INTERVALO | FRECUENCIA |     FR     |     FRA    |     FRP    |     FRPA   |      F°    | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |   (6-11)   |      3     |     0.43   |     0.43   |     43.0   |     43.0   |     154.8  | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |  (12-17)   |      0     |      0.0   |     0.43   |      0.0   |     43.0   |     0.0    | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |  (18-23)   |      2     |     0.29   |     0.72   |     29.0   |     72.0   |     104.4  | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |  (24-29)   |      0     |      0.0   |     0.72   |      0.0   |     72.0   |     0.0    | 
  ------------------------------------------------------------------------------------------  
 |            |            |            |            |            |            |            | 
 |  (30-35)   |      2     |     0.29   |     1.01   |     29.0   |    101.0   |     104.4  | 
  ------------------------------------------------------------------------------------------  
Desea conocer la ubicación de algún dato con base a su porcentaje?: 1.Si  2.No
: 2

Media: 19.14
Mediana: 23
Moda: La moda es (6-11) con 3 repeticiones

Cuartil 1: 8.5
Cuartil 2: 23.0
Cuartil 3: 27.5
Cuartil 4: 32

Datos_en_el_cuartil_1: 7, 8,
Datos_en_el_cuartil_2: 9, 23, 23,
Datos_en_el_cuartil_3:
Datos_en_el_cuartil_4: 32, 32,

¿Que tipo de varianza desea que se emplee? 1.Poblacional  2.Muestral
2
Por favor ingrese el numero menor que desee que se analice con el teorema de chevyshev: 7
Por favor ingrese el numero mayor que desee que se analice con el teorema de chevyshev: 32

¿Desea conocer a cuantas desviaciones estandar de la media muestral se encuentra algún numero en específico?  1.Si  2.No
2
[[['-14.1', '-3.0', '8.1', '19.1', '30.2', '41.3', '52.4']]]

El rango es: 25
El rango intercuartico es: 19.0

|  Xi  |  media_muestral(Xˉ) | (Xi - Xˉ )^2 |
   7                19.14            147.38
   8                19.14            124.1
   9                19.14            102.82
   23                19.14            14.9
   23                19.14            14.9
   32                19.14            165.38
   32                19.14            165.38

La varianza muestral es de: 122.48
La desviacion estandar es de: 11.07
 el porcentaje en el que se encuentra el rango ingresado anteriormente segun la media muestral es de: 17
 El numero No se ingresó ningún numero, se encuentra a No se ingresó ningún numero, de desviaciones estandar de la media muestral
   ____________________________________________________  
  |                                                    | 
  |                                                    | 
  |                      _______                       | 
  |                     /   |   \                      | 
  |                ____/    |    \____                 | 
  |               / |       |       | \                | 
  |              /  |       |       |  \               | 
  |         ____/   | 34%   |  34%  |   \____          | 
  |        /|       |       |       |       |\         | 
  |  _____/ | 13.5% |       |       | 13.5% | \_____   | 
  | / | 24% |       |       |       |       | 24% | \  | 
   ¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯  
       -14.1      -3.0      8.1      19.1        30.2        41.3        52.4   
  |                  <------ ------>                   | 
  |                    EL 68% DENTRO                   | 
  |                     1 DESVIACION                   | 
  |                      ESTANDAR                      | 
  |                                                    | 
  |           <-------------  ------------->           | 
  |                    EL 95% DENTRO                   | 
  |                      2 DESVICIONES                 | 
  |                       ESTANDAR                     | 
  |    <--------------------    ----------------->     | 
  |                    EL 97% DE TODOS                 | 
  |                    LOS DATOS ESTAN                 | 
  |                DENTRO DE 3 DESVIACIONES            | 
  |                       ESTANDAR                     | 
  |                                                    | 
   ¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯  
   ________________________________________________________  
  |                                                        | 
  |                                                        | 
  |    |             _________ _________             |     | 
  |    |            |         |         |            |     | 
  |    |            |         |         |            |     | 
  |    |            |         |         |            |     | 
  |    |            |         |         |            |     | 
  |    |             ¯¯¯¯¯¯¯¯¯ ¯¯¯¯¯¯¯¯¯             |     | 
  |                 |         |         |                  | 
  |                 |         |         |                  | 
  |  _______________|_________|_________|_________________ | 
       -10.5      8.5       23.0        27.5        46.5   
  |  LIMITE        Q1        Q2        Q3        LIMITE    | 
  | INFERIOR                                    SUPERIOR   | 
  |________________________________________________________| 
```
Y así es como funciona este programa.

# NOTAS
Al utilizar este programa se debe tener en cuenta que:
- Para el diagrama de caja y el teorema de Chevyshev, el programa solo acepta 5 caracteres.
- Para el resto de funcionadad, el limite es 10 carateres.
  
