# Foro 3 — Respuestas Desarrolladas
**Diplomado IA aplicada a la Gestión de Personas — Call Co.**

---

## Pregunta 1
Proponga una estrategia empírica para evaluar el impacto de las entrevistas cerca de TESTSCOREyellow sobre la selección de candidatos que tienen mejor probabilidad de permanecer por más de 6 meses en la empresa.

### Respuesta

Para evaluar el impacto de las entrevistas, es necesario usar una estrategia que permita establecer causalidad, no solo correlación. En la Clase 2 se revisan cuatro métodos posibles para esto: el experimento aleatorio, las diferencias en diferencias, la variable instrumental y la regresión discontinua {1}.

El **experimento aleatorio** sería el más directo, pero requeriría asignar al azar quién es entrevistado cerca del corte, lo que interrumpe el proceso normal de contratación de la empresa y puede no ser viable en la práctica {1}.

Las **diferencias en diferencias** no se ajustan bien a esta situación, porque no existe un momento claro en que un grupo comienza a recibir entrevistas y otro no a lo largo del tiempo {1}.

La **variable instrumental** tampoco es fácil de aplicar aquí, ya que sería difícil encontrar una variable externa que afecte si el candidato es entrevistado pero que no tenga ningún otro efecto sobre su retención {1}.

Por eso, la estrategia más adecuada es el **diseño de regresión discontinua** {1}. La razón es que TESTSCOREyellow funciona exactamente como el tipo de corte que este método requiere: los candidatos que quedan justo por debajo son entrevistados, y los que quedan justo por encima son contratados directamente sin entrevista. Ambos grupos tienen puntajes muy similares, por lo que sus características son prácticamente iguales. La única diferencia real entre ellos es si pasaron o no por una entrevista.

Comparando la retención a 6 meses de ambos grupos cerca de ese corte, podemos estimar de forma creíble cuánto impacto tiene la entrevista sobre la probabilidad de que un candidato permanezca en la empresa. Esta lógica es consistente con la evidencia de que respetar las recomendaciones del algoritmo se asocia con mejores resultados de retención {2}, lo que sugiere que la etapa de entrevista tiene un efecto real sobre la selección final. Para que el método sea válido, es importante que los candidatos no puedan manipular su puntaje para quedar de un lado u otro del corte, condición que se cumple si el Testscore tiene variabilidad natural en sus resultados.

---

## Pregunta 2
¿Basándose en el análisis de Testscore en la clase, usted piensa que la clasificación de los candidatos en grupos rojo, amarillo y verde mejorará los resultados de la empresa, específicamente en términos de retención y desempeño?

### Respuesta

La clasificación generará una mejora parcial y limitada. Si bien la Tabla II muestra que usar un test de selección aumenta la duración del empleo {2}, el análisis de clase indica que la correlación entre Testscore y retención es muy débil, y con el desempeño es prácticamente cero {1}{3}. Esto significa que dividir a los candidatos en tres colores no va a cambiar de forma significativa ni quién se queda en la empresa ni quién rinde mejor.

El mayor riesgo de esta propuesta es contratar a los candidatos verdes sin entrevista. La Figura IV muestra que cuando se ignora la recomendación del algoritmo los resultados empeoran {2}, pero contratar sin entrevista también elimina información valiosa que el Testscore no captura, como la actitud y motivación del candidato {1}. Dado que el test tiene baja capacidad predictiva, la entrevista cumple un rol complementario importante que no debería eliminarse.

En resumen, rechazar a los candidatos rojos puede ayudar en algo, pero la clasificación no resolverá el problema de fondo: el Testscore simplemente no predice bien ni la retención ni el desempeño {1}{3}.

---

## Referencias

{1} Bojilov, R. (2024). *Clase 2: Usos y abusos de la analítica de personas*. Diplomado en Inteligencia Artificial aplicada a la Gestión de Personas. Pontificia Universidad Católica de Chile.

{2} Hoffman, M., Kahn, L.B. y Li, D. (2018). Discretion in Hiring. *The Quarterly Journal of Economics*, 133(2), 765–800.

{3} Bojilov, R. (2024). *Clase 3: Evaluación de herramientas analíticas: análisis descriptivo*. Diplomado en Inteligencia Artificial aplicada a la Gestión de Personas. Pontificia Universidad Católica de Chile.

{4} Bojilov, R. (2024). *Clase 4: Evaluación de herramientas analíticas: regresiones*. Diplomado en Inteligencia Artificial aplicada a la Gestión de Personas. Pontificia Universidad Católica de Chile.

---

*Nota de transparencia: Este documento fue elaborado con apoyo de Claude (Anthropic, 2026) como herramienta de redacción y estructuración. El análisis conceptual y las referencias académicas fueron verificados por el autor en base a los materiales del curso.*
