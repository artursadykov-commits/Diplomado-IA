# Control 4 — Preguntas y Respuestas
**Clases 3 y 4 — Diplomado IA aplicada a la Gestión de Personas**

---

## Pregunta 1
Considere la regresión no lineal simple de la variable dependiente en los deciles de la variable independiente de interés principal y otras variables independientes. ¿Cómo se definen las variables del tipo indicador que corresponden a los deciles de la variable independiente?

- a. El indicador toma el valor 1 si, para una observación determinada, la variable independiente tiene su valor en el decil correspondiente o en un uno de los deciles precedente, y 0 en caso contrario.
- b. El indicador toma el valor de la variable independiente asociada con una observación determinada si la variable independiente tiene su valor en el decil correspondiente, y 0 en caso contrario.
- c. El indicador toma el valor de la variable independiente asociada con una observación determinada si la variable independiente tiene su valor en el decil correspondiente, y el indicador no se define para los otros deciles.
- d. El indicador toma el valor 1 si, para una observación determinada, la variable dependiente tiene su valor en el decil correspondiente, y 0 en caso contrario.
- **e. El indicador toma el valor 1 si, para una observación determinada, la variable independiente tiene su valor en el decil correspondiente, y 0 en caso contrario. ✅**

**Fundamento:** Clase 4 (p. 7-8, Paso 5): "un indicador que toma el valor 1 si, para una observación determinada, la variable explicativa asociada tiene su valor en el decil correspondiente, y 0 en caso contrario." La opción a es incorrecta porque agrega "o en uno de los deciles precedentes."

---

## Pregunta 2
Considere la regresión lineal múltiple de la variable dependiente en la variable independiente de interés principal y otras variables independientes. ¿Por qué se incluyen las variables independientes adicionales?

- a. Para mejorar la precisión de la estimación del coeficiente de la variable independiente de interés principal.
- b. Para mejorar el coeficiente de la variable independiente de interés principal.
- c. Para mejorar el R-cuadrado de la regresión.
- d. Para reducir el riesgo de sesgo por selección.
- **e. Para reducir el riesgo de sesgo por variable omitida. ✅**

**Fundamento:** Clase 4 (p. 7, Paso 4): "La inclusión de todas las variables explicativas adicionales plausibles reduce el riesgo de este problema, conocido como sesgo por variable omitida." Si se omiten, quedan en el término de error, correlacionándose con la variable principal y violando los supuestos del modelo.

---

## Pregunta 3
¿Cuál es la afirmación que NO es parte del protocolo para la implementación del análisis de regresión?

- a. El protocolo incluye la regresión lineal de la variable dependiente en la variable independiente de interés principal.
- **b. El protocolo incluye el análisis de la correlación entre la variable dependiente y la variable independiente de interés principal. ✅**
- c. El protocolo incluye la regresión lineal de la variable dependiente en los deciles (o quintiles, etc.) de la variable independiente de interés principal.
- d. El protocolo incluye la regresión lineal de la variable dependiente en los deciles (o quintiles, etc.) de la variable independiente de interés principal y otras variables independientes que podrían impactar la variable dependiente.
- e. El protocolo incluye la regresión lineal de la variable dependiente en la variable independiente de interés principal y otras variables independientes que podrían impactar la variable dependiente.

**Fundamento:** El protocolo de la Clase 4 (p. 7-8) incluye: análisis visual, división entrenamiento/prueba, regresión lineal simple, regresión multivariada, regresión no lineal simple, regresión no lineal multivariada, evaluación de calidad y resumen. El análisis de correlación corresponde a la Clase 3, no al protocolo de regresión.

---

## Pregunta 4
Considere la regresión no lineal simple de la variable dependiente en los deciles de la variable independiente de interés principal y otras variables independientes. La categoría de referencia (el decil omitido) es el decil 1. ¿Cuál es el efecto de un valor de la variable independiente en decil 1?

- a. Es igual al coeficiente del constante.
- b. Es igual a 0.
- c. Es igual al promedio de los coeficientes de los otros deciles.
- **d. Se incorpora en el coeficiente del constante. ✅**
- e. Se incorpora en el coeficiente de cada uno de los otros deciles.

**Fundamento:** Clase 4 (p. 13-14): "La exclusión de [la categoría de referencia] de la regresión implica que su efecto está capturado por la constante." El efecto del decil 1 queda absorbido en la constante, no es un coeficiente separado.

---

## Pregunta 5
Considere la regresión lineal simple de la variable dependiente en los deciles de la variable independiente de interés principal y otras variables independientes. ¿Cómo se interpreta el coeficiente del decil 10 cuando la categoría de referencia (el decil omitido) es el decil 1?

- a. El coeficiente representa el efecto de un valor de la variable independiente en decil 10.
- **b. El coeficiente representa el efecto de un valor de la variable independiente en decil 10 relativo al efecto de un valor de la variable independiente en el decil 1. ✅**
- c. El coeficiente representa el efecto de un valor de la variable independiente en decil 10 relativo al efecto de un valor de la variable independiente en el decil 9.
- d. El coeficiente representa el efecto de un valor de la variable independiente en decil 10 relativo al efecto promedio de la variable independiente.
- e. El coeficiente representa el efecto de un valor de la variable independiente en el decil 10, en relación con la suma de la constante estimada y del efecto de un valor de la variable independiente en el decil 1.

**Fundamento:** Clase 4 (p. 13): "Los coeficientes del resto de las categorías se interpretan de forma relativa respecto a esta categoría de referencia [decil 1]." Siempre es relativo al decil omitido, no al decil anterior ni al promedio.

---

## Pregunta 6
¿Cuál es el valor añadido del análisis de regresión en comparación con el análisis descriptivo?

- a. El análisis de regresión estima la relación de interés en una manera que nos da la oportunidad de evaluar el impacto de cambios significativos en el entorno.
- b. El análisis de regresión estima la relación de interés eliminando supuestos restrictivos.
- c. El análisis de regresión estima la relación de interés sin la necesidad de mantener supuestos técnicos.
- d. El análisis de regresión estima la relación de interés utilizando mejores y más avanzados métodos.
- **e. El análisis de regresión permite estimar la relación de interés, así como la precisión de dicha relación y la calidad de la estimación, controlando el efecto de otras variables explicativas. ✅**

**Fundamento:** Clase 4 (p. 5-6) lista tres ventajas: (1) controla por otras variables explicativas, (2) estima la precisión del coeficiente, (3) entrega medidas de calidad de la aproximación (R²). La opción e captura las tres ventajas.

---

## Pregunta 7
Considere la regresión no lineal del desempeño en los deciles de Testscore y otras variables explicativas, presentada en Tabla 4 de la clase. La categoría de referencia (el decil omitido) es el decil 1. Los deciles 2 a 10 de Testscore no son significativos estadísticamente y los coeficientes asociados están cerca de cero. ¿Cómo es la interpretación incorrecta de estos resultados?

- a. Los deciles de Testscore no pueden explicar las variaciones el desempeño.
- b. Testscore no tiene efecto sobre el desempeño.
- **c. Solo la categoría de referencia, el decil 1, tiene un efecto significativo. ✅**
- d. Los deciles 2 a 10 de Testscore tienen el mismo efecto sobre el desempeño.
- e. Los aumentos en Testscore no provocan cambios (aumentos) en el desempeño.

**Fundamento:** La interpretación incorrecta es la c. El decil 1 es la categoría de referencia y su efecto queda absorbido por la constante — no tiene un efecto "significativo" por sí solo. Lo que los resultados indican es que ningún decil tiene efecto diferencial sobre el desempeño respecto al decil 1, es decir, Testscore no tiene efecto sobre el desempeño.

---

## Pregunta 8
Si el proceso de estimación ha de ser válido, la aplicación de modelos analíticos más avanzados, como las regresiones lineales y no lineales:

- a. Requiere muchos recursos de computación.
- **b. Requiere que se cumplan ciertos supuestos teóricos. ✅**
- c. Requiere el monitoreo continuo de los analistas.
- d. Requiere a veces la retroalimentación humana.
- e. Requiere mucho tiempo para su ejecución.

**Fundamento:** Clase 4 (p. 5-6): "La aplicación de modelos analíticos más avanzados, como las regresiones lineales y no lineales, requiere que se cumplan ciertos supuestos teóricos, si el proceso de estimación ha de ser válido."

---

## Pregunta 9
En la aplicación del análisis de regresión, no se recomienda:

- a. Probar los supuestos que se requieren para la estimación válida de la regresión.
- b. Alcanzar los objetivos del proyecto analítico con el menor nivel posible de complejidad técnica.
- c. Usar su sentido común para evaluar los resultados.
- **d. Implementar los métodos de estimación más avanzados para asegurar la calidad de la estimación. ✅**
- e. Usar estadísticas descriptivas y análisis visual para llegar a un conjunto preliminar de resultados.

**Fundamento:** Clase 4 (p. 5-6): "Mantén el análisis lo más simple posible... Solo argumentos muy sólidos deberían convencerle de avanzar hacia métodos estadísticos más exóticos y avanzados." Lo recomendado es lo opuesto a la opción d.

---

## Pregunta 10
Indique la afirmación incorrecta:

- a. El análisis de regresión proporciona diversas medidas de la calidad de la aproximación de la relación.
- b. El análisis de regresión es válido si se cumplan ciertos supuestos teóricos.
- c. El análisis de regresión limita el riesgo de sesgo de variable omitida por la inclusión de otras variables independientes que podrían impactar la relación de interés.
- **d. El análisis de regresión reporta automáticamente las pruebas de los supuestos que se requieren para la estimación válida. ✅**
- e. En el análisis de regresión se estima la precisión de la relación, controlando por el efecto de otras variables explicativas plausibles.

**Fundamento:** La afirmación incorrecta es la d. Clase 4 (p. 5-6): "Con frecuencia, presionados por la necesidad de obtener resultados rápidamente, los analistas no verifican estos supuestos. A veces, los supuestos son tan técnicos y abstractos que, en la práctica, no se pueden verificar." El análisis de regresión NO reporta automáticamente las pruebas de supuestos.

---

## Resumen de Respuestas

| Pregunta | Respuesta |
|----------|-----------|
| 1 | e |
| 2 | e |
| 3 | b |
| 4 | d |
| 5 | b |
| 6 | e |
| 7 | c |
| 8 | b |
| 9 | d |
| 10 | d |
