# BEDU-Santander: Proyecto final

## Problema: "Análisis de la Inseguridad Alimentaria en México"               

Un centro de salud nutricional está interesado en analizar estadísticamente y probabilísticamente los patrones de gasto en alimentos saludables y no saludables en los hogares mexicanos con base en su nivel socioeconómico, en si el hogar tiene recursos financieros extras al ingreso y en si presenta o no inseguridad alimentaria. Además, está interesado en un modelo que le permita identificar los determinantes socioeconómicos de la inseguridad alimentaria.
        
La base de datos es un extracto de la Encuesta Nacional de Salud y Nutrición (2012) levantada por el Instituto Nacional de Salud Pública en México. 

La mayoría de las personas afirman que los hogares con menor nivel socioeconómico tienden a gastar más en productos no saludables que las personas con mayores niveles socioeconómicos y que esto, entre otros determinantes, lleva a que un hogar presente cierta inseguridad alimentaria.
                     
La base de datos contiene las siguientes variables:
  - nse5f (Nivel socieconómico del hogar): 1 "Bajo", 2 "Medio bajo", 3 "Medio", 4 "Medio alto", 5 "Alto". 
  - area (Zona geográfica): 0 "Zona urbana", 1 "Zona rural".
  - numpeho (Número de personas en el hogar).
  - refin (Recursos financieros distintos al ingreso laboral): 0 "no", 1 "sí".
  - edadjef (Edad del jefe/a de familia).
  - sexoje (Sexo del jefe/a de familia): 0 "Hombre", 1 "Mujer".
  - añosedu (Años de educación del jefe de familia).
  - ln_als (Logarítmo natural del gasto en alimentos saludables).
  - ln_alns (Logarítmo natural del gasto en alimentos no saludables).
  - IA (Inseguridad alimentaria en el hogar): 0 "No presenta IA", 1 "Presenta IA".
        

![gráfica del resumen estadístico](https://github.com/dnsmartinez/BEDU_S08_Postwork/blob/main/figs/s08_postwork_summary.png)
![gráfica del gasto en alimentos saludables y no saludables](https://github.com/dnsmartinez/BEDU_S08_Postwork/blob/main/figs/s08_postwork_corr.png)


Punto 1 Plantea el problema del caso.
General: Determinar los patrones que generan inseguridad alimentaria en México.
a) Determinar el gasto en alimentos saludables y no saludables con base en su nivel socioeconómico, recursos extras y seguridad alimentaria.
b) Proponer un modelo para identificar los determinantes socioeconómicos de la inseguridad alimentaria.
c) Probar/desechar que a menor nivel socioeconómico mayor es el consumo en alimentos no saludables.
Para poder trabajar con los datos es necesario importar las librerías correspondientes. Después se realiza la lectura de datos y se asigna a un data frame.
Se realiza la limpieza de datos. En el data frame Casos.completos se asignan únicamente los registros que no tengan datos faltantes usando la función complete.cases.
A pesar de que se reducen a la mitad los elementos de la muestra sigue siendo una muestra aceptable para el análisis.
Transformación de variables
Las variables categóricas (que son si o no, hombre o mujer, nivel socioeconómico) se transforman en factores. En este caso se transformaron las variables Nivel socieconómico, Zona geográfica, Recursos financieros distintos al ingreso laboral, Sexo del jefe/a de familia e Inseguridad alimentaria en el hogar.
Se hace el cambio a factores para facilitar la lectura de datos a R y aplicar las herramientas estadísticas adecuadas.
Al final se muestra como quedaron los datos en el data frame.
Punto 2. Realiza un análisis descriptivo de la información (Sesión 3)
Con table agrupamos las categorías y contamos cuántos datos hay de la misma. Se realiza este paso para las variables categóricas. Con el transform obtenemos las frecuencias relativas. 
Imprimimos las probabilidades que acabamos de calcular así como las medias y desviaciones estándar de los logaritmos naturales del gasto en alimentos saludables y no saludables.
Al final mostramos los distintos estadísticos descriptivos.
Histogramas y gráficas con el resumen de los datos
A continuación se muestran los histogramas y gráficas con el resumen de los datos.
Para las variables categóricas utilizamos donut_chart y para las variables cualitativas discretas y continuas usamos bar_plots e histograms.
Gasto en alimentos saludables
En la gráfica del gasto en alimentos saludables, se observa que los datos tienen un sesgo a la izquierda y que la gráfica es leptocurtica.
Gasto en alimentos no saludables
En la gráfica del gasto en alimentos no saludables, se observa que los datos tienden a una distribución normal, simétrica y platicúrtica. 
Todas las paletas de colores usadas en las gráficas son amigables con las personas que padecen de algún problema de daltonismo usando las paletas de colorBrewer
Generamos un resumen de las imágenes que se guarda en el disco duro.
Calculamos la correlación entre el gasto de alimentos saludables y no saludables con base en el nivel socioeconómico, recursos extras y la inseguridad alimentaria.
Como las variables son categóricas se transforman a datos numéricos 

Punto 3. Calcula probabilidades que nos permitan entender el problema en México
Se usarán las variables nivel socioeconómico (nse5f) y el gasto en alimentos no saludables (ln_alns) para buscar la probabilidad de la relación del nivel socioeconómico bajo contra el intervalo de gastos en alimentos no saludables.
Obtenemos la media, desviación estándar, valor máximo y valor mínimo de la variable del gasto en alimentos no saludables. 
Hacemos grupos de cuatro partes
Agrupamos el gasto de alimentos no saludables en los grupos previamente generados.
Elaboramos la primera tabla de frecuencia de los datos agrupados en intervalos. 
Luego hacemos una tabla cruzada con los datos del nivel socioeconómico con los gastos ahora en intervalos.
Se toman los valores de la primera fila que es el nivel bajo.
Busco el rango que me dé la mayor probabilidad de los gastos en alimentos no saludables.


Punto 4. Plantea hipótesis estadísticas y concluye sobre ellas para entender el problema en México

Punto 5. Estima un modelo de regresión, lineal o logístico, para identificar los determinantes 
de la inseguridad alimentaria en México



