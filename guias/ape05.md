---
# GRUPO F
---
#### PARTICIPANTES:
* Willan Granda
* Darwin Campoverde
* Jeancarlos Aguirre
* Bayron Coronel
* Axel Jiménez
#### DOCENTE:
* Ing. Cristian Narváez
---




# **Tarea 1**

**Modelado Computacional de la Distribución Binomial**

Escenario: Control de calidad de software.
Un lote de 20 microservicios tiene una probabilidad del 15% de fallar bajo estrés.
Se modela el número de fallos usando una distribución Binomial(n=20, p=0.15).





<img width="601" height="511" alt="a" src="https://github.com/user-attachments/assets/c7d3aed5-d1c5-4d97-9a5b-01c0c32e4b01" />






<img width="975" height="447" alt="b" src="https://github.com/user-attachments/assets/77a9dbfe-144c-4978-bb34-946c3109e1cc" />






# **Tarea 2:**

**Modelado de la Distribución de Poisson (Eventos Raros)**

La distribución de Poisson modela el número de eventos que ocurren en un
intervalo de tiempo o espacio continuo, con una tasa media conocida . Su PMF
es:

$$
T(X = x) = \frac{e^{-\lambda}\lambda^x}{x!}
$$

Suponga que los servidores de la universidad en Loja reciben en promedio $$
\lambda = 4.5
$$
peticiones de acceso erróneas por minuto.
Basándose en la estructura del código de la Tarea 1, implemente la simulación
utilizando scipy.stats.poisson. Grafique únicamente la PMF evaluando desde $$
x = 0
$$
 hasta $$
x = 15
$$ .

Calcule mediante código la probabilidad exacta de recibir exactamente 6
peticiones erróneas en un minuto: .






<img width="604" height="401" alt="c" src="https://github.com/user-attachments/assets/ca582de3-23eb-4730-b9de-656134dede08" />







<img width="597" height="324" alt="d" src="https://github.com/user-attachments/assets/65efb72f-6718-4bac-97c8-8df8729f95b4" />






# **Tarea 3:**

**Hito texto en cursiva del Proyecto - Identificación de Variables de Conteo (ABP)
Cargue su dataset regional en pandas.**

Identifique una variable discreta que represente un "conteo" (ej. número de
accidentes semanales en Loja, número de transacciones diarias, cantidad de
clientes por hora).
Calcule la media muestral ( ) de esa variable y asuma que es el parámetro
para un modelo de Poisson teórico.
Genere un gráfico superponiendo el histograma de densidad de su variable
empírica contra la línea de la PMF teórica de Poisson generada en scipy. Discuta
visualmente si los datos reales siguen esta distribución.






<img width="631" height="519" alt="e" src="https://github.com/user-attachments/assets/d273deef-69d7-4a90-916c-277156070ba0" />







<img width="1239" height="408" alt="f" src="https://github.com/user-attachments/assets/20885a95-a235-4205-bc6d-02b639c59ad3" />






<img width="677" height="492" alt="g" src="https://github.com/user-attachments/assets/d684193d-eabd-4733-8d09-65a651108bc0" />







# **Tarea 4**
# Aproximación de la Distribución Binomial a Poisson

La distribución **Binomial** $X \sim \text{Bin}(n, p)$ puede aproximarse por una distribución de **Poisson** cuando se cumplen las siguientes condiciones:

- El número de ensayos $n$ es muy grande
- La probabilidad de éxito $p$ es muy pequeña
- El producto $\lambda = n \cdot p$ se mantiene constante

**Bajo estas condiciones:**

$$
X \sim \text{Bin}(n, p) \quad \approx \quad \text{Poisson}(\lambda)
$$

**donde:**

$$
\lambda = n \cdot p
$$

---

### Interpretación

Esto significa que cuando tenemos **muchos ensayos** con una **probabilidad muy baja de éxito**, el número de éxitos puede modelarse como eventos raros, lo cual es precisamente lo que describe la distribución de Poisson.

---

### Aplicación práctica

Esta aproximación es útil porque simplifica los cálculos, ya que la distribución de Poisson es más sencilla que la Binomial cuando $n$ es grande.

**Regla práctica común:**
- Si $n \geq 20$ y $p \leq 0.05$, la aproximación suele ser válida.






<img width="475" height="304" alt="a" src="https://github.com/user-attachments/assets/cea90715-fe3d-41c2-9950-3078d034ee45" />






### Conclusión

Los resultados obtenidos muestran que las probabilidades calculadas con la distribución **Binomial** y la **Poisson** son prácticamente idénticas.

Esto confirma experimentalmente que, cuando \( n \) es grande y \( p \) es pequeño, la distribución Binomial puede aproximarse de manera muy efectiva mediante una distribución de Poisson con parámetro \( \lambda = n \cdot p \).

La diferencia entre ambas probabilidades es mínima, lo que valida la aproximación teórica.





# **Preguntas de Control:**





### 1. Matemáticamente y conceptualmente, ¿por qué la Función de Distribución Acumulada (CDF) de una variable aleatoria discreta tiene una gráfica en forma de "escalera" (step function) a diferencia de las funciones continuas?


Matemáticamente: Su función de distribución F(x)=P(X≤x), se calcula mediante un
sumatorio de probabilidades: F(x)=∑xi≤xP(X=xi). El valor acumulado solo se incrementa cuando la variable avanza y alcanza un valor exacto definido dentro de su recorrido.


•	Conceptualmente: La probabilidad está concentrada únicamente en puntos aislados. Entre un punto y el siguiente no existe probabilidad adicional por lo que la acumulación se detiene, manteniendo la gráfica plana. Cuando se llega a un nuevo valor válido, la función experimenta un salto cuya altura es exactamente igual a la probabilidad de ese punto específico.


¿Por qué difiere de la variable continua?
•	Probabilidad puntual nula: A diferencia de las discretas, en una variable continua la probabilidad de que tome un valor exacto y prefijado es siempre cero (P(X=x)=0).


•	Acumulación ininterrumpida: Al carecer de probabilidades concentradas en puntos, no existen los saltos. La probabilidad se asocia a intervalos y se acumula ininterrumpidamente a través del cálculo de una integral, lo que resulta en una curva suave y continua a lo largo de todo su dominio.


### 2. Analizando los supuestos del experimento de Bernoulli, si extraemos cartas de una baraja sin reemplazo buscando ases, ¿podemos modelar este escenario con una distribución Binomial? Justifique estadísticamente su respuesta.
No, no es posible modelar este escenario utilizando la distribución binomial.
La distribución Binomial se basa en la repetición de ensayos de Bernoulli, cuyos dos supuestos fundamentales se rompen al realizar extracciones sin reemplazo:


•	Independencia de los eventos: La distribución Binomial exige que el resultado de un ensayo no afecte en absoluto el resultado de los ensayos posteriores, al extraer una carta y no devolverla al mazo, la composición de la baraja cambia. Por lo tanto, el resultado de la segunda extracción es directamente dependiente de lo que ocurrió en la primera.


•	Probabilidad de éxito constante (p): Debe mantenerse inalterable en cada iteración. En un mazo estándar de 52 cartas con 4 ases, ocurre lo siguiente sin reemplazo:


1.	Probabilidad en la 1ª extracción: P(As) = 4/52 ≈ 0.0769
2.	Probabilidad en la 2ª extracción (si el primero fue un as): P(As) = 3/51 ≈ 0.0588
3.	Probabilidad en la 2ª extracción (si el primero no fue un as): P(As) = 4/51 ≈ 0.0784


Como la probabilidad de éxito p fluctúa en cada ensayo, la fórmula de la PMF de la binomial, arrojaría resultados incorrectos.


### 3. En la Tarea 3 de su proyecto (ABP), ¿qué limitaciones existen al asumir que la tasa media (λ) calculada de su dataset permanece constante a lo largo de todo el periodo de estudio? ¿Se cumple la propiedad de estacionariedad?

Asumir una tasa media ($\lambda$) constante es una gran limitación porque presupone falsamente que los eventos ocurren a un ritmo uniforme, ignorando la variabilidad del mundo real; de hecho, el análisis de este dataset revela una sobredispersión extrema donde la varianza (182850.10) supera abrumadoramente a la media (806.66), provocando que la curva teórica no se ajuste al histograma empírico. Por esta misma razón empírica, no se cumple la propiedad de estacionariedad, la cual exige que la tasa de ocurrencia se mantenga inalterable en cualquier momento o espacio medido; la enorme diferencia entre los estadísticos demuestra que la tasa real fluctúa drásticamente entre los registros, rompiendo así los supuestos fundamentales de independencia y homogeneidad del modelo de Poisson.

### 4. A partir de la investigación en la Tarea 4 (ABI), ¿cuáles son los umbrales prácticos (valores comúnmente aceptados en la literatura estadística de n y p) para considerar que la aproximación de Poisson a la Binomial es segura y válida?

En la práctica, la literatura estadística establece dos reglas generales para que esta aproximación sea segura:Regla básica: $n \ge 20$ y $p \le 0.05$.Regla para muestras grandes: Si $n \ge 100$, el producto $n \cdot p$ (es decir, $\lambda$) debe ser menor o igual a 10.En nuestro experimento usamos $n = 1000$ y $p = 0.003$, cumpliendo a la perfección con la regla para muestras grandes (ya que $\lambda = 3$). Al estar dentro de este umbral seguro, el código validó en la práctica que la aproximación funciona, arrojando una diferencia mínima de apenas 0.000112 entre la distribución Binomial y la de Poisson.

### 5. Si $X \sim \text{Poisson}(\lambda)$, sabemos teóricamente que $E[X] = \lambda$ y $V[X] = \lambda$. ¿Se cumple esta propiedad (media igual a varianza) en la variable de conteo que extrajo de su dataset regional? Calcule ambos estadísticos muestrales y comente.

No, la propiedad teórica de la distribución de Poisson ($E[X] = V[X] = \lambda$) no se cumple en los datos empíricos extraídos de nuestro dataset regional.Al calcular los estadísticos muestrales para la variable de conteo (num_fincas), obtuvimos los siguientes resultados:Media muestral ($\bar{x}$): 806.66Varianza muestral ($s^2$): 182850.10

Como se puede observar de forma directa en los cálculos, la varianza muestral (182850.10) es abrumadoramente mayor que la media muestral (806.66). En estadística, este fenómeno de la vida real se conoce como sobredispersión. Esto significa que nuestros datos presentan una variabilidad o dispersión muchísimo más alta de la que el modelo teórico de Poisson puede soportar. En consecuencia, aunque utilizamos la media muestral para definir nuestro parámetro $\lambda = 806.66$, la gran diferencia entre ambos estadísticos demuestra que la variable num_fincas no se ajusta perfectamente a una distribución de Poisson, ya que viola este supuesto fundamental de que la esperanza matemática y la varianza deben ser iguales.
