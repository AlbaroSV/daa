
Analicemos la complejidad del problema de encontrar un clique de tamaño k en un grafo, un problema clásico en la teoría de la complejidad.
El Problema del Clique pertenece a NP

Dado un grafo G y un entero k,  la afirmación de que existe un clique de tamaño k en G se puede verificar eficientemente. Un certificado de la existencia de dicho clique es simplemente el conjunto de k vértices que lo forman.  Verificar que estos k vértices forman un clique (es decir, que existe una arista entre cada par de ellos) se puede realizar en tiempo polinomial respecto al tamaño del grafo.  Por lo tanto, el problema del clique pertenece a la clase NP.
El Problema del Clique es NP-Difícil (Reducción desde 3-SAT)

La NP-dureza del problema del clique se demuestra mediante una reducción desde el problema 3-SAT (3-Satisfacibilidad).  Construiremos un grafo a partir de una instancia de 3-SAT de forma que la existencia de un clique de un tamaño específico en el grafo corresponda a la satisfacibilidad de la fórmula booleana.

Consideremos una instancia de 3-SAT con n variables y k cláusulas.  Cada cláusula contiene exactamente tres literales. Construiremos un grafo no dirigido G de la siguiente manera:

Para cada cláusula Cᵢ = (lᵢ₁, lᵢ₂, lᵢ₃), creamos tres vértices vᵢ₁, vᵢ₂, vᵢ₃ en G, uno por cada literal de la cláusula.  Unimos dos vértices vᵢⱼ y vₖₗ con una arista si y solo si:

1.  Los vértices pertenecen a cláusulas diferentes (i ≠ k), y
2.  Los literales correspondientes lᵢⱼ y lₖₗ son consistentes (es decir, no son uno la negación del otro).

Esta construcción se puede realizar en tiempo polinomial.  Ahora demostraremos la equivalencia entre la satisfacibilidad de la instancia de 3-SAT y la existencia de un clique de tamaño k en G.


Directamente: Si la instancia de 3-SAT es satisfacible, existe una asignación de verdad que satisface todas las cláusulas.  Para cada cláusula, seleccionamos un vértice correspondiente a un literal que es VERDADERO en esa asignación.  El conjunto de k vértices seleccionados forma un clique en G, ya que los literales escogidos no pueden ser contradictorios entre sí.


Recíprocamente:  Si existe un clique de tamaño k en G, este clique debe contener exactamente un vértice por cada cláusula (debido a la condición 1 de la construcción del grafo).  Asignando el valor VERDADERO a los literales correspondientes a los vértices del clique, obtenemos una asignación satisfactoria para la instancia de 3-SAT, ya que la condición 2 de la construcción asegura que no se asignará VERDADERO a un literal y a su negación simultáneamente.


Concluimos que el problema del clique es NP-difícil.  Dado que también pertenece a NP, el problema del clique es NP-completo.