# Foro 2 — Respuestas Desarrolladas
**Diplomado IA aplicada a la Gestión de Personas — Call Co.**

---

## Pregunta 1: ¿Utilizaría toda la base de datos para predecir la probabilidad de retención de nuevos candidatos?

**No utilizaría toda la base de datos.** Hacerlo sin una selección cuidadosa introduciría sesgos que deteriorarían la calidad del modelo predictivo. Existen tres razones fundamentales:

### Razón 1 — Datos anteriores a agosto 2021 corresponden a un régimen distinto

La Clase 3 (p. 5) establece que "la empresa instituyó la versión actual de su encuesta formal de preselección en agosto de 2021." Antes de esa fecha no existía el Testscore ni la encuesta diagnóstica de 50 preguntas. Los datos de ese período corresponden a un proceso de contratación completamente distinto, con criterios diferentes de selección. Mezclar ambos regímenes en un mismo modelo haría que el algoritmo aprendiera patrones contradictorios, reduciendo su capacidad predictiva sobre candidatos actuales.

### Razón 2 — Datos de países distintos sesgan el modelo

Call Co opera en centros ubicados en Santiago, Buenos Aires, Madrid y otras ciudades. La Clase 3 (p. 5-6) describe un contexto laboral muy específico: deudas pequeñas, exigencia de pago total, tasa de cobro mensual del 93% y asignación aleatoria de llamadas. Estas condiciones operativas y del mercado laboral no son idénticas entre países. Entrenar un modelo con datos de Madrid y aplicarlo en Santiago significaría usar patrones de retención de un mercado laboral con distinta legislación, cultura organizacional y perfil de candidatos. Lo correcto es construir modelos separados por mercado, o al menos controlar por país mediante variables indicadoras.

### Razón 3 — Sesgo de selección: el problema más importante

Este es el punto más técnico y más crítico. La Clase 4 (p. 20) advierte explícitamente: *"nuestro análisis se centra en la relación entre Testscore y el desempeño solo para los empleados de largo plazo. Con base en esto, no podemos extrapolar y concluir que Testscore tampoco esté relacionada con el desempeño en la población de candidatos."*

La base de datos de Call Co solo registra resultados (retención, desempeño) de personas que fueron contratadas. Nunca sabemos qué habría ocurrido con los candidatos rechazados. Si el modelo aprende exclusivamente de los contratados, tiene una visión parcial del universo de candidatos posibles. La Figura 3 de la Clase 4 (p. 20) ilustra este problema: al filtrar candidatos por Testscore antes de la contratación, eliminamos de la base a quienes podrían haber mostrado buen desempeño. Aplicar ese modelo sesgado a nuevos candidatos produce predicciones incorrectas.

### ¿Qué submuestra utilizar?

Siguiendo el protocolo de la Clase 4 (p. 7, Paso 2), la submuestra correcta sería:
- Solo datos **post agosto de 2021** (mismo régimen de Testscore y proceso de selección)
- Solo datos del **mercado local** donde se aplicará el modelo predictivo
- Dividida en **60% muestra de entrenamiento** y **40% muestra de prueba**

La Clase 4 (p. 7) justifica esta división: *"la idea detrás es utilizar la muestra de entrenamiento como 'datos disponibles del pasado' para estimar la relación, y luego aplicar el modelo estimado a los 'datos futuros' representados por la muestra de prueba."* Esto permite detectar si el modelo sobreajusta los datos históricos y garantiza que su desempeño se evalúe sobre datos que no participaron en la estimación.

---

## Pregunta 2: ¿Por qué el uso de antecedentes penales puede provocar discriminación contra grupos minoritarios y personas pobres?

El uso de antecedentes penales genera **discriminación estadística indirecta** a través de tres pasos encadenados:

### Paso 1 — Los antecedentes penales no miden solo comportamiento

Si la policía detiene y registra desproporcionadamente a personas de grupos minoritarios y de bajos ingresos, entonces tener antecedentes penales no refleja únicamente si alguien cometió una infracción — también refleja cuánto fue vigilado. Un candidato de un grupo minoritario puede tener antecedentes por el mismo comportamiento que un candidato de otro grupo que nunca fue detenido. La variable "antecedentes penales" es un *proxy* contaminado: recoge la señal real (comportamiento del candidato) más un ruido sistemático (sesgo en la acción policial).

Esto conecta con la advertencia de la Clase 4 (p. 7), que señala que las variables explicativas deben controlar factores que "pueden estar correlacionadas con las herramientas analíticas" pero que no representan genuinamente lo que queremos medir. Incluir una variable contaminada en el modelo produce estimaciones sesgadas por definición.

### Paso 2 — Los datos del call center evidencian discriminación sistémica preexistente

La Clase 4 (p. 24-25) entrega evidencia empírica directa en la regresión multivariada de retención (Tabla 6): el coeficiente del indicador racial "Negro" es **0.082** con **p = 0.002**, estadísticamente significativo. Bojilov interpreta: *"este coeficiente sugiere la presencia de discriminación contra las personas negras en el mercado laboral local."* Si grupos minoritarios ya enfrentan barreras externas al proceso de contratación, agregar un filtro de antecedentes penales que los afecta desproporcionadamente amplifica esa discriminación dentro de la empresa.

### Paso 3 — El modelo aprende y perpetúa el sesgo histórico

La Clase 4 (p. 5-6) explica que los modelos de regresión y machine learning estiman relaciones *en los datos disponibles*. Si los datos históricos reflejan que candidatos con antecedentes penales (mayoritariamente de grupos minoritarios) fueron rechazados o mostraron peores resultados —no necesariamente por menor capacidad, sino por haber sido discriminados en el proceso anterior— el modelo aprende esa asociación y la aplica a futuros candidatos. El algoritmo no distingue entre causalidad real y correlación espuria producida por discriminación pasada.

Bojilov (Clase 4, p. 5) recomienda aplicar siempre *"pruebas de sentido común: ¿Tienen sentido los resultados? ¿Corroboran su intuición?"* En este caso, la intuición ética y estadística debería alertar que rechazar candidatos por antecedentes penales en contextos de vigilancia policial sesgada no constituye una medición válida de su potencial como empleados.

**Recomendación:** excluir los antecedentes penales del modelo, o realizar previamente un análisis de *disparate impact* para verificar si su inclusión genera tasas de rechazo desproporcionadas en grupos protegidos.

---

## Pregunta 3: ¿Es un buen plan medir el efecto del software con 500 trabajadores antes y después en un solo centro?

**No. El plan tiene cuatro fallas metodológicas graves**, todas identificables desde el marco teórico de las Clases 3 y 4:

### Falla 1 — Sin grupo de control no hay causalidad

La Clase 4 (p. 5-6) es explícita: el análisis de regresión existe porque *"la relación se estima controlando por el efecto de muchas otras variables explicativas."* Un diseño antes/después sin grupo de control no puede separar el efecto del software de otros cambios ocurridos durante esos 3 meses: nuevos supervisores, estacionalidad de llamadas, cambios de política interna, entre otros. Cualquier variación en productividad podría atribuirse erróneamente al software.

La Clase 3 (p. 9) también advierte: *"si los analistas encuentran resultados significativos después de aplicar herramientas avanzadas, entonces, como gerentes, están justificados para dudar del origen del resultado."* Con este diseño deficiente, incluso si la productividad sube, no habría certeza de que el software sea la causa.

### Falla 2 — Un solo centro no es representativo

La Clase 4 (p. 7, Paso 7) enfatiza la importancia de evaluar la calidad del modelo sobre datos fuera de muestra, precisamente para verificar que los resultados se generalizan. El mismo principio aplica al diseño experimental: si el estudio se realiza en un único centro de los 10 existentes, las condiciones particulares de ese centro (tipo de clientes, perfil de supervisores, horarios) pueden contaminar los resultados e impedir su generalización al resto de la empresa.

### Falla 3 — 3 meses puede ser insuficiente

La Clase 3 (p. 7-8) establece que la empresa mide el desempeño cada 3 meses y utiliza el **promedio de los primeros 6 meses** como indicador principal, porque *"también coincide con el horizonte temporal en el que la tasa de separación de empleados se estabiliza."* Si 6 meses es el horizonte mínimo para que el desempeño sea representativo y estable, evaluar el impacto del software en la mitad de ese período puede capturar únicamente la curva de aprendizaje inicial, no el efecto real en régimen de operación normal.

### Falla 4 — Sesgo por variable omitida

La Clase 4 (p. 7, Paso 4) advierte sobre el **sesgo por variable omitida**: si existen variables que afectan la productividad y están correlacionadas con el uso del software (por ejemplo, si los 500 trabajadores seleccionados son los más productivos o los más motivados), el efecto estimado del software estará sesgado. Bojilov señala: *"si las omitimos de la regresión y las dejamos en el término de error, entonces nuestra variable explicativa principal y el error estarán correlacionados"*, violando un supuesto fundamental del análisis.

### Mejoras propuestas

Siguiendo el protocolo de análisis de la Clase 4 (p. 7-8) y el estándar de desempeño de la Clase 3 (p. 7-8):

| Mejora | Fundamento |
|--------|-----------|
| **Asignación aleatoria** dentro de cada centro (grupo tratamiento vs. control) | Garantiza que las diferencias se atribuyan al software, no a características previas (Clase 4, p. 7) |
| **Múltiples centros** (al menos 3-4) | Asegura representatividad y generalizabilidad de los resultados |
| **6 meses de seguimiento** | Consistente con el horizonte de medición de desempeño de la empresa (Clase 3, p. 7) |
| **Índice de desempeño compuesto** (deuda cobrada, tiempo de llamada, adherencia, calidad) | Usa el mismo indicador multidimensional que ya emplea Call Co (Clase 3, p. 7-8) |
| **Análisis de diferencias en diferencias (DiD)** | Controla por tendencias previas comunes a ambos grupos, aislando el efecto del software |

La Clase 4 (p. 5) resume bien el espíritu de esta propuesta: *"mantén el análisis lo más simple posible; esfuérzate por alcanzar los objetivos del proyecto analítico con el menor nivel posible de complejidad técnica."* Un experimento aleatorio controlado bien diseñado es, en este caso, la opción más simple y más robusta para responder la pregunta causal de María José.

---

## Referencias

Bojilov, R. (2024). *Clase 3: Evaluación de herramientas analíticas: análisis descriptivo*. Diplomado en Inteligencia Artificial aplicada a la Gestión de Personas. Pontificia Universidad Católica de Chile.

Bojilov, R. (2024). *Clase 4: Evaluación de Herramientas Analíticas: Regresiones*. Diplomado en Inteligencia Artificial aplicada a la Gestión de Personas. Pontificia Universidad Católica de Chile.

Barr, T.; Bojilov, R.; Munasinghe, L. (2020). "Referrals and Search Efficiency: Who Learns What and When?" *Journal of Labor Economics*, Vol. 37(4), pp. 1009–1059.

Cameron, C.; Trivedi, P. (2006). *Microeconometrics*. Cambridge University Press.

---

*Nota de transparencia: Este documento fue elaborado con apoyo de Claude (Anthropic, 2025) como herramienta de redacción y estructuración. El análisis conceptual y las referencias académicas fueron verificados por el autor en base a los materiales del curso.*
