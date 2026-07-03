# Guía de Actividades Práctico-Experimentales Nro. 001
## Variables Aleatorias y Distribuciones de Probabilidad

**1. Datos Generales:**
* **Asignatura:** Teoría de la Distribución y Probabilidad
* **Ciclo:** 2do "A" - Carrera de Computación
* **Docente:** Cristian Ramiro Narváez Guillén
* **Resultado de Aprendizaje:** Calcula probabilidades y momentos de variables aleatorias discretas y continuas bajo los principios de solidaridad, responsabilidad, transparencia y honestidad.



<img width="462" height="317" alt="cap 1" src="https://github.com/user-attachments/assets/b1581df0-6dac-4f1a-aef6-d9d731c7912b" />



## Tarea 1: Variable Aleatoria Discreta - Análisis Analítico y Simulación
### Caso de Estudio: Control de Calidad en Componentes Electrónicos

Una fábrica de componentes electrónicos sabe que el **5%** de sus productos son defectuosos. Se selecciona una muestra aleatoria de **20 componentes**.

Definimos la Variable Aleatoria:
* $X$: Número de componentes defectuosos en la muestra de 20.
* $X \sim \text{Binomial}(n = 20, p = 0.05)$



<img width="603" height="421" alt="cap 2" src="https://github.com/user-attachments/assets/ca1d9fec-c88e-4428-a10e-0ddf5e2da382" />




<img width="711" height="473" alt="cap 3" src="https://github.com/user-attachments/assets/6e23be94-90f8-4684-abb3-ceb961df0bb1" />




<img width="558" height="500" alt="cap 4" src="https://github.com/user-attachments/assets/2a3c8213-1279-4f46-a2df-d4f8db82def1" />




<img width="510" height="514" alt="cap 5" src="https://github.com/user-attachments/assets/ef6cbc59-b361-4e5a-b2aa-dff79dfcfac7" />




<img width="591" height="442" alt="cap 6" src="https://github.com/user-attachments/assets/d2315c89-fab8-4e54-afbd-fbbfb44971a1" />




## Tarea 2: Variable Aleatoria Continua - Distribución Normal y Estandarización
### Caso de Estudio: Resistencia de Materiales en Infraestructura de TI

En el desarrollo de un centro de datos, se analiza la resistencia a la tracción de un compuesto de fibra de carbono utilizado para los racks de los servidores. Se sabe que la resistencia $X$ (en MPa) se distribuye normalmente con una media de $\mu = 500 \text{ MPa}$ y una desviación estándar de $\sigma = 40 \text{ MPa}$.

$$X \sim \mathcal{N}(\mu = 500, \sigma^2 = 40^2)$$

**Objetivos del bloque:**
1. Graficar la función de densidad de probabilidad (PDF) teórica.
2. Calcular áreas bajo la curva utilizando la tipificación $Z = \frac{X - \mu}{\sigma}$.
3. Realizar una aproximación mediante la función de distribución acumulada (CDF) de SciPy.




<img width="595" height="434" alt="cap7" src="https://github.com/user-attachments/assets/124aa96c-0a4f-4d6b-9453-e5cbbf271f1f" />




<img width="705" height="320" alt="cap 8" src="https://github.com/user-attachments/assets/0b19823b-8227-469c-af2a-c498c3e5c615" />




<img width="593" height="414" alt="cap 9" src="https://github.com/user-attachments/assets/3d22a8e4-f01c-4920-ab67-556a610cb70a" />





<img width="1043" height="377" alt="a" src="https://github.com/user-attachments/assets/63c9de10-5c91-4595-9bf9-a15ba92fb899" />





## Tarea 3: Verificación Computacional de Momentos y Teorema de Chebyshev

Siguiendo el estándar de análisis riguroso de datos del laboratorio, utilizaremos simulación para contrastar las métricas de variabilidad teórica contra las empíricas, y validaremos el comportamiento de colas mediante la desigualdad estadística.




<img width="504" height="408" alt="a" src="https://github.com/user-attachments/assets/2420ce69-f042-455d-85f7-bae056ea8a10" />




<img width="460" height="274" alt="b" src="https://github.com/user-attachments/assets/db5919d5-6116-4b39-b666-77e2187ff259" />




## Tarea 4: Simulación Estocástica y Análisis Comparativo Empírico
Generación de muestras aleatorias ($N=1000$) para contrastar visual y estadísticamente las aproximaciones muestrales frente a sus respectivos marcos teóricos (PMF y PDF).




<img width="744" height="519" alt="a" src="https://github.com/user-attachments/assets/716c1191-ba0e-4b6a-b258-5a31986ffdcb" />




<img width="1043" height="458" alt="b" src="https://github.com/user-attachments/assets/aef6ac65-321e-4975-a32d-5d1226eecf5d" />





## 5. Resultados Esperados y Conclusiones del Laboratorio
* **Comprensión Conceptual:** Identificación formal de los dominios de las variables discretas (valores contables/enteros) y continuas (escalas continuas/mediciones reales).
* **Eficiencia Computacional:** Uso de funciones clave (`pmf`, `pdf`, `cdf`, `ppf`) de `scipy.stats` para modelar y resolver problemas complejos sin recurrir a tablas impresas tradicionales.
* **Convergencia Estocástica:** Demostración de que las frecuencias relativas provenientes de muestreos Monte Carlo de tamaño $N=1000$ convergen con precisión controlada hacia los parámetros poblacionales e integrales teóricas establecidas.



## 6. Resolución Programática de las Preguntas de Control del APE 1
Para garantizar consistencia y replicabilidad computacional (estilo APE 7), se resuelven y programan todos los ejercicios de la sección analítica de la guía.




<img width="586" height="370" alt="a" src="https://github.com/user-attachments/assets/9b993b4a-8d6a-4610-bb7b-56bc2c91dd88" />





<img width="548" height="366" alt="b" src="https://github.com/user-attachments/assets/47e0c623-8d40-4767-bd1e-cff7c917f9d6" />





### Conceptos Teóricos y Fundamentación Matemática (Respuestas de Control)

1. **Importancia de la Distribución Normal:**
   * **Teorema del Límite Central (TLC):** Explica por qué una enorme cantidad de variables en la naturaleza y la ingeniería se comportan como normales, ya que la suma o promedio de variables independientes tiende a estabilizarse bajo esta curva.
   * **Propiedad de Simetría:** Es perfectamente simétrica respecto a su media, dividiendo el área en dos porciones exactas de $0.50$.
   * **Parametrización Única:** Está totalmente definida por únicamente dos momentos analíticos: su localización ($\mu$) y su escala ($\sigma$).

2. **Uso Práctico de la Función Generatriz de Momentos (FGM):**
   La FGM se define algebraicamente como el valor esperado de la transformación exponencial:
   $$M_X(t) = E\left[e^{tX}\right]$$
   Permite extraer los momentos crudos de cualquier variable de manera puramente algebraica sin necesidad de realizar integraciones continuas repetitivas sobre funciones de densidad complejas:
   * **Media Teórica:** Se obtiene evaluando la primera derivada respecto a $t$ en el origen: $\mu = M_X'(0)$.
   * **Varianza Teórica:** Se deduce combinando la segunda derivada y la primera: $\sigma^2 = M_X''(0) - [M_X'(0)]^2$.
