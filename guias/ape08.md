# APE 008 - Intervalos de Confianza (Solo Tarea 1)

**Integrantes:**
* Willan Granda
* Fernando Aguirre
* Darwin Campoverde
* Byron Coronel
* Axel Jimenez
  
**Asignatura:** Teoría de la Distribución y Probabilidad  
**Fecha:** 02 de junio de 2026


import numpy as np
import matplotlib.pyplot as plt
from scipy.stats import norm

# Para que los resultados sean iguales cada vez
np.random.seed(42)

### Explicación de la Tarea 1

Cuando $n \geq 30$ (muestra grande), usamos la distribución **Normal (Z)**.

**Fórmula:**
$$ IC = \bar{x} \pm Z_{\alpha/2} \left( \frac{s}{\sqrt{n}} \right) $$




<img width="485" height="438" alt="cap 1" src="https://github.com/user-attachments/assets/8edd742d-6ec1-4d7e-a7d5-bc4b6a22b42f" />




<img width="698" height="521" alt="cap 2" src="https://github.com/user-attachments/assets/cd68e857-ff05-44d4-aca2-364406ab1254" />




<img width="473" height="525" alt="cap 3" src="https://github.com/user-attachments/assets/0d1284b5-bbc9-43b3-9807-bfe3ff08b528" />




<img width="486" height="523" alt="cap 4" src="https://github.com/user-attachments/assets/660daf1b-035e-4ac8-a39e-d9ab84a7d29f" />




<img width="456" height="506" alt="cap 5" src="https://github.com/user-attachments/assets/a2aaef77-45d7-4040-a0db-4232a9bede60" />




<img width="396" height="475" alt="cap 6" src="https://github.com/user-attachments/assets/7b3facd0-b1b7-4004-9f31-fd4d03e9bd76" />




<img width="533" height="520" alt="cap 7" src="https://github.com/user-attachments/assets/8bdff3f7-b87b-446a-902f-caa253acbfbb" />




### Análisis de Sensibilidad (ABI): El Impacto del Nivel de Confianza ($1-\alpha$)

**1. El efecto balanza: Confianza vs. Precisión**

Como podemos ver claramente en el gráfico de líneas, existe un efecto de balanza (o *trade-off*) entre el Nivel de Confianza y nuestro Margen de Error. Si queremos estar casi totalmente seguros de nuestra estimación (subiendo la confianza al 99%), corremos el riesgo de tener un margen de error mucho más ancho.

Matemáticamente, esto ocurre porque al pedir más certeza, necesitamos cubrir un área más grande bajo la campana de la distribución (ya sea $Z$ o $T$), lo que hace crecer el valor multiplicador en nuestra fórmula, es decir que a mayor seguridad de que el valor real esté en nuestro rango, menor precisión tendremos sobre cuál es ese valor exacto.

**2. ¿Por qué la industria y los proyectos se quedan con el 95%?**

Buscar el 99% de certeza sería lo ideal. Sin embargo, en la realidad, ese 99% nos da un intervalo tan holgado que el dato pierde su utilidad. Por ejemplo, en un proyecto de emprendimiento regional, de nada nos sirve saber algo con certeza casi absoluta si el rango resultante es tan gigante que no nos permite planificar costos, infraestructuras o recursos operativos.

Ahí es donde entra el 95% como el estándar de oro, nos da un **equilibrio sumamente práctico**: estamos lo suficientemente seguros de nuestro resultado, pero el margen de error sigue siendo pequeño y manejable para tomar decisiones sólidas de negocio. Si seguimos intentando conseguir el 99% pero manteniendo un margen pequeño, la única salida metodológica sería salir a recolectar una cantidad masiva de datos adicionales ($n$), porque esto dispararía los tiempos y costos del proyecto sin ofrecer una mejora que realmente lo justifique.


**PREGUNTAS DE CONTROL**
1. **Defina con precisión técnica la diferencia conceptual entre una estimación puntual y una estimación por intervalos. ¿Por qué la estimación puntual por sí sola es insuficiente en ingeniería?**

Estimación puntual: Es un único valor calculado a partir de la muestra que se utiliza para estimar un parámetro poblacional desconocido (por ejemplo, la media muestral $  \bar{x}  $ como estimador de $  \mu  $). Es un "mejor intento" único.
Estimación por intervalos: Es un rango de valores (intervalo) dentro del cual se espera que se encuentre el parámetro poblacional con un determinado nivel de confianza (ej. 95%).

¿Por qué la estimación puntual es insuficiente en ingeniería?
Porque no proporciona ninguna medida de incertidumbre o precisión. Un solo número ($  \bar{x} = 350  $ kWh) no indica cuán confiable es esa estimación. En ingeniería se toman decisiones críticas (diseño de redes eléctricas, tratamiento de agua, dimensionamiento de equipos, etc.) donde es fundamental conocer el margen de error posible. La estimación por intervalos permite evaluar el riesgo y tomar decisiones más robustas y seguras.

2. **Explique la interpretación frecuentista correcta de un Intervalo de Confianza del 95%. (Evite el error común)**

Si repetimos el proceso de toma de muestra y construcción del intervalo de confianza muchas veces (en teoría infinitas), entonces el 95% de esos intervalos contendrán el verdadero valor del parámetro poblacional ($  \mu  $).
Interpretación práctica (para un intervalo calculado):
Existe un 95% de confianza de que el intervalo que construimos contenga al verdadero parámetro poblacional. No significa que “hay un 95% de probabilidad de que $  \mu  $ esté dentro del intervalo”, porque una vez calculado el intervalo, $  \mu  $ o está dentro o no (es un valor fijo desconocido). La probabilidad se refiere al método de construcción del intervalo, no al intervalo específico.

3. **Al comparar las distribuciones Normal Estándar (Z) y la de Student (t), ¿qué característica visual y matemática de la campana de la t la hace idónea para muestras pequeñas?**

La distribución t de Student tiene:

Colas más pesadas (más anchas) que la distribución Normal.
Un pico más bajo en el centro (menor curtosis en el centro, mayor dispersión en las colas).

Razones matemáticas:

Cuando el tamaño de muestra es pequeño, la estimación de la desviación estándar muestral ($  s  $) es imprecisa.
La distribución t incorpora esta incertidumbre adicional mediante los grados de libertad ($  df = n-1  $).
A medida que $  n  $ aumenta, la distribución t se aproxima a la Normal (Teorema del Límite Central).

Esto hace que los intervalos construidos con t sean más conservadores (más anchos), lo cual es necesario para compensar la falta de información en muestras pequeñas.

4. **Si desea reducir el Margen de Error a la mitad sin disminuir el Nivel de Confianza (95%), ¿qué debe hacer con $  n  $? Apóyese en la fórmula.**

La fórmula del margen de error es:
$$E = z_{\alpha/2} \cdot \frac{s}{\sqrt{n}} \quad \text{(o } t_{\alpha/2} \text{ para muestras pequeñas)}$$
Si queremos que $  E_{nuevo} = \frac{E_{actual}}{2}  $, entonces:
$$\frac{z \cdot s}{\sqrt{n_{nuevo}}} = \frac{1}{2} \cdot \frac{z \cdot s}{\sqrt{n_{actual}}}$$
Simplificando:
$$\sqrt{n_{nuevo}} = 2 \cdot \sqrt{n_{actual}} \quad \Rightarrow \quad n_{nuevo} = 4 \cdot n_{actual}$$
Conclusión: Se debe cuadruplicar el tamaño de la muestra.

5. **Basado en su gráfico de la Tarea 4, ¿qué ocurre con el Intervalo de Confianza si buscamos un 99% de certeza teórica? ¿Tiene esto alguna utilidad analítica real para su proyecto en Loja?**

A medida que aumenta el nivel de confianza (80% → 90% → 95% → 99%), el margen de error aumenta significativamente, haciendo que el intervalo sea mucho más amplio.
Ventajas y desventajas:

Ventaja: Mayor certeza de que el intervalo contiene el verdadero parámetro.
Desventaja: El intervalo pierde precisión y puede volverse tan amplio que pierde utilidad práctica para la toma de decisiones.

En el contexto del proyecto en Loja:

Un intervalo extremadamente ancho (por ejemplo, consumo energético entre 280 y 520 kWh) no ayuda a dimensionar correctamente una red eléctrica o a tomar decisiones de inversión.
Por eso el 95% se considera el estándar en la industria: ofrece un buen compromiso entre confianza y precisión.

