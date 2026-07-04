# APE 011 - Inferencia Estadística Multigrupo: Análisis de Varianza (ANOVA de 1 factor) y Pruebas Post-Hoc (Tukey)

## Integrantes:


*   Willan Granda
*   Darwin Campoverde
*   Bayron Coronel
*   Jeancarlos Aguirre
*   Axel Jiménez

## Docente:
*   Ing. Cristian Narvaéz

## Fecha:

*  22/06/2026


<img width="656" height="518" alt="cap 1" src="https://github.com/user-attachments/assets/100f6efc-6e27-4d53-a73e-696ebe663c40" />



<img width="549" height="339" alt="cap 2" src="https://github.com/user-attachments/assets/d0f3820c-a2ab-4f75-a6c7-e750cd6cfb8b" />



Se evidenció mediante el análisis estadístico que el Algoritmo A presenta un consumo medio de memoria RAM de 118.91 MB, resultando significativamente más eficiente que el Algoritmo B, cuyo promedio asciende a 126.71 MB, como se obtuvo un valor-p de 0.0133, cifra que es muuy inferior al nivel de significancia establecido del 5% (alfa de 0.05), se rechaza la hipótesis nula, confirmando empíricamente que esta diferencia de rendimiento no es producto del azar. Asimismo, el estadístico T de -2.5362 y el claro desplazamiento hacia la izquierda de la curva de densidad del Algoritmo A en la gráfica corroboran, tanto visual como matemáticamente, su menor consumo sistemático de recursos.




<img width="615" height="423" alt="cap 3" src="https://github.com/user-attachments/assets/f535da7b-1ec2-488a-8523-9f07cfcd31c7" />




Para esta práctica se planteó la hipótesis nula de que el nuevo firewall no produce una reducción significativa en la latencia de los servidores, mientras que la hipótesis alternativa establece que sí existe una disminución significativa de la latencia después de su instalación. Luego de aplicar la prueba t para muestras pareadas, se obtuvo un valor-p menor a 0.05, por lo que se rechazó la hipótesis nula. Esto permite concluir que el firewall logró reducir significativamente la latencia de los servidores, mejorando así el rendimiento y la velocidad de respuesta de la red.





<img width="696" height="521" alt="a" src="https://github.com/user-attachments/assets/a1581db3-d05d-4afc-b24b-d711a9d3ec62" />





<img width="1241" height="52" alt="b" src="https://github.com/user-attachments/assets/4d482add-5027-4e7d-aabf-3aa4aa92f7c6" />





<img width="739" height="461" alt="c" src="https://github.com/user-attachments/assets/a5709429-8e54-4fa9-990e-aa0c8f6e625a" />






### 7. Preguntas de Control

**1. ¿Por qué es un error metodológico grave aplicar una prueba T para muestras independientes (Tarea 1) en el escenario de la Tarea 2 (evaluación antes/después del firewall en los mismos servidores)? Explique el impacto en el término de covarianza.**

Es un error metodológico grave porque las mediciones "antes" y "después" provienen de las mismas unidades de observación (los mismos servidores), por lo que son datos dependientes. Aplicar una prueba independiente asume erróneamente que la covarianza entre los grupos es nula ($Cov(X_1, X_2) = 0$). Al ignorar la covarianza positiva típica de las muestras pareadas, se infla artificialmente el error estándar de la diferencia, restándole sensibilidad estadística a la prueba y aumentando drásticamente la probabilidad de cometer un Error Tipo II (no detectar una mejora real).

**2. Describa matemáticamente y gráficamente qué es la "Prueba T de Welch". ¿Qué parámetro fundamental (calculado a partir de $n$ y la varianza) ajusta esta prueba para evitar cometer Errores Tipo I al comparar distribuciones muy dispares?**

Matemáticamente, la Prueba T de Welch es una adaptación de la T de Student que no exige el supuesto de homocedasticidad poblacional ($\sigma_1^2 \neq \sigma_2^2$). Gráficamente, permite comparar de forma fiable los centros de dos distribuciones (curvas de densidad) que presentan niveles de dispersión o achatamiento radicalmente distintos. Para evitar Errores Tipo I, esta prueba ajusta dinámicamente los **grados de libertad** ($\nu$) mediante la aproximación de Welch-Satterthwaite, calculándolos a partir de las varianzas muestrales ($s_1^2, s_2^2$) y los tamaños de muestra ($n_1, n_2$) de cada grupo.

**3. En el análisis de su Proyecto Integrador (Tarea 3), si el Intervalo de Confianza para la diferencia de medias ($\mu_1-\mu_2$) incluyera al número cero ($0$), ¿cuál sería inevitablemente el resultado de su prueba de hipótesis usando $\alpha=0.05$?**

El resultado inevitable sería que **NO se rechaza la Hipótesis Nula ($H_0$)**. Si el valor $0$ está contenido dentro del intervalo de confianza del $95\%$, significa que existe una probabilidad estadísticamente admisible de que la diferencia real entre las medias poblacionales sea nula ($\mu_1 = \mu_2$).

**4. Según lo investigado en la Tarea 4 (ABI), si el Test de Levene arroja un $valor\text{-}p=0.85$ ¿cuál es la conclusión estadística respecto a las varianzas y qué versión del Test T debería usar?**

Dado que el $valor\text{-}p=0.85$ es superior al nivel de significancia ($\alpha = 0.05$), la conclusión es que no hay evidencia para rechazar la igualdad de varianzas, confirmando el supuesto de **Homocedasticidad**. Por lo tanto, se debe utilizar la **Prueba T de Student clásica** (en código, pasando el parámetro `equal_var=True`).

**5. En el mundo real del Data Science, ¿cómo difiere el concepto estadístico clásico enseñado hoy frente a la ejecución comercial de un "A/B Testing" en plataformas web (ej. comparar el color de un botón de compra)?**

El enfoque estadístico clásico suele centrarse en el cumplimiento estricto de supuestos teóricos (normalidad, homocedasticidad) sobre muestras limitadas y estáticas. En el Data Science comercial aplicado a plataformas web, el A/B Testing se ejecuta sobre flujos masivos de datos (Big Data). Con tamaños de muestra ($n$) tan grandes, casi cualquier mínima disparidad generará un $valor\text{-}p < 0.05$. Por ende, la ejecución comercial difiere en que ya no busca solo la "significancia estadística", sino que prioriza la **relevancia práctica** o magnitud del efecto, evaluando si el cambio genera un impacto real y rentable en el negocio (ej. aumento del ROI o tasa de conversión).
