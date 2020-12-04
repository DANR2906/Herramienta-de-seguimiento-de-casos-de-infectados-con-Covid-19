# Herramienta-de-seguimiento-de-casos-de-infectados-con-Covid-19
Proyecto final Matemáticas Discretas Universidad Industrial de Santander

## RESUMEN

La sociedad ha vuelto a ser puesta en prueba frente a una pandemia, esta vez causada por el brote de un virus nombrado Covid-19. A pesar de que la civilización de hoy en día está más conectada gracias a diversas herramientas como el internet y posee un enorme desarrollo tecnológico en los diversos campos como el científico con respecto a épocas anteriores, sufre demasiadas problemáticas como es la desinformación presente en la comunicación golpeando fuertemente a la sociedad. Por consiguiente se buscó una forma de poder visualizar y analizar el impacto que genera un virus de tal categoría en una población teniendo en cuenta determinados factores relevantes al momento de dicho estudio.

La investigación de este proyecto se centró en la realización de una simulación para el estudio del desarrollo del virus utilizando teoría de grafos, se partió de la idea de una población con una cantidad determinada de personas, de las cuales cada una posee características aleatorias tales como nombre, identificación y su relación con otros individuos, además de cualidades susceptibles al virus tales como enfermedades respiratorias y su edad; obteniendo un grafo base que presenta personas no infectadas, con enfermedades respiratorias, contagiados y combinaciones de estas, por lo cual cada persona representa un vértice y las relaciones entre ellas las aristas. Para desarrollar la simulación del avance del virus se utilizó un posible modelo estocástico a cerca del Covid 19, donde se tienen diversos datos estadísticos presentados durante el desarrollo de este brote, como la tasa y probabilidad de mortalidad con respecto a rangos de edades, afección respiratoria, tasa de contagio, la cual comparte factores anteriormente mencionados, recuperación promedio, etc. El tratamiento, análisis y la implementación de la simulación se realizó en el lenguaje de programación Python y se desarrolló en el entorno de Jupyter Notebook.

INTRODUCCIÓN
Los virus han estado presente siempre en la historia de la humanidad, y algunos han afectado en gran escala a la sociedad, el covid-19 no es la excepción, a pesar de la tecnología y la gran evolución de la sociedad en los diferentes campos que se ha logrado obtener hoy en día, el covid-19 logro desestabilizar la economía y la misma convivencia humana en la sociedad, al paso del tiempo quizás ya la humanidad fuera logrado superar tal pandemia, pero esto depende de muchos factores, como el desacato de sanidad por una parte de la sociedad, la desigualdad social, entre otros. después de todo, errar está en el ámbito humano, una de las cualidades que hace especial a la humanidad, si ese no fuera nuestro caso, no podríamos darle un mínimo sentido a nuestra existencia la cual le es indiferente a tan basto universo.

El objetivo de este proyecto es lograr demostrar el comportamiento que debe presentar cada persona en el momento de enfrentar esta pandemia que azota con la gran cantidad de personas en el mundo. A su vez se muestra la importancia del aislamiento colectivo y el cuidado personal para lograr combatir y disminuir a mayor escala la enfermedad.

En conclusión, analizaremos el comportamiento de una población con la enfermedad COVID-19, producido por el virus SARS-COV2, en el cual se lleva un seguimiento de cada uno de los casos presentados por la trasmisión de la enfermedad y así ver como al pasar de los días y semanas, el virus logra alterar al ser humano y aumentar el riesgo de muerte de la misma persona. De este modo podemos ver ilustrado como las personas portadoras del virus al momento de tomar la decisión de aislarse, logran la disminución de contagio, también podemos observar como pueden recuperarse y la cantidad de muertes que se pueden llegar a ocasionar. Por esto mismo es fundamental enseñar las diversas maneras para combatir y disminuir el virus para evitar un mayor riesgo a la población.

REVISIÓN DE LA LITERATURA
Pierson, D. (2020, 21 marzo). Si me infecto con coronavirus, ¿cuáles son mis probabilidades de supervivencia? - Los Angeles Times. Los Angeles Times en Español. https://www.latimes.com/espanol/internacional/articulo/2020-03-20/si-me-infecto-con-coronavirus-cuales-son-mis-probabilidades-de-supervivencia

Ruiz-Ramírez, J. (s. f.). Modelo estocástico de la transmisión de enfermedades infecciosas. SCIELO. Recuperado 2 de septiembre de 2020, de http://www.scielo.org.mx/scielo.php?script=sci_arttext&pid=S0036-36342009000500006

Cuffe, R. (2020, 3 marzo). ¿Qué tan mortal es realmente el nuevo coronavirus? BBC News Mundo. https://www.bbc.com/mundo/noticias-51708029

OMS. (s. f.). Preguntas y respuestas sobre la enfermedad por coronavirus (COVID-19). Organización Mundial de la Salud. https://www.who.int/es/emergencies/diseases/novel-coronavirus-2019/advice-for-public/q-a-coronaviruses?gclid=CjwKCAjwkdL6BRAREiwA-kiczF1ymYKxIPJUD0cx4nMHzHcFsmrZMYACMaAqer11--bpNkmviwuYgBoCUq0QAvD_BwE

MÉTODO
DEFINICIÓN DEL GRAFO
Definimos un conjunto de personas como:

P= {p1,p2,p3,...,pn}

Por lo cual la población total estaría dada por:

∑ni=1pi=X

Hay un conjunto de persona infectadas

I= {n1,n2,n3}

El total de personas infectadas se define por:

∑mi=1ni=Y

Donde I⊆P

Por lo tanto existe un grafo no dirigido que representa las relaciones sociales de toda la población P y se define como:

G(P)=(V(P),E(P))

Donde V(P) representa el conjunto de vertices (personas de la población), por lo cual:

V(P)=P

y E(P) el conjunto de aristas (relación entre personas)

La relación de incidencia se define como:

δ:E→x  |  x= {{u,v} | u≠v ;  u∧v∈V}

La relación de incidencia define la relación social entre las personas de la población, donde un inviduo no puede estar relacinado consigo mismo y además esta puede definir tres tipos de relación, las cuales son: PERSONA INFECTADA-PERSONA INFECTADA, PERSONA INFECTADA-PERSONA NO INFECTADA y PERSONA NO INFECTADA-PERSONA NO INFECTADA.

PSEUDOCÓDIGO
Descripción del algoritmo usado para representar el problema
Pseudocodigo
Declaramos la variable array

Asignamos a array los datos que estan en el archivo NationalNames.csv

Declaramos la lista nombres y la variable cantidadDePersonas

cantidadDePersonas = 400

para i = 1 hasta cantidadDePersonas

Asignamos a nombres += {array en la posición i}

Declaramos la variable lista

para i = 0 hasta cantidadDePersonas - 1

edadRan = Generar un numero pseudoaleatorio del 1 al 80

lista += [Creamos un objeto de la clase Person(i+1, nombres en la posición i, edadRan)]

para i en lista

i.establecerInfectados() Usamos el metodo establecerInfectados() de la clase Person

i.establecerEnfermedadesRespiratorias() Usamos el metodo establecerEnfermedadesRespiratorias() de la clase Person

Definimos el grafo de la siguiente forma:

Declaramos la variable grafo

De esta manera declaramos las aristas en el grafo de forma pseudoaleatoria:

para i en lista

Declaramos cantAristas = numero pseudoaleatorio del 1 al 6

Declaramos un diccionario como dicAux

Para i = 0 hasta cantAristas

Declaramos nodoAleatorio = numero pseudoaleatorio del 0 hasta la cantidad de personas en la variable lista

si i.getId() es diferente que nodoAleatorio + 1

Asignamos dicAux += [(lista en la posición nodoAleatorio).getId()]

grafo en la posición i.getId() = dicAux

Asignamos cantAristas = len(Graph(grafo).edges()) tamaño del grafo que guarda la información de las aristas

para i = 0 hasta cantAristas

Declaramos ultimoEncuentro = numero pseudoaleatorio de 1 hasta 30

Declaramos listaAux = list(Graph(grafo).edges()[en la posición i])

Si (lista en la posición listaAux[0] - 1).getIngeftado es verdadero o (lista en la posición listaAux[1] - 1).getIngeftado es verdadero, entonces:

Se agrega el conjunto de aristas correspondiente a Graph(grafo).edges()[i] con un encuentro = ultimoEncuentro y un color = 'red'

De lo contrario:

Se agrega el conjunto de aristas correspondiente a Graph(grafo).edges()[i] con un encuentro = ultimoEncuentro y un color = 'black'

Se procede a modelar el grafo haciendo uso de la clase networkx y del metodo colorarGrafo(), el cual se encarga de colorar los nodos ilustrados en el grafo de las siguientes maneras:

Veamos a p como cualquier persona del conjunto de aristas.

Morado: Si p esta infectado y posee enfermedades respiratorias.

Rojo: Si p esta infectado con el virus.

Amarillo: Si p posee enfermedades respiratorias.

Verde: Si p se ha recuperado del virus.

Gris: Si p esta muerto.

Azul: Si p se encuentra en un estado normal.

Rosado: Si p se encuentra aislado

Declaramos una lista como listaInfectados

para i en lista

si i.getInfectado() es verdadero:

listaInfectados += {i}

para i = 0 hasta el numero de infectados (len(listaInfectados))

ran = numero pseudoaleatorio de 0 a 100

Si ran es menor o igual que 20:

Asignamos el aislamiento como verdadero en listaInfectados en la posicion i

Asignamos cantAristas = numero de aristas len(Graph(grafo).edges())

Declaramos encuentroAux

para i = 1 hasta cantidadAristas

Declaramos edgeAux = G.adj[i] conjunto de aristas en la posición i

para u = 0 hasta len(edgeAux)

encuentroAux en la posición i,edgeAux[u] = G.edges con los valores i,edgeAux[u] devolver ['encuentro']

Declaramos listaInfectados como una lista vacia

para i en lista

si i.getInfectado() es verdadero

Entonces aisgnamos a listaInfectados += {i}

Declaramos dos listas llamadas encuentros y colores

para i en listaInfectados

si i .getAislamiento es falso

Declaramos vecinos como = list(G.adj[i.getId()]) esto devolvera todos los nodos vecinos al nodo i

para u en vecinos

Asignamos a encuentros += {G.edges[i.getId(),u]devolver ['encuentro']}

Asignamos a colores += {G.edges[i.getId(),u] devolver ['color']}

para j = 0 hasta len(vecinos) - 1

Llamamos al metodo contagio() y le pasamos como parametros contagio(encuentros en la posición j, lista en la posición veciones[j]-1)

Asignamos a la variable Dia += 7

Llamamos al metodo establecerRecuperados(lista) y le pasamos como parametro la lista que contiene a las personas de la población

Llamamos al metodo aislarNodos()

Definición de algunos de los metodos:

Función aislarNodos():

para i en listaInfectados

si i.getAislamiento es verdadero

Declaramos auxEdges y asignamos = list(G.adj[i.getId()])

para k = 0 hasta len(auxEdges)

Remover el conjunto de aristas (auxEdges[k], i.getId())
