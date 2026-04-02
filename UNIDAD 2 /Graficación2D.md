La computación gráfica 2D es la generación de imágenes digitales por computadora sobre todo de modelos bidimensionales (como modelos geométricos, texto y imágenes digitales 2D) y por técnicas específicas para ellos. La palabra puede referirse a la rama de las ciencias de la computación que comprende dichas técnicas, o a los propios modelos.
La computación gráfica 2D se utiliza principalmente en aplicaciones que fueron desarrolladas originalmente sobre tecnologías de impresión y dibujo tradicionales, tales como tipografía, cartografía, dibujo técnico, publicidad, etc. En estas aplicaciones, la imagen bidimensional no es sólo una representación de un objeto del mundo real, sino un artefacto independiente con valor semántico añadido; los modelos bidimensionales son preferidos por lo tanto, porque dan un control más directo de la imagen que los gráficos 3D por computadora (cuyo enfoque es más semejante a la fotografía que a la tipografía).

# 2.1. Transformación bidimensional.
Se aplica una traslación en un objeto para cambiar su posición a lo largo de la trayectoria de una línea recta de una dirección de coordenadas a otra. Convertimos un punto bidimensional al agregar las distancias de traslación, tx y ty la posición de coordenadas original (x,y)

El par de distancia de traslación se llama vector de traslación o vector de cambio. Se pueden expresar las ecuaciones anteriores en una sola ecuación matricial al utilizar vectores de columna para representar las posiciones de coordenadas y el vector de traslación

Los polígonos se trasladan al sumar el vector de traslación a la posición decoordenadas de cada vértice y se vuelve a generar el polígono utilizando un nuevo conjuntode coordenadas y vértices y las especificaciones actuales de los atributos.
