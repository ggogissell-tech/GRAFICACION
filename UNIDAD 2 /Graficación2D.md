<div align="justify">
La computación gráfica 2D es la generación de imágenes digitales por computadora sobre todo de modelos bidimensionales (como modelos geométricos, texto y imágenes digitales 2D) y por técnicas específicas para ellos. La palabra puede referirse a la rama de las ciencias de la computación que comprende dichas técnicas, o a los propios modelos.
La computación gráfica 2D se utiliza principalmente en aplicaciones que fueron desarrolladas originalmente sobre tecnologías de impresión y dibujo tradicionales, tales como tipografía, cartografía, dibujo técnico, publicidad, etc. En estas aplicaciones, la imagen bidimensional no es sólo una representación de un objeto del mundo real, sino un artefacto independiente con valor semántico añadido; los modelos bidimensionales son preferidos por lo tanto, porque dan un control más directo de la imagen que los gráficos 3D por computadora (cuyo enfoque es más semejante a la fotografía que a la tipografía).

# 2.1. Transformación bidimensional.
## 2.1.1. Traslación.
Se aplica una traslación en un objeto para cambiar su posición a lo largo de la trayectoria de una línea recta de una dirección de coordenadas a otra. Convertimos un punto bidimensional al agregar las distancias de traslación, tx y ty la posición de coordenadas original (x,y)

El par de distancia de traslación se llama vector de traslación o vector de cambio. Se pueden expresar las ecuaciones anteriores en una sola ecuación matricial al utilizar vectores de columna para representar las posiciones de coordenadas y el vector de traslación

Los polígonos se trasladan al sumar el vector de traslación a la posición decoordenadas de cada vértice y se vuelve a generar el polígono utilizando un nuevo conjuntode coordenadas y vértices y las especificaciones actuales de los atributos.

<div align="center">
<img width="293" height="320" alt="image" src="https://github.com/user-attachments/assets/33d0feb9-f7ee-4349-a8dc-9c147b2db5ee" />
</div>
## 2.1.2. Escalamiento.
Una transformación de escalación altera el tamaño de un objeto. Se puede realizar esta operación para polígonos al multiplicar los valores de coordenadas (x, y) de cada vértice por los factores de escalación s x y s  y para producir las coordenadas transformadas (x’, y’ )

## 2.1.3. Rotación.
Se aplica una rotación bidimensional en un objeto al cambiar su posición a lo largo de la trayectoria de una circunferencia en el plano de xy . Para generar una rotación, especificamos un ángulo de rotación θ y la posición (x r , y r ) del punto de rotación (o punto pivote) en torno al cual se gira el objeto.

<div align="center">
<img width="302" height="320" alt="image" src="https://github.com/user-attachments/assets/7fe13f4d-89c1-4ead-a23a-e31e85ed62d8" />
</div>
## 2.1.4. Sesgado.
# 2.2.Representación matricial de las transformaciones
bidimensionales.
Las transformaciones bidimensionales se representan mediante matrices 3x3 en coordenadas homogéneas, permitiendo aplicar traslación, rotación, escalado y sesgado de manera uniforme a todos los puntos de un objeto.
### EJEMPLO
El script en Blender define una herramienta interactiva llamada operador modal, lo que significa que, una vez activada, permanece en ejecución escuchando continuamente las acciones del usuario. Al iniciarse, el operador se registra en Blender y se ejecuta automáticamente, entrando en un modo en el que puede reaccionar a eventos del teclado en tiempo real.

Dentro de ese modo, el código busca un objeto específico en la escena llamado “Stroke”. Cada vez que detecta que se presiona una tecla de dirección, modifica directamente la posición de ese objeto: las flechas izquierda y derecha lo mueven sobre el eje X (horizontalmente), mientras que las flechas arriba y abajo lo desplazan sobre el eje Z (verticalmente). Cada pulsación aplica un cambio fijo de 0.5 unidades, lo que produce un movimiento incremental.

El operador sigue activo indefinidamente mientras no se cancele, permitiendo controlar el objeto como si fuera un pequeño sistema de navegación con el teclado. Finalmente, cuando el usuario presiona la tecla ESC, el operador termina su ejecución y deja de escuchar eventos, saliendo del modo interactivo.

https://github.com/user-attachments/assets/24ba58ed-0b09-4b44-83eb-66a76d40683b

# 2.3. Trazo de líneas curvas.
Los puntos y las líneas rectas en la graficación de sistemas son fundamentales, pero las formas y modelados de figuras reales rara vez son únicamente compuestas por polígonos rectos. Así, usamos curvas creadas mediante expresiones matemáticas polinomiales que aproximan o interpolan los vértices o "puntos de control".

Estas expresiones matemáticas garantizan que se genere una línea fluida y sin vértices o puntas drásticas —una propiedad conocida como Continuidad, donde se busca al menos una curvatura suave de primera derivada (la tangente 
C1) y de la segunda derivada (C2). El balance y uniones de estos polinomios modelan las "Curvas Spline".
## 2.3.1. Bézier.
Las curvas de Bézier son una herramienta fundamental en matemáticas aplicadas y gráficos porque permiten describir curvas suaves de forma muy controlada usando pocos elementos. Se definen mediante un conjunto de puntos llamados puntos de control, y la curva resultante no necesariamente pasa por todos ellos, sino que es “atraída” por estos, formando una trayectoria suave.

Existen distintos tipos según la cantidad de puntos:

Lineal (2 puntos): en realidad es una línea recta.
Cuadrática (3 puntos): genera una curva simple con un solo punto de control que “tira” de la forma.
Cúbica (4 puntos): es la más utilizada, ya que permite mayor flexibilidad al tener dos puntos de control que definen la entrada y salida de la curva.

Matemáticamente, las curvas de Bézier se basan en combinaciones de polinomios (polinomios de Bernstein), lo que garantiza propiedades importantes como la suavidad y la continuidad. Una característica clave es que la curva siempre está contenida dentro del “polígono de control” (la figura formada al unir los puntos de control), lo que facilita prever su forma.

Otra propiedad importante es la interpolación progresiva: la curva se genera como una interpolación entre los puntos de control, lo que se puede entender con el algoritmo de De Casteljau, que construye la curva paso a paso mediante interpolaciones lineales.

Las curvas de Bézier son ampliamente usadas porque:

Permiten un control intuitivo de formas complejas
Son eficientes de calcular
Garantizan suavidad sin discontinuidades
Se pueden escalar, rotar y transformar fácilmente

Por eso aparecen en muchas áreas como tipografías digitales, diseño vectorial (por ejemplo, en formatos como SVG), animación, CAD y gráficos en general.
##v2.3.2. B-spline.
Como ejemplo de B-spline, se presentará una animación de un conejo construida a partir de capas, utilizando una imagen de referencia para guiar el dibujo y el movimiento. La idea consiste en descomponer la figura del conejo en distintas partes o niveles, de modo que cada capa represente un elemento del diseño y pueda ser controlada de forma independiente.

A partir de esta referencia visual, se construyen curvas B-spline para definir contornos suaves y continuos, lo que permite modelar la forma del conejo con mayor fluidez y precisión. Estas curvas facilitan la creación de líneas orgánicas, evitando quiebres bruscos y manteniendo una transición suave entre puntos de control.

Posteriormente, cada capa del dibujo se anima siguiendo la estructura definida por las curvas, logrando un movimiento progresivo y coherente con la forma del conejo. Este enfoque permite aprovechar las propiedades de las B-spline para generar animaciones más naturales, en las que la deformación y el desplazamiento de las partes se integran de manera armónica a partir de la referencia inicial.

https://github.com/user-attachments/assets/ec50a00c-3980-4175-abb0-41e18cdba4c6

# 2.4. Fractales
Los fractales son estructuras geométricas que se caracterizan por repetir un mismo patrón a diferentes escalas. Esto significa que una parte del fractal se parece al todo, un fenómeno conocido como autosimilitud. A diferencia de las formas geométricas tradicionales, los fractales no se describen fácilmente con figuras simples como círculos o cuadrados, sino mediante procesos iterativos o recursivos que generan complejidad a partir de reglas muy básicas.

Un fractal puede construirse repitiendo una operación muchas veces, donde cada iteración añade más detalle al resultado final. Ejemplos clásicos incluyen el conjunto de Mandelbrot, el triángulo de Sierpinski o la curva de Koch. Estas formas muestran cómo un sistema simple puede producir estructuras visualmente complejas e infinitamente detalladas.

Los fractales se utilizan en diversas áreas como la generación de paisajes en gráficos por computadora, la simulación de fenómenos naturales (montañas, nubes, costas) y el análisis de sistemas caóticos. Su principal valor radica en que permiten crear complejidad visual con reglas matemáticas simples.
# 2.5. Uso y creación de fuentes de texto.
El uso y creación de fuentes de texto se refiere al diseño de alfabetos digitales y su implementación en sistemas informáticos. Una fuente tipográfica es un conjunto de caracteres que comparten un estilo visual coherente, y su diseño implica definir la forma de cada letra, número y símbolo de manera consistente.

Las fuentes modernas suelen construirse mediante vectores, lo que permite que los caracteres se escalen sin perder calidad. Esto se logra utilizando curvas (como Bézier) para definir los contornos de cada letra, lo que garantiza suavidad y precisión en cualquier tamaño.

El proceso de creación de una fuente incluye el diseño de glifos (formas individuales de cada carácter), el ajuste de espaciado entre letras (kerning) y la definición de métricas generales que controlan la alineación y proporción del texto. Una vez finalizada, la fuente se exporta en formatos estándar como TrueType u OpenType, que permiten su uso en sistemas operativos y aplicaciones.

Las fuentes de texto son fundamentales en diseño gráfico, comunicación visual y tecnología, ya que influyen directamente en la legibilidad, la estética y la identidad visual de cualquier contenido escrito.
#  Referencias Bibliográfica
* Client challenge. (s. f.). https://es.scribd.com/document/365919093/Unidad-2-Graficacion-2d-Jose-Birrueta-Castro
* Ramírez, O. S. (2020, 10 octubre). Transformación bidimensional. https://graficacion2d.blogspot.com/2020/10/transformacion-bidimensional.html
