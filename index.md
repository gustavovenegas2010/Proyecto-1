# Preguntas sobre Satisfacción Laboral de los encuestados de la base Stack Overflow Data - Encuesta de 2017

El conjunto de datos tiene más de 50.000 observaciones y 154 variables. Sobre está base de datos me intereso realizarme las siguientes preguntas: 

Pregunta 1: ¿Cómo se comporta la satisfacción laboral?

Pregunta 2: ¿Si una persona tiene alta satisfacción por un carrera (CareerSatisfaction), también tendrá alta satisfacción por su trabajo (JobSatisfaction)?

Pregunta 3: ¿Qué variables cualitativas y cuantitativas influyen para que un empleado tenga una alta satisfacción por su trabajo (JobSatisfaction)?


## Pregunta 1


Imagenes/1.PNG


Se calculo un resumen de estadísticas descriptivas de la variable _JobSatisfaction_, donde se puede visualizar que en promedio la satisfacción laboral es de 6.9 es decir que la mayoría de encuestados tienen buena satisfacción laboral. También se evidencia que el percentil 1 (25%) es 6, por consiguiente el 75% de los encuestados tienen una satisfacción laboral por encima de 6 que es aceptable, como se puede ver en las siguiente tabla, grafico de barras y diagrama caja.

A continuación se realiza las siguientes tablas comparando la satisfacción laboral con el estado del empleado, el tamaño de la compañía y el país. De aquí se concluye que los empleados con menos satisfacción laboral son los que tienen contratos de tiempo completo.

También se evidencia que los empleados con mayor satisfacción laboral son los que trabajan para empresas con 10 a menos empleados, seguidas de las empresas de 10 a 19 empleados; de aquí se concluye que los de mayor satisfacción laboral son los empleados cuyas empresas cuentas con pocos empleados.

## Pregunta 2

Se realizo un diagrama de correlación anterior se muestra que entre las variables cuantitativas la mayor relación lineal se encuentra entre las variables de JobSatisfaction y _CareerSatisfaction_, con una correlación de 0.65. Al tener esta nos indica que existen indicios que entre más Satisfacción por su carrera también tendrá mayor satisfacción por su trabajo. A continuación realizaremos un modelo lineal simple para verificar si esta variable incide y cuál es su impacto?

Se realizo un prepocesamiento de dato para la realización del modelo, donde el modelo se va realizar únicamente con las variables de JobSatisfaction y _CareerSatisfaction_, realizar una subset a la base con estas dos variables.

Dado que la base de datos contiene valores en null procedemos a eliminar las filas con valores null, dejando un total de 40.352 registos para realizar el modelo

Después de realizar la regresión lineal simple observamos que el R2 es igual a 0.4170 lo que indica que la variable 'CareerSatisfaction' explica una parte de la variable 'JobSatisfaction', sin embargo después de probar con más variables en ejercicios alternos no logra incrementar su r2, por consiguiente se revisa los estadísticos Prob (F-statistic) y P_value de la variable 'CareerSatisfaction', para determinar si es significativa.

También se analiza la probabilidad de la estadística F, Prob( F statistic )=0.00 es menor a 0.05% , con un nivel del 95% podemos rechazar la hipótesis nula (Ho), es decir que el modelo es explicativo, por consiguiente la variable 'CareerSatisfaction' del modelo tiene efecto en la variable de respuesta 'CareerSatisfaction' y también observamos que el p_value de la variable 'CareerSatisfaction' es 0.000, menor a 0.05%, es decir que es significativa para el modelo.

Por lo anterior se concluye que el grado de satisfacción por una carrera influye en la satisfacción por el trabajo, sin embargo no es suficiente para explicar el la satisfacción por el trabajo, por consiguiente debe existir otras variables que también contribuyan para que la satisfacción por el trabajo sea mayor.

## Pregunta 3

Dado que la base de datos contiene más de 140 variables cualitativas, seleccionamos las variables cualitativas que están más relacionadas con las condiciones laboral como lo son: 'EmploymentStatus'_, _'CompanySize' y _'SeriousWork'_, está selección de variables se realiza despendiendo el punto de vista de investigador.

Dado que la base de datos contiene valores en null procedemos a eliminar las filas con valores null.

### Modelo lineal Múltiple:

Con el objetivo de analizar variables cualitativas en el modelo de regresión lineal múltiple, es necesario convertir cada categoría de cada variable en 1 columna respectivamente, este proceso se conoce como "one-hot encoding".

Después de obtener la base, se introduce todas las variables en el modelo con el fin de determinar cúales son las más relevantes.

Después de realizar el modelo, encontramos que existe problemas de multicolinealidad, ya que todas las columnas las ingresamos al modelo. Por consiguiente se realizó varias interacciones seleccionando diferentes variables y el modelo presentado a continuación, es el mejor modelo que itero con un R2 igual a 89.3% y nos indica que las variable de 'EmploymentStatus' es significativa para modelo, es decir que el estado del empleado influye positivamente en la satisfacción del trabajador.

#### Después de realizar queda la pregunta: _¿Qué las otras variables cualitativas son significativas e influyen en la satisfacción laboral de un empleado?_, averígualo replicando este código con otras variables.*




