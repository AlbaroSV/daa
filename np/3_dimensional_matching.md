El Problema del Matching Tridimensional: Complejidad NP-Completa

Analicemos la complejidad del problema del Matching Tridimensional (3DM), un problema fundamental en la teoría de la complejidad.
3DM pertenece a NP

Dado un conjunto de triples T ⊂ X × Y × Z, un certificado de que existe un matching perfecto es simplemente un subconjunto T' ⊆ T.  La verificación de que cada elemento de X ∪ Y ∪ Z aparece exactamente una vez en las triples de T' se puede realizar en tiempo polinomial.  Por lo tanto, 3DM reside en la clase NP.
3DM es NP-Difícil (Reducción desde 3-SAT)

Para demostrar que 3DM es NP-difícil, construiremos una reducción desde el problema 3-SAT (3-Satisfacibilidad).  La idea principal es representar las variables y cláusulas de una instancia de 3-SAT como estructuras ("gadgets") en una instancia de 3DM.

Consideremos una instancia de 3-SAT con n variables (x₁, x₂, ..., xₙ) y k cláusulas (C₁, C₂, ..., Cₖ).  Construiremos nuestra instancia de 3DM en tres etapas:


Etapa 1: Gadgets para las Variables:

Para cada variable xᵢ, creamos un "gadget variable" compuesto de:

 Un conjunto de *2k elementos "centrales": Aᵢ = {aᵢ₁, aᵢ₂, ..., aᵢ₂ₖ}.
 Un conjunto de *2k elementos "periféricos": Bᵢ = {bᵢ₁, bᵢ₂, ..., bᵢ₂ₖ}.

 Un conjunto de *2k triples:  Para cada j ∈ {1, 2, ..., 2k}, definimos la triple tᵢⱼ = (aᵢⱼ, aᵢⱼ₊₁, bᵢⱼ), donde la suma de los subíndices se toma módulo 2k.  Llamaremos a las triples con j par "triples pares" y a las con j impar "triples impares".

Observemos que para cubrir todos los elementos de Aᵢ en un matching perfecto, se deben seleccionar todas las triples pares O todas las triples impares.  Esto representa la asignación de verdad de la variable: todas las triples pares implican xᵢ = FALSO, mientras que todas las triples impares implican xᵢ = VERDADERO.


Etapa 2: Gadgets para las Cláusulas:

Para cada cláusula Cⱼ, construimos un "gadget cláusula" con dos elementos internos Pⱼ = {pⱼ, pⱼ'}.  Para cada literal t en Cⱼ:

 Si *t = xᵢ, añadimos la triple (pⱼ, pⱼ', bᵢ₂ⱼ).
 Si *t = ¬xᵢ, añadimos la triple (pⱼ, pⱼ', bᵢ₂ⱼ₋₁).

Estos gadgets aseguran que al menos una de las triples que representan un literal en una cláusula sea parte del matching, reflejando la condición de satisfacción de la cláusula.


Etapa 3: Elementos de "Limpieza":

Tras las etapas anteriores, no todos los elementos periféricos (bᵢⱼ) están cubiertos.  Para completar el matching, añadimos *n*k-k "triples de limpieza" con nuevos elementos.


Conclusión:

Si la instancia de 3-SAT es satisfacible, existe una asignación de verdad que satisface todas las cláusulas.  Esta asignación se traduce directamente en un matching perfecto en nuestra instancia de 3DM, seleccionando las triples pares o impares para cada gadget variable de acuerdo a la asignación de verdad.  Por el contrario, un matching perfecto en 3DM implica una asignación de verdad satisfactoria en 3-SAT.  Por lo tanto, 3DM es NP-difícil.


En resumen, al ser 3DM un problema en NP y NP-difícil, concluimos que es NP-completo.  La reducción constructiva demuestra la equivalencia entre la satisfacibilidad de una fórmula booleana y la existencia de un matching perfecto en el grafo resultante.