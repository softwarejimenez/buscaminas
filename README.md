Buscaminas
==========

El juego del buscaminas comienza con un tablero de F filas y
C columnas, donde se ocultan N minas. Inicialmente no se
sabe nada sobre lo que hay debajo de cada casilla, pudiendo
ser una casilla sin mina o con mina.

El problema consiste en localizar las minas sin detonar
ninguna de ellas. En cada paso, el jugador escoge entre:
1. Destapar una casilla. Si es una mina, habrá detonado y
el juego ha terminado sin éxito. Si no lo es, se abrirá la
	casilla y el resto de casillas del “entorno”.
2. Marcar una casilla como posición probable de una
mina. Es decir, el jugador determina que esta casilla
nunca se abrirá, ya que piensa que tiene una mina.

Si el juego continúa y llega el momento en que todas las casillas se han abierto (excepto las
que contienen una mina), no quedarán casillas por abrir y, por tanto, se habrá ganado el
juego.

Para poder guiar al jugador de forma que pueda averiguar dónde se encuentran las minas, el
juego ofrece pistas sobre dónde podrían estar las minas. En concreto, cuando se abre una
casilla sin mina existen dos posibilidades:

1. Está vacía, sin mina, y no hay ninguna mina al lado. En este caso, el juego explora
automáticamente las 8 casillas que hay a su alrededor, abriendo aquellas que no
tengan mina.

2. Está vacía, sin mina, pero tiene una o más minas al lado. En este caso el juego se limita
a mostrar al jugador la casilla como vacía, pero mostrando un número que indica el
número de minas que están en su entorno.

El jugador deberá analizar los números que se van mostrando para deducir dónde se sitúan
las N minas que sabemos oculta el tablero.

##Manual de uso del juego en la consola

En este proyecto se pretende usarse con la consola.
Por tanto, las entradas y salidas deberán realizarse con “ cin” y “cout”. Se propone la siguiente
interfaz:

1. Inicialmente comienza el juego pidiendo los parámetros de dificultad. Estos
parámetros están compuestos por el número de filas, el número de columnas, y el
número de minas ocultas. Observe que el número de minas no puede ser demasiado
grande. Por ejemplo, podemos obligar a que siempre haya un número mínimo de 5
minas y un número máximo que corresponde al 50% de casillas en el tablero.

2. En cada iteración, el juego muestra el tablero actual y pregunta por una acción a
realizar. La acción puede ser:
	* Abrir una posición. El usuario escribe tres datos, el primero será una palabra
	“a” o “abrir” (con cualquier combinación mayúsculas/minúsculas), y los dos
	siguientes la fila y columna correspondientes. En este caso, el programa abre la
	casilla indicada modificando el tablero según corresponda. Observe que esta
	acción no hace nada si la casilla ya está abierta o tiene una marca.
		
	* Marcar/Desmarcar una posición. El usuario escribe tres datos, el primero una
	palabra “m” o “marcar” (con cualquier combinación mayúsculas/minúsculas), y
	los dos siguientes la fila y columna correspondiente. Si la casilla está sin marcar
	la pone como marcada, y en caso de que ya esté marcada elimina la marca.

3. El juego termina con éxito cuando todas las casillas sin mina están abiertas. Por otro
lado, el juego termina sin éxito si se realiza una acción de apertura sobre una casilla
que contiene una mina.
