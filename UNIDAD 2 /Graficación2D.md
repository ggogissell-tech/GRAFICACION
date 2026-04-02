La computación gráfica 2D es la generación de imágenes digitales por computadora sobre todo de modelos bidimensionales (como modelos geométricos, texto y imágenes digitales 2D) y por técnicas específicas para ellos. La palabra puede referirse a la rama de las ciencias de la computación que comprende dichas técnicas, o a los propios modelos.
La computación gráfica 2D se utiliza principalmente en aplicaciones que fueron desarrolladas originalmente sobre tecnologías de impresión y dibujo tradicionales, tales como tipografía, cartografía, dibujo técnico, publicidad, etc. En estas aplicaciones, la imagen bidimensional no es sólo una representación de un objeto del mundo real, sino un artefacto independiente con valor semántico añadido; los modelos bidimensionales son preferidos por lo tanto, porque dan un control más directo de la imagen que los gráficos 3D por computadora (cuyo enfoque es más semejante a la fotografía que a la tipografía).

# 2.1. Transformación bidimensional.
## 2.1.1. Traslación.
Se aplica una traslación en un objeto para cambiar su posición a lo largo de la trayectoria de una línea recta de una dirección de coordenadas a otra. Convertimos un punto bidimensional al agregar las distancias de traslación, tx y ty la posición de coordenadas original (x,y)

El par de distancia de traslación se llama vector de traslación o vector de cambio. Se pueden expresar las ecuaciones anteriores en una sola ecuación matricial al utilizar vectores de columna para representar las posiciones de coordenadas y el vector de traslación

Los polígonos se trasladan al sumar el vector de traslación a la posición decoordenadas de cada vértice y se vuelve a generar el polígono utilizando un nuevo conjuntode coordenadas y vértices y las especificaciones actuales de los atributos.

<img width="293" height="320" alt="image" src="https://github.com/user-attachments/assets/33d0feb9-f7ee-4349-a8dc-9c147b2db5ee" />

## 2.1.2. Escalamiento.
Una transformación de escalación altera el tamaño de un objeto. Se puede realizar esta operación para polígonos al multiplicar los valores de coordenadas (x, y) de cada vértice por los factores de escalación s x y s  y para producir las coordenadas transformadas (x’, y’ )

## 2.1.3. Rotación.
Se aplica una rotación bidimensional en un objeto al cambiar su posición a lo largo de la trayectoria de una circunferencia en el plano de xy . Para generar una rotación, especificamos un ángulo de rotación θ y la posición (x r , y r ) del punto de rotación (o punto pivote) en torno al cual se gira el objeto.

<img width="302" height="320" alt="image" src="https://github.com/user-attachments/assets/7fe13f4d-89c1-4ead-a23a-e31e85ed62d8" />
 
## 2.1.4. Sesgado.
# 2.2.Representación matricial de las transformaciones
bidimensionales.

(se puede colocar el ejercicio de control con teclas de dirección.)
# 2.3. Trazo de líneas curvas.

## 2.3.1. Bézier.

##v2.3.2. B-spline.

(colocar el ejercicio dibujo de la animación)
# 2.4. Fractales

# 2.5. Uso y creación de fuentes de texto.

