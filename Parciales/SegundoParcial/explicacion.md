Los Elementos del Aprendizaje por Refuerzo en Conecta 4
El Entorno: Es el tablero de juego. Es el encargado de hacer cumplir las reglas: calcula en qué fila cae la ficha por la gravedad y avisa si alguien logró conectar 4 en línea.

Los Estados: Es la foto de cómo están puestas las fichas en un momento de la partida. Para que el agente lo recuerde fácil, el tablero se transforma en una sola línea de texto.

Las Acciones: Son las opciones que tiene el agente, que básicamente es elegir una columna libre para dejar caer su ficha.

La Recompensa: Es el premio que da el juego al final. Si el agente gana recibe un 1.0, si pierde un 0.0, y si empatan un 0.5.

La Politica: Es el criterio que usa el agente para decidir qué columna jugar. En este caso usa UCB para balancear las jugadas seguras con la curiosidad de probar columnas nuevas.
La memoria del agente (diccionario value_function). Guarda la foto de cada tablero junto a una nota de éxito de 0.0 a 1.0. Si un tablero tiene nota de 0.9 sabe que está por ganar y busca llegar ahí, pero si tiene 0.1 sabe que va a perder y evita esa jugada.

1. Como evalua las jugadas?
El agente evalua las jugadas haciendo un calculo mental antes de tirar la ficha. Mira las columnas que están libres y calcula en cuál fila va a caer su ficha por el efecto de la gravedad. Luego, busca ese tablero imaginario en su memoria para ver qué tanta probabilidad tiene de ganar si juega ahí.

2. Como explora las columnas?
El agente explora usando la estrategia UCB, que es básicamente la curiosidad matemática. En lugar de jugar siempre en el mismo sitio o elegir columnas a lo tonto, el agente mira su memoria y le da un bono de curiosidad a las columnas que casi no ha probado. Si una columna la ha jugado muy pocas veces, las ganas de probarla suben y la formula de UCB lo obliga a meter la ficha ahí para ver qué pasa.

3. ¿Como explota las jugadas ganadoras?
La explotacion es ir a lo seguro cuando el agente ya tiene experiencia. Cuando una jugada hace que conecte 4 fichas y gane, el juego le da un premio. El agente recuerda todo el camino de columnas que uso para ganar y les pone una nota altísima en su memoria. En las siguientes partidas, como esas columnas ya demostraron que sirven para ganar, el agente se deja de curiosidades y las juega directo para asegurar la victoria.
