# Foro 2 — Comentarios a Posts de Compañeros
**Diplomado IA aplicada a la Gestión de Personas — Call Co.**

---

## Comentario 1

**Post comentado:** Compañero que propone división 60-70% entrenamiento / datos recientes como prueba, discriminación indirecta por antecedentes penales, y grupo de control para el software con cita de asignación aleatoria de llamadas.

Comparto el enfoque general de las tres respuestas. En particular, me parece muy bien fundamentada la pregunta 2 — el mecanismo explicado es claro: la variable de antecedentes penales no mide solo comportamiento real, sino también la intensidad del control policial sobre ciertos grupos, y el modelo reproduce ese sesgo histórico amplificándolo en cada decisión futura.

Respecto a la pregunta 1, agregaría un elemento que considero clave: el corte temporal no debería ser solo "datos históricos vs. recientes", sino específicamente **a partir de agosto de 2021**, cuando la empresa implementó su encuesta formal de preselección (Clase 3, p. 5). Los datos anteriores corresponden a un proceso de contratación distinto, sin Testscore, por lo que mezclarlos haría que el modelo aprendiera patrones contradictorios. Además, faltaría considerar que la base solo registra resultados de candidatos **contratados** — quienes fueron rechazados no tienen datos de desempeño, lo que genera sesgo de selección al entrenar el modelo (Clase 4, p. 20).

En la pregunta 3 me parece un acierto aprovechar la asignación aleatoria de llamadas que ya existe en la empresa como argumento a favor de un buen diseño experimental. Añadiría que el seguimiento debería extenderse a **6 meses**, que es el horizonte mínimo en que el desempeño se estabiliza según la Clase 3 (p. 7-8), no solo por la curva de aprendizaje del software, sino porque ese es el estándar de medición de la propia empresa.

---

## Comentario 2

**Post comentado:** Compañero que menciona división 60/40, discriminación por investigaciones sin condena, y pruebas del software en todos los centros con variables adicionales para correlación/causalidad.

Buen análisis en las tres preguntas. Destaco especialmente el matiz de la pregunta 2: señalar que los antecedentes incluyen **investigaciones sin condena** es un punto importante que refuerza el argumento — la variable es aún menos objetiva cuando ni siquiera existe un veredicto, lo que amplifica el riesgo de discriminación indirecta contra grupos que son detenidos y registrados con mayor frecuencia sin que eso derive en una condena real.

En la pregunta 1 agregaría que, además del criterio de división 60/40 mencionado, hay un corte específico relevante: los datos anteriores a **agosto de 2021** no son comparables con el proceso actual porque la empresa no tenía encuesta de preselección ni Testscore antes de esa fecha (Clase 3, p. 5). Mezclarlos con los datos actuales haría que el modelo aprendiera dos procesos de contratación distintos.

En la pregunta 3 comparto la recomendación de probar en múltiples centros para asegurar representatividad. Añadiría que el elemento más crítico que falta en el plan original es un **grupo de control** — sin él, no es posible separar el efecto del software de otros cambios que ocurran en paralelo durante esos 3 meses. Evaluar variables adicionales, como sugieres, ayuda a controlar factores de confusión, lo que va en la misma dirección del protocolo de regresión multivariada de la Clase 4 (p. 7, Paso 4).

---

## Referencias

Bojilov, R. (2024). *Clase 3: Evaluación de herramientas analíticas: análisis descriptivo*. Diplomado en Inteligencia Artificial aplicada a la Gestión de Personas. Pontificia Universidad Católica de Chile.

Bojilov, R. (2024). *Clase 4: Evaluación de Herramientas Analíticas: Regresiones*. Diplomado en Inteligencia Artificial aplicada a la Gestión de Personas. Pontificia Universidad Católica de Chile.
