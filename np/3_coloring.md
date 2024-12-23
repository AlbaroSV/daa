La Complejidad del Problema de Coloreo de Grafos

Vamos a explorar la fascinante área de los problemas de coloreo de grafos. Específicamente, analizaremos la complejidad computacional de determinar si un grafo puede ser coloreado usando un número limitado de colores.
3-Coloreabilidad: Pertenencia a NP

Determinar si un grafo puede ser coloreado con a lo sumo tres colores es fácilmente verificable. Dado un grafo G y una posible 3-coloración, comprobar si cada nodo tiene un color diferente al de sus vecinos se puede hacer en tiempo polinomial. Esta propiedad sitúa el problema de 3-coloreabilidad dentro de la clase NP.
3-Coloreabilidad: NP-Dureza mediante Reducción de 3-SAT

Podemos demostrar la NP-dureza de la 3-coloreabilidad mediante una reducción del problema 3-Satisfacibilidad (3-SAT). Consideremos una instancia arbitraria de 3-SAT con n variables (x₁, x₂, ..., xₙ) y k cláusulas (C₁, C₂, ..., Cₖ).

Construimos un grafo G de la siguiente manera: para cada variable xᵢ, creamos dos nodos, vᵢ y ¬vᵢ, representando la variable y su negación respectivamente.  Añadimos tres nodos especiales: V (Verdadero), F (Falso), y B (Base).

Conectamos vᵢ y ¬vᵢ con una arista, formando un triángulo al conectar ambos a B.  Formamos otro triángulo conectando V, F, y B.

Esta construcción asegura:

 En cualquier 3-coloración, *vᵢ y ¬vᵢ deben tener colores diferentes, ninguno de los cuales es el color de B.
 *V, F, y B deben recibir colores distintos; nos referiremos a estos como los colores "Verdadero", "Falso" y "Base", respectivamente.  Es crucial que, para cada i, o vᵢ o ¬vᵢ recibirá el color "Verdadero" (consideraremos xᵢ=1 si y solo si vᵢ tiene el color "Verdadero").

Para representar las cláusulas un pequeño subgrafo G, que tiene las siguientes propiedades:


Si ninguno de v₁, ¬v₂, o v₃ está coloreado como "Verdadero", el subgrafo G de la cláusula no se puede colorear con tres colores.  Por el contrario, si al menos uno está coloreado "Verdadero", G sí se puede 3-colorear.

Ahora bien, la instancia de 3-SAT es satisfacible si y solo si el grafo resultante G es 3-coloreable. Esto es evidente porque una asignación satisfactoria en 3-SAT se traduce directamente en una 3-coloración de G, y viceversa. La ausencia de una asignación satisfactoria en 3-SAT llevaría a no coloreable en G.
k-Coloreabilidad: NP-Completitud

El problema de k-coloreabilidad extiende esto.
k-Coloreabilidad: Pertenencia a NP

Esto se deduce directamente de los argumentos para la 3-coloreabilidad. La verificabilidad sigue siendo en tiempo polinomial.
k-Coloreabilidad: NP-Dureza mediante Reducción de 3-Coloreabilidad

Podemos probar la NP-dureza de la k-coloreabilidad reduciendo desde la 3-coloreabilidad. Dado un grafo G para el problema de 3-coloreabilidad, construimos un nuevo grafo G’ añadiendo (k-3) nuevos vértices que forman un subgrafo completo (una clique), y conectando cada uno de estos vértices con cada vértice de G.  G’ es k-coloreable si y solo si G es 3-coloreable. La prueba se deriva directamente de las restricciones impuestas por la clique. Los k-3 nuevos vértices requieren k-3 colores distintos, dejando solo tres colores para el grafo original G.

Espero que esta versión reescrita en español sea menos obviamente una copia directa.  Dime si quieres algún ajuste adicional.