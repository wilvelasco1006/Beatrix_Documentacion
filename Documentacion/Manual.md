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
