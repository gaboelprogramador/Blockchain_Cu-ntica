# Hackathon

## Organización del repositorio 

El repositorio se ha organizado de forma accesible 

## Código ejecutado en el simulador

Con el fin de ejecutar el código importamos las librerías de Qiskit que necesitaremos para definir el circuito cuántico, representarlo y simularlo. Finalmente, lo ejecutaremos en un ordenador cuántico real y analizaremos los resultados susceptibles al ruido cuántico.

En primer lugar, creamosprimero una función que nos construye un operador unitario de dimensión 2 lo más general posible a partir 4 parámetros. Después definimos la función proceso que nos construye el circuito que representa el problema de dos jugadores que queremos estudiar. El circuito tendrá dos qubits y dos bits clásicos. Los qubits representan a los dos jugadores, los operadores sus decisiones y los bits nos dan la medida de cada qubit. El operador J_2 crea la superposición y entrelazamiento de las decisiones de los dos jugares. A continuación se añaden las dos matrices U_A y U_B que describen las decisiones de cada jugador. Por último, añadimos la puerta J_2_dg (la inversa de J_2), que deshace la operación inicial de enrelazamiento. Para poder medir los resultados, añadimos una medida de los qubits en sus registros clásicos correspondientes. Una vez que tenemos el circuito, creamos una tarea en la que ejecutamos el circuito 1024 veces en el simulador qasm y epresentamos los resultados en un histograma.

A continuación ejecutamos el programa para distintos juegos, es decir, distintos parámetros de las matrices unitarias. Según la teoría del equilibrio de Nash, en el dilema del prisionero clásico, la opción que alcanza el equilibrio es aquella en la que ambos jugadores se delatan. Nuestra primer ejemplo (caso clásico) verifica este resultado. Los dos siguientes casos, damos parámetros en los que uno de los jugadores ganará: estos casos se dan cuando uno de los jugadores confiesa y el otro no. Finalmente, realizamos una versión del dilema del prisionero cuántica en la que el resultado es una superposición de los dos casos anteriores, con la misma probabilidad. Qiskit tiene definidas las puertas S y X que replican el dilema del prisionero cuántico.

## Código ejecutado en el ordenador cuántico
Ejecutamos el código del último juego en el ordenador cuántico de IBM ibmq_manila. Se realiza una simulación y se compara con el resultado real. Observamos que el ruido no modifica sustancialmente los resultados.
