El rendimiento de un algoritmo se evalúa atendiendo a cuatro medidas:
+ **Completitud:** ¿Está garantizado que el algoritmo encuentre una solución cuando esta exista?
+ **Optimización:** ¿Encuentra la estrategia la solución óptima?
+ **Complejidad en tiempo:** ¿Cuándo tarda en encontrar una solución?
+ **Complejidad en espacio:** ¿Cuánta memoria es necesaria para el funcionamiento de la búsqueda?
La complejidad en tiempo y espacio siempre se considera con respecto a alguna medida de la dificultad del problema. En Inteligencia Artificial la complejidad se expresa en términos de tres cantidades:
+ b: **factor de ramificación,** máximo número de sucesores de cualquier nodo;
+ d: **profundidad** de la solución de mínimo costo;
+ m: **profundidad máxima** de cualquier camino en el espacio de estados.
#### Características de las búsquedas no informadas

Una estrategia se define mediante la determinación del orden de expansión de los nodos. Las estrategias de búsqueda no informada usan únicamente la información disponible en la definición del problema. Todo lo que pueden hacer es generar los sucesores y distinguir entre un estado objetivo que uno que no lo es.

### Búsqueda primero en anchura

En lo que sigue se asume un costo unitario por generar cualquier sucesor de cualquier nodo. La búsqueda primero en anchura es una estrategia sencilla en la que se expande primero el nodo raíz, a continuación se expanden todos los sucesores del nodo raíz, después sus sucesores, etc.

En general, se expanden todos los nodos a una profundidad en el árbol de búsqueda antes de expandir cualquier nodo del próximo nivel.

![[animated_bfs.gif]]
#### Propiedades

+ **¿Es completa?** Sí, si el factor de ramificación es finito.
+ **¿Es óptima?** Sí, si el costo del camino es una función no decreciente de la profundidad del nodo (por ejemplo, cuando todas las acciones tienen el mismo coste). En general, no lo es.
+ **¿Cuánta memoria emplea?** 
![[Pasted image 20241029190610.png]]
+ **¿Cuánto tiempo emplea?**
![[Pasted image 20241029190636.png]]

![[Pasted image 20241029190751.png]]

Los requisitos de memoria son un problema más grande para la búsqueda primero en anchura que el tiempo de ejecución, en general, los problemas de búsqueda de complejidad exponencial no pueden resolverse por métodos sin información, salvo en casos pequeños.

## Siguiente [[Búsqueda de costo uniforme]]