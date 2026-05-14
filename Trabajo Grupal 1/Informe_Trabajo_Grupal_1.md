# Proyecto Grupal: Uso de la inteligencia artificial en la gestión de personas

**Empresa analizada:** Call Co.
**Herramienta Analítica:** Testscore

---

## ETAPA I: Análisis Descriptivo

En base a la Tabla 1 del caso, se analizan los promedios incondicionales y condicionales a través de los 10 deciles de Testscore:

### 1. Impacto sobre el Desempeño
**a. ¿El desempeño aumenta a medida que aumentan los deciles?**
No. El desempeño fluctúa de manera no monótona a lo largo de los deciles (entre 2.85 y 3.14). Por ejemplo, el decil 1 tiene un promedio de 3.01, el decil 5 tiene 3.10, y el decil 10 baja a 2.97.

**b. Interpretación económica:**
La herramienta Testscore no tiene capacidad predictiva sobre el desempeño real del trabajador en el puesto. Contratar a un candidato con Testscore alto no garantiza un mejor desempeño productivo en el Call Center en comparación con uno de bajo puntaje. Este resultado es consistente con la correlación de -0.02 entre Testscore y Desempeño reportada en la Tabla 2 de Bojilov (Clase 3, p. 13), donde se concluye que "no detectamos ninguna correlación entre Testscore y Desempeño". La Tabla 5 (Clase 3, p. 24) confirma que para todos los deciles el desempeño promedio se mantiene "alrededor de 3 o justo por debajo de este valor", sin tendencia positiva asociada al Testscore.

### 2. Impacto sobre la Retención Condicional
**a. ¿La tasa de retención condicional aumenta a medida que aumentan los deciles?**
No, de hecho se observa un fenómeno contrario. Los deciles más bajos (1 y 2) presentan tasas de retención condicional más altas (60% y 56%), mientras que los deciles del 4 al 10 se estancan entre 34% y 39%.

**b. Interpretación económica:**
Económicamente, los candidatos con menores puntajes en Testscore (que habitualmente son descartados), si logran ser contratados, tienden a permanecer más tiempo en la empresa. La herramienta falla en su objetivo principal que era reducir la rotación a largo plazo priorizando puntajes altos. La Tabla 5 de Bojilov (Clase 3, p. 24) muestra exactamente este patrón: la retención condicional del Decil 1 es 0.600, mientras que la del Decil 10 cae a 0.351. Bojilov concluye que "si existe alguna rotación no aleatoria posterior a la contratación, no está impulsada por diferencias en el Testscore" (Clase 3, p. 24), y que "la herramienta analítica Testscore tiene su mayor y único impacto en los resultados de contratación a través de su efecto en la selección de candidatos para ser entrevistados" (Clase 3, p. 24).

### 3. Impacto sobre la probabilidad de tener un Título Senior (Ascenso)
**a. ¿La probabilidad de un ascenso aumenta a medida que aumentan los deciles?**
No. La probabilidad varía aleatoriamente entre los deciles, por ejemplo, el decil 1 tiene un 20% de probabilidad, el decil 3 un 32%, y el decil 10 cae a 14%.

**b. Interpretación económica:**
Los ascensos (que implican un cargo y salario superior) no guardan correlación con el puntaje Testscore obtenido en la contratación. Esto es coherente con el diseño institucional descrito por Bojilov (Clase 3, p. 8), donde "las decisiones de promoción son tomadas por un comité de supervisores que generalmente no participan en las entrevistas y decisiones de contratación de sus futuros subordinados", lo que por diseño desvincula el Testscore del proceso de ascenso.

---

## ETAPA II: Análisis de Regresión

En esta etapa se controla por factores observables adicionales para aislar el impacto real del Testscore respecto a un grupo base (Decil 1).

### 1. Efecto sobre el Desempeño (Tabla 3)
**a. Comportamiento de coeficientes:** Los coeficientes no aumentan con los deciles, oscilan entre valores negativos y positivos sin una tendencia clara (ej: Decil 4 es -0.111, Decil 8 es 0.201, Decil 10 es 0.040).

**b. Significancia estadística:** Ninguno de los coeficientes es estadísticamente significativo al nivel del 5% ($p > 0.05$ en todos los deciles, con valores desde 0.645 a 0.968).

**c. Importancia económica:** Al no ser significativos estadísticamente, podemos asumir que el efecto del Testscore sobre el desempeño es cero. Este resultado replica exactamente lo encontrado en el análisis de regresión no lineal simple de Bojilov (Clase 4, Tabla 3, p. 16-17), donde se concluye que "ninguno de los deciles 2 a 10 tiene un efecto en el desempeño significativamente diferente del efecto de Testscore en el primer decil". La regresión no lineal multivariada (Clase 4, Tabla 4, p. 17-18) confirma que "la introducción de variables explicativas adicionales no genera cambios en el efecto estimado de Testscore sobre el desempeño: Testscore sigue sin tener ningún efecto sobre el desempeño."

### 2. Efecto sobre la Retención Condicional (Tabla 2)
**a. Comportamiento de coeficientes:** No aumentan a medida que crecen los deciles. Por el contrario, todos los coeficientes son negativos frente a la categoría de referencia (decil 1), fluctuando entre -0.084 y -0.294.

**b. Significancia estadística:** Varios deciles (4, 5, 6, 7, y 10) tienen significancia estadística débil (p-value cercano o menor a 0.10, y el decil 10 tiene $p=0.054$). Esto reafirma la confianza estadística de que los deciles altos retienen *menos* que el decil base.

**c. Importancia económica:** El efecto negativo (hasta casi un -0.30 en probabilidad) es económicamente altísimo dado que la probabilidad base promedio de la empresa es cercana al 0.36. Significa que los deciles altos reducen drásticamente la probabilidad de retención respecto al decil 1. La Tabla 7 (Clase 4, p. 26) refuerza este hallazgo: en la regresión no lineal simple, todos los coeficientes de los deciles de Testscore sobre la retención condicional son negativos y ninguno alcanza significancia estadística al 5%, lo que "confirma que no existe una relación positiva sólida entre la retención de los empleados recién contratados y Testscore" (Clase 4, p. 23).

### 3. Efecto sobre la probabilidad de tener un Título Senior (Tabla 4)
**a. Comportamiento de coeficientes:** Oscilan alrededor de cero (desde 0.061 a -0.032) y no aumentan monótonamente.

**b. Significancia estadística:** Completamente nula. Todos los valores $p$ son inusualmente altos (0.659 a 0.935). No se puede rechazar la hipótesis de que los coeficientes son cero.

**c. Importancia económica:** Económicamente el Testscore es irrelevante para predecir qué empleado obtendrá un ascenso. Este resultado es consistente con el protocolo de regresión presentado en Bojilov (Clase 4, p. 7-8), que establece que un coeficiente es significativo cuando $p < 0.05$ y el estadístico $t > 2$.

---

## ETAPA III: Prueba de Discriminación

Al comparar el modelo de la Tabla 4 con el de la Tabla 5, que incluye la variable "Desempeño" observada al momento del ascenso:

### 1. Efecto del desempeño sobre la probabilidad de ascenso (Tabla 5)
**a. Efecto positivo:** Sí, el coeficiente es de 0.059, lo cual es positivo.
**b. Significancia estadística:** Altamente significativo ($p = 0.000$).
**c. Importancia económica:** Por cada punto adicional de desempeño que un empleado obtiene en sus primeros seis meses (en una escala de 0 a 8), sus chances de obtener un título senior aumentan en casi un 6%.

### 2. Efecto de los deciles de Testscore controlando por desempeño (Tabla 5)
**a. Cambio de coeficientes:** Los coeficientes permanecen prácticamente idénticos a los observados en la Tabla 4 (ej. Decil 10 pasó de -0.029 a 0.007).
**b. Significancia estadística:** Siguen siendo estadísticamente no significativos ($p$ entre 0.656 y 0.976).
**c. Importancia económica:** Siguen sin tener ningún impacto en la probabilidad real de ascenso.

### 3. ¿Hay discriminación estadística en el call center?
Para que exista discriminación estadística en los ascensos, la Tabla 4 debería haber mostrado un efecto positivo y significativo de los deciles de Testscore sobre el ascenso (porque los gerentes usarían la prueba como un *proxy* del desempeño real no observable). Y luego, en la Tabla 5, al incluir el verdadero desempeño, ese efecto del Testscore debería haber desaparecido.

**Resultado:** Como la Tabla 4 nunca mostró un efecto positivo del Testscore en las promociones desde el inicio, podemos concluir que **no existe discriminación estadística** al momento de decidir las promociones. Los encargados de promoción basan sus decisiones en el desempeño real, ignorando la puntuación de Testscore. Bojilov (Clase 4, p. 24) confirma que el desempeño sí tiene un efecto estadísticamente significativo sobre la retención y las promociones: "una experiencia específica de entre 2 y 5 años aumenta la probabilidad de retención en 0.11 respecto a la categoría de referencia", lo que indica que las decisiones internas responden a criterios productivos observables, no al Testscore.

### 4. ¿Hay discriminación por preferencia?
Para que exista discriminación por preferencia, el Testscore debería beneficiar los ascensos independientemente del desempeño real del trabajador (es decir, mostrar coeficientes positivos tanto en la Tabla 4 como en la Tabla 5).

**Resultado:** Como los deciles de Testscore no son significativos ni ayudan a la probabilidad de promoción en ninguno de los dos escenarios, **no hay discriminación por preferencia** en las promociones en Call Co.

---

## RECOMENDACIONES FINALES

**1. Evaluación sobre la Discriminación**
Basados en el análisis empírico formal, **no hay indicios de discriminación (ni estadística ni por preferencia) en la etapa de promoción de los empleados**. Las promociones dentro de Call Co son meritocráticas en cuanto a que están directamente correlacionadas con el desempeño productivo comprobable de los empleados en sus primeros 6 meses de trabajo, sin que la prueba analítica o el puntaje de selección influya o sesgue esta decisión interna.

**2. Recomendación a la Gerencia sobre Testscore**
Nuestra recomendación es **terminar definitivamente con el uso de la herramienta Testscore en la etapa de pre-selección.** Esta conclusión es consistente con la recomendación explícita de Bojilov (Clase 4, p. 30): "con base en estos hallazgos, no recomendamos continuar utilizando la herramienta analítica Testscore."

* **Razón 1:** Falla en su objetivo principal (la retención). Irónicamente, el modelo demuestra que los candidatos con los peores puntajes de la prueba (decil 1) son los que tienen mayor retención condicional a largo plazo (60%), mientras que aquellos a los que se les da prioridad, abandonan (Bojilov, Clase 3, Tabla 5, p. 24). La correlación entre Testscore y Retención es solo de 0.15, "una mala noticia para nuestra herramienta analítica" (Bojilov, Clase 3, p. 12-13).
* **Razón 2:** Testscore no tiene relación predictiva con el verdadero desempeño laboral productivo. La regresión lineal simple muestra un coeficiente de -0.001 con $p = 0.701$ (Bojilov, Clase 4, Tabla 1, p. 12), y el R-cuadrado ajustado es negativo, confirmando que el modelo no aporta poder predictivo.
* **Razón 3:** Actualmente la empresa está rechazando candidatos de los deciles inferiores que estadísticamente hubieran sido empleados más leales y de igual desempeño a los de los deciles altos. Bojilov (Clase 3, p. 25) señala que "el perfil de contrataciones exitosas se puede encontrar entre los candidatos en el primer decil en términos de su Testscore."

En lugar de parchear esta herramienta, Call Co debería auditar qué características reales comparten los trabajadores que sí permanecen. Bojilov (Clase 4, Tabla 6, p. 24-25) identifica que la **experiencia específica de 2 a 5 años** es el predictor más robusto de retención (coef. = 0.109, $p = 0.005$), y sugiere rediseñar la pre-selección en base a predictores reales derivados de su propia base de datos descriptiva.

---

## Referencias

Barr, T.; Bojilov, R.; Munasinghe, L. (2020). "Referrals and Search Efficiency: Who Learns What and When?" *Journal of Labor Economics*, Vol. 37(4), pp. 1009–1059.

Bojilov, R. (2024). *Clase 3: Evaluación de herramientas analíticas: análisis descriptivo*. Diplomado en Inteligencia Artificial aplicada a la Gestión de Personas. Pontificia Universidad Católica de Chile.

Bojilov, R. (2024). *Clase 4: Evaluación de Herramientas Analíticas: Regresiones*. Diplomado en Inteligencia Artificial aplicada a la Gestión de Personas. Pontificia Universidad Católica de Chile.

Cameron, C.; Trivedi, P. (2006). *Microeconometrics*. Cambridge University Press.

Varian, H. R. (2014). "Big Data: New Tricks for Econometrics." *Journal of Economic Perspectives*, 28(2): 3-28.
