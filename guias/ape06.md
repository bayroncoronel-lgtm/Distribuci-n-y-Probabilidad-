#APE 06 - Distribuciones Continua - Notables

### Integrantes:

* Willan Granda
* Fernando Aguirre
* Darwin Campoverde
* Byron Coronel
* Axel Jimenez

### **Asignatura:** Teoría de la Distribución y Probabilidad  

### **Ciclo:** 2 "A"


<img width="678" height="525" alt="cap 1" src="https://github.com/user-attachments/assets/712d5f98-4aef-4178-b88a-c169d09d2177" />



<img width="619" height="327" alt="cap 2" src="https://github.com/user-attachments/assets/188de039-dde7-4a65-bb0e-38bf691e3bae" />



<img width="475" height="316" alt="cap 3" src="https://github.com/user-attachments/assets/aa501bfe-789f-4fcb-9e2e-04ee4276f3fc" />




<img width="461" height="451" alt="cap 4" src="https://github.com/user-attachments/assets/fcd1a538-64c8-4887-a62e-c521796ae14e" />




<img width="399" height="423" alt="cap 5" src="https://github.com/user-attachments/assets/9a142fff-7b60-4300-a3e6-94f415ad72fd" />




<img width="764" height="511" alt="cap 6" src="https://github.com/user-attachments/assets/67e09425-5cb0-46f7-aa0e-4d303a4f7d3f" />



<img width="805" height="467" alt="cap 7" src="https://github.com/user-attachments/assets/9c4787b5-c132-41c6-a5cc-2221299e0150" />



<img width="687" height="410" alt="cap 8" src="https://github.com/user-attachments/assets/d0eefa10-8e7a-4eb6-9037-f9ae6f4b4530" />



<img width="955" height="414" alt="cap 9" src="https://github.com/user-attachments/assets/f528e50c-1b2f-4784-aa1c-f95a10f6dc15" />



# PREGUNTAS DE CONTROL

### 1. Matemáticamente, ¿por qué en una variable aleatoria continua modelada por una función de densidad f(x) , la probabilidad de que tome un valor exacto es cero, es decir, P(X = c) = 0?

Porque en una variable aleatoria continua, la probabilidad se representa mediante el área bajo la curva de su función de densidad. Dado que un valor exacto representa un solo punto en el eje horizontal, su ancho es igual a cero. Al no tener ancho, no se genera ningún área en ese punto, por lo que P(X = c) = 0. Esto ocurre porque hay infinitos valores posibles en un entorno continuo, y la probabilidad de acertar a uno solo de forma exacta es de 1 entre infinito, lo cual es matemáticamente cero.

#### 2. Interprete conceptualmente qué significa que un valor de su dataset regional tenga un puntaje estándar de . ¿Se consideraría un valor atípico bajo el criterio de la regla empírica?

Que un valor de nuestro  dataset regional tenga un puntaje de -2.45 significa que este registro específico se encuentra bastante por debajo del promedio general. Al tener ese número negativo, nos indica que está alejado hacia abajo del centro de los datos. Tomando en cuenta la regla empírica, sí se lo consideraría como un valor atípico, porque la regla nos dice que la gran mayoría de los datos normales o habituales (alrededor del 95%) siempre se agrupan mucho más cerca del promedio, en un rango entre -2 y 2. Como este dato sobrepasa ese límite inferior, alejándose más allá del -2, se sale por completo de ese grupo común y se destaca como un caso inusualmente bajo dentro de la  región.

### 3. En la Tarea 3, calculó probabilidades asumiendo que su variable regional seguía una distribución Normal. ¿Qué riesgo metodológico existe al tomar decisiones basadas en este cálculo si la gráfica de la variable presenta un fuerte sesgo (skewness)?

El principal riesgo metodológico es obtener estimaciones de probabilidad incorrectas, lo que llevaría a tomar decisiones basadas en un escenario irreal. Al presentar un fuerte sesgo, la distribución real de los datos es asimétrica y se acumula hacia un lado, por lo que no coincide con la forma de campana perfecta y equilibrada del modelo normal. Si se fuerza una distribución normal sobre estos datos sesgados, se calcula de manera errónea la verdadera frecuencia de los eventos, terminando por sobreestimar o subestimar gravemente la probabilidad de que ocurran valores extremos. Por lo que cualquier decisión o planificación basada en este cálculo será muy poco confiable, ya que se estaría actuando sobre una predicción que no refleja el comportamiento genuino de los datos de la región.  

### 4. Con base en la Tarea 4 (ABI), si el p-valor del test de Shapiro-Wilk es , ¿cuál es la conclusión estadística respecto a la distribución de sus datos regionales? ¿Se invalida el cálculo realizado en la Tarea 3?

Si el p-valor del test de Shapiro-Wilk es 0.001, al ser un número mucho menor que el límite de error habitualmente aceptado (0.05), la conclusión estadística es que se rechaza la normalidad; es decir, está comprobado que los datos regionales no siguen una distribución normal. En consecuencia, el resultado práctico del cálculo realizado en la Tarea 3 sí queda invalidado. Porque ese procedimiento matemático se basó enteramente en la suposición de que los datos tenían una forma de campana perfecta, aplicar esa probabilidad a una variable que se comporta de otra manera genera una estimación engañosa y metodológicamente incorrecta para tomar cualquier decisión real.

### 5. Explique el principio matemático detrás del Gráfico Q-Q. ¿Qué representan los cuantiles teóricos en el eje X versus los cuantiles empíricos en el eje Y?

El principio matemático del Gráfico Q-Q (Quantile-Quantile) consiste en comparar los cuantiles de una muestra con los cuantiles de una distribución teórica, por lo general la distribución normal, para evaluar si los datos siguen dicha distribución. Si ambas distribuciones son similares, los puntos del gráfico se alinearán aproximadamente sobre una recta. En el eje X se representan los cuantiles teóricos, que son los valores esperados según la distribución teórica seleccionada, en el eje Y se representan los cuantiles empíricos, que corresponden a los cuantiles obtenidos a partir de los datos observados en la muestra, permitiendo comparar visualmente los datos reales con los valores que se esperarían bajo el modelo teórico. Cuanto más cerca estén los puntos de una línea recta, mayor será la concordancia entre la distribución de los datos y la distribución teórica.
