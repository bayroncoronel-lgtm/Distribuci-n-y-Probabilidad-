<h1 align="center">🔷 Portafolio Digital Sistematizado 🔷</h1>

---

# Componente 1: El Documento Técnico (Unidad 2)

**Asignatura:** Teoría de la Distribución y Probabilidad  
**Estudiante:**
* Bayron Alexander Coronel Sarango

**Ciclo:**
* Segundo Ciclo
## 1. Pruebas de Hipótesis Unimuestrales (Tarea APE 09)

En esta sección se analiza si la temperatura media registrada durante el mes de diciembre en la Estación Quinara M0145 difiere significativamente de una media hipotética de referencia de 21.0 °C. Para ello se aplica una prueba t de Student para una muestra, considerando que la desviación estándar poblacional es desconocida.

### Formulación de Hipótesis

Hipótesis nula:

$$
H_0:\mu=21.0
$$

La temperatura media poblacional durante diciembre es igual a 21.0 °C.

Hipótesis alternativa:

$$
H_1:\mu\neq21.0
$$

La temperatura media poblacional durante diciembre es diferente de 21.0 °C.

### Estadístico de prueba

Debido a que la desviación estándar poblacional es desconocida, se utiliza la distribución t de Student.

$$
t=\frac{\bar{x}-\mu_0}{s/\sqrt{n}}
$$

donde:

- $\bar{x}$ = media muestral.
- $s$ = desviación estándar muestral.
- $n$ = tamaño de la muestra.

Se adopta un nivel de significancia de

$$
\alpha=0.05
$$

para tomar la decisión estadística.

<img width="456" height="479" alt="cap 1" src="https://github.com/user-attachments/assets/37486a0b-5fcf-4d77-a6d6-0f760f2d9042" />


<img width="577" height="462" alt="cap 2" src="https://github.com/user-attachments/assets/e2fb5552-8aec-4f80-bd1d-b98303c7754a" />


<img width="820" height="329" alt="cap 3" src="https://github.com/user-attachments/assets/cf7dbfb9-c51a-4047-8747-c2e8cd7c2c60" />


## 2. Comparación de Grupos (Tareas APE 10 y 11)

En esta sección se comparan las temperaturas registradas durante el mes de diciembre entre tres estaciones meteorológicas representativas de la provincia de Loja: Quinara (M0145), Zaruma (M0180) y San Marcos–La Célica (M1266). Para ello se aplica un Análisis de Varianza (ANOVA) de un factor con el objetivo de determinar si existen diferencias estadísticamente significativas entre las medias de temperatura de los grupos analizados.

### Formulación de Hipótesis

Hipótesis nula

$$
H_0:\mu_{Quinara}=\mu_{Zaruma}=\mu_{Célica}
$$

Las medias poblacionales de temperatura son iguales en las tres estaciones.

Hipótesis alternativa

$$
H_1:\exists(i,j)\;tal\;que\;\mu_i\neq\mu_j
$$

Al menos una de las medias poblacionales es diferente.

### Estadístico de prueba

El ANOVA de un factor utiliza el estadístico

$$
F=\frac{MS_{Entre\;Grupos}}{MS_{Dentro\;de\;los\;Grupos}}
$$

donde:

- $MS_{Entre\;Grupos}$ representa la variabilidad entre las medias de los grupos.
- $MS_{Dentro\;de\;los\;Grupos}$ representa la variabilidad interna de cada grupo.

Se adopta un nivel de significancia de

$$
\alpha=0.05
$$

Si el valor-p obtenido es menor que $\alpha$, se rechaza la hipótesis nula y se aplica la prueba Post-Hoc de Tukey para identificar qué pares de estaciones presentan diferencias estadísticamente significativas.

El estadístico utilizado en la prueba de Tukey se expresa como:

$$
Q=\frac{\bar{x}_{max}-\bar{x}_{min}}
{\sqrt{\frac{MS_{Dentro}}{n}}}
$$

<img width="466" height="501" alt="cap 4" src="https://github.com/user-attachments/assets/7bb0f63f-b793-4a1a-9f7a-f59cffb61c9b" />


<img width="1003" height="368" alt="cap 5" src="https://github.com/user-attachments/assets/b259f054-a4c3-4dd0-9540-a759bd209950" />

