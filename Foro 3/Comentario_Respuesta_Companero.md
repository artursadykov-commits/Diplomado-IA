# Foro 3 — Comentario a respuesta de compañero/a

---

## Comentario

Muy buen análisis. La idea de comparar candidatos en los bordes del umbral se asemeja a un diseño de regresión discontinua (RDD), que en econometría se usa precisamente para identificar efectos causales cuando la asignación depende de cruzar un punto de corte en una variable continua. La fortaleza es que, en el borde, los candidatos son estadísticamente equivalentes, por lo que las diferencias en resultados posteriores son más atribuibles a la acción tomada.

Respecto al sesgo del testscore, el punto es clave: un modelo entrenado sobre empleados retenidos tiene sesgo de supervivencia, ya que excluye a quienes fueron descartados. El grupo piloto que propones es una buena forma de generar datos más representativos y recalibrar el score en el tiempo.

Agregaría que, aunque la segmentación por colores no mejora directamente los resultados de retención, podría tener valor para guiar decisiones de forma más consistente, especialmente si se combina con el monitoreo ex-post de falsos negativos que mencionas.
