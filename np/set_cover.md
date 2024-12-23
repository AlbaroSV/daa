La Complejidad del Problema de la Cobertura de Conjuntos (Set Cover)

Analicemos la complejidad computacional del conocido problema de la cobertura de conjuntos (Set Cover).
Set Cover pertenece a NP

El problema de determinar si existe una cobertura de conjuntos de tamaño menor o igual a k se encuentra en la clase de complejidad NP.  Para demostrar esto, observemos que dado un conjunto universo X, una colección S de subconjuntos de X, y un entero k, un certificado de que la respuesta es "sí" es simplemente un subconjunto S' de S con tamaño a lo sumo k tal que la unión de los conjuntos en S' es igual a X.  Verificar que un subconjunto dado satisface esta condición puede hacerse en tiempo polinomial en el tamaño de la entrada.
Set Cover es NP-Difícil (Reducción desde 3-Dimensional Matching)

La NP-dureza del problema de la cobertura de conjuntos se puede demostrar mediante una reducción desde el problema del 3-Dimensional Matching (3DM), un problema ya conocido por ser NP-completo.

El problema 3DM se puede reformular como una instancia del problema Set Cover de la siguiente manera: el conjunto universo X sería la unión de los tres conjuntos X, Y, y Z de la instancia de 3DM.  La colección S de subconjuntos estaría compuesta por las triples de la instancia de 3DM, donde cada triple representa un subconjunto de X.  En esta formulación, encontrar un matching perfecto en 3DM equivale a encontrar un subconjunto S' de S tal que la unión de los subconjuntos en S' cubre todo el conjunto X, y el tamaño de S' es a lo sumo n (siendo n el número de elementos en X, Y, o Z).

Dado que resolver el problema de la cobertura de conjuntos en esta instancia resuelve el problema de 3DM, y 3DM es NP-completo, concluimos que el problema de la cobertura de conjuntos también es NP-completo.  La reducción es eficiente, ya que la transformación de una instancia de 3DM a una instancia de Set Cover puede realizarse en tiempo polinomial.


Por lo tanto, el problema Set Cover es NP-completo.  Su pertenencia a NP y su NP-dureza (demostrada mediante la reducción polinomial desde 3DM) establecen su lugar dentro de la clase de problemas computacionalmente intratables (a menos que P=NP).