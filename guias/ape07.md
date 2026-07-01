# APE 007 - Distribuciones Muestrales y Teorema del Límite Central (TLC)
**Nombre:**
* Bayron Coronel
* Darwin Campoverde
* Axel Jiménez
* Willan Granda
* Jeancarlos Aguirre

**Carrera:** Computación  
**Fecha:** 30/05/2026

**Objetivo:** Demostrar computacionalmente el Teorema del Límite Central mediante simulación estocástica y aplicar bootstrapping al dataset regional.



<img width="497" height="361" alt="cap 1" src="https://github.com/user-attachments/assets/bfdae9da-23c8-4dd1-908b-3f06c4db1705" />



<img width="517" height="301" alt="cap 2" src="https://github.com/user-attachments/assets/cd1d142a-3516-453b-ade3-af958810025c" />



<img width="538" height="372" alt="cap 3" src="https://github.com/user-attachments/assets/b99787e6-f0f3-47a5-919e-1e3da4415fce" />



<img width="504" height="316" alt="cap 4" src="https://github.com/user-attachments/assets/468468d1-a0a3-4e97-aa99-6be17cfdabbf" />



<img width="800" height="498" alt="cap 5" src="https://github.com/user-attachments/assets/197a8d4b-4dd5-48f6-bf30-baecb964400b" />



<img width="509" height="303" alt="cap 6" src="https://github.com/user-attachments/assets/a1c5a016-c9d9-4aee-a497-eaaf0cbaebbc" />



<img width="673" height="324" alt="cap 7" src="https://github.com/user-attachments/assets/ddcb60bb-a93a-4185-891f-7b0f034b69d0" />



<img width="538" height="314" alt="cap 8" src="https://github.com/user-attachments/assets/35f6bc0d-e584-480d-8921-8c7f89de8752" />




### Interpretación del decaimiento del Error Estándar

Cuando analizamos cómo cambia el error estándar al aumentar el tamaño de la muestra, observamos que la curva no baja de manera lineal, sino de forma **asintótica**.


## Preguntas de Control

### Pregunta 1
**¿Por qué el Teorema del Límite Central es considerado el puente matemático fundamental entre la probabilidad descriptiva y la inferencia estadística?**

El Teorema del Límite Central (TLC) establece que, bajo condiciones generales, la distribución de las **medias muestrales** de una población con media y varianza finitas tiende a una distribución Normal cuando el tamaño de la muestra $n$ crece. Esto convierte a la Normal en un modelo universal para el comportamiento de las medias, incluso cuando la población original no es normal.  

Gracias a esto, podemos pasar de la **probabilidad descriptiva** (describir datos observados) a la **inferencia estadística** (estimar parámetros poblacionales, construir intervalos de confianza y realizar pruebas de hipótesis) usando la Normal como aproximación teórica para la media muestral.

---

### Pregunta 2
**Demuestre, utilizando los datos numéricos impresos en su consola en la Tarea 2, cómo se cumple con precisión la propiedad matemática fundamental: $E[\bar{X}] = \mu$.**

En la Tarea 2 se imprimen dos cantidades clave:

- La media poblacional real $\mu$ de la distribución exponencial.
- La media de las medias muestrales $\overline{\bar{X}}$ obtenida a partir de las $k = 1000$ muestras de tamaño $n = 30$.

Al comparar numéricamente ambos valores, se observa que:

$$ \overline{\bar{X}} \approx \mu $$

con una diferencia muy pequeña debida únicamente al error de simulación. Esta coincidencia empírica ilustra la propiedad teórica:

$$ E[\bar{X}] = \mu $$

es decir, la media muestral es un **estimador insesgado** de la media poblacional.

---

### Pregunta 3
**En la Tarea 4, al graficar la curva del Error Estándar frente a $n$, ¿por qué la curva decrece siguiendo una trayectoria no lineal? Si requiere reducir el error estándar exactamente a la mitad, ¿cuántas veces debe incrementar el tamaño de la muestra?**

La curva es no lineal porque el error estándar de la media se define como:

$$ \sigma_{\bar{X}} = \frac{\sigma}{\sqrt{n}} $$

Por lo tanto, al aumentar $n$, el error estándar decrece con la **raíz cuadrada** de $n$, no de forma proporcional.  

Si queremos reducir el error estándar a la mitad, planteamos:

$$ \frac{\sigma}{\sqrt{n_{\text{nuevo}}}} = \frac{1}{2} \cdot \frac{\sigma}{\sqrt{n_{\text{actual}}}} \Rightarrow n_{\text{nuevo}} = 4 \cdot n_{\text{actual}} $$

Es decir, para reducir el error estándar a la mitad, debemos **multiplicar el tamaño de la muestra por 4**.

---

### Pregunta 4
**Si la población analizada en su proyecto integrador regional posee una asimetría extrema (como una distribución de Pareto), ¿es suficiente un tamaño muestral de $n = 30$ para garantizar la normalidad de las medias? Justifique.**

La regla empírica de $n \geq 30$ funciona razonablemente bien para poblaciones moderadamente asimétricas con varianza finita. Sin embargo, en el caso de **asimetría extrema** (por ejemplo, distribuciones tipo Pareto con colas muy pesadas), la convergencia de las medias muestrales hacia la Normal puede ser **mucho más lenta**.  

En estos escenarios, un tamaño muestral de $n = 30$ puede no ser suficiente. Se requieren tamaños muestrales mayores y verificación empírica.

---

### Pregunta 5
**Diferencie conceptual y operativamente la "Desviación Estándar ($\sigma$)" de una muestra individual frente al "Error Estándar de la Media ($\sigma_{\bar{X}}$)".**

- **Desviación Estándar ($\sigma$) de una muestra individual:**  
  Mide la **dispersión de los datos individuales** alrededor de la media. Cuantifica qué tan dispersos o concentrados están los valores observados en la población o muestra original. Se calcula directamente sobre los datos $X_1, X_2, \dots, X_n$.

- **Error Estándar de la Media ($\sigma_{\bar{X}}$):**  
  Mide la **variabilidad de la media muestral** como estimador de la media poblacional. Teóricamente se define como:

  $$ \sigma_{\bar{X}} = \frac{\sigma}{\sqrt{n}} $$

  Operativamente, en las simulaciones se estima como la desviación estándar de las medias muestrales obtenidas por Monte Carlo o bootstrapping.
