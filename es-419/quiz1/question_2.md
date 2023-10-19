--- question ---
---
legend: Pregunta 2 de 3
---

En este proyecto, utilizaste procedural generation (generación de procedimientos): hacer que la computadora cree y ubique partes de tu mundo para ti. Si bien hacer esto es un gran ahorro de tiempo, especialmente si estás creando niveles muy grandes también puede crear algunos problemas. ¿Cuál de los problemas a continuación deberías tener en cuenta al probar tu procedural generation (generación de procedimientos?

--- choices ---

- (x) Todos

  --- feedback ---

¡Correcto! Todos estos problemas pueden ocurrir cuando se utiliza la generación de procedimientos. Podrías agregar más código para verificar y solucionar estos problemas, o probar diferentes seeds (semillas) hasta que encuentres una que funcione.

  --- /feedback ---

- ( ) Podrían generarse obstáculos que dejen al jugador sin camino a seguir.

  --- feedback ---

No exactamente. Esto puede suceder con obstáculos generados por procedimientos, particularmente cuando el juego apenas comienza.


**Sugerencia:** Puedes solucionar este problema evitando que aparezcan obstáculos demasiado cerca de la posición inicial del jugador. ¿Se te ocurren otras soluciones?

  --- /feedback ---

- ( ) Los obstáculos aparecen directamente debajo del jugador.

  --- feedback ---

No exactamente. Esto puede suceder al comienzo del juego o cuando se agregan nuevos obstáculos como resultado del aumento del nivel de dificultad, si eligen una posición cercana a la del jugador.


**Tip:** A potential solution might be to make the player temporarily immune to collision with all obstacles, or even only newly created obstacles, for a short time after a level increase. ¿Qué problemas se podriar crear eligiendo una nueva posición para el obstáculo, si esta estuviera demasiado cerca del jugador?

  --- /feedback ---

- ( ) Los obstáculos están todos agrupados, dejando demasiado espacio libre en otros lugares.

  --- feedback ---

No exactamente. Because random generation can choose groups of numbers that are close together, this can be a problem.


**Sugerencia:** Una solución podría ser cambiar a la generación semialeatoria: dividir la pantalla en pedazos y usar números aleatorios para generar obstáculos dentro de cada uno de esos pedazos. ¿Puedes pensar en cómo podrías usar este tipo de generación de procedimientos para hacer que tu juego sea más interesante o más desafiante?

  --- /feedback ---

--- /choices ---

--- /question ---
