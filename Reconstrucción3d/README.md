# Práctica Reconstrucción 3D

El problema que se quiere resolver en esta práctica consiste en a partir de un par de cámaras que están situadas a a cierta distancia y apuntando al mismo sitio, reconstruir en 3D la escena que capturan. Como se aprecia en la imagen se quiere recontruir la escena con los personajes del universo Mario.

<p align="center">
  <img width="460" height="300" src="https://github.com/johnbyrs/Rob-tica/blob/master/Reconstrucci%C3%B3n3d/imgs/problema.png">
</p>

## Primer paso

Para empezar el proceso se deberá encontrar los puntos carácteristicos de las imágenes capturadas, en este caso se ha usado el detector de bordes canny para extraer esa información de cada imagen capturada por cada cámara. Resultando en la siguiente imagen.

<p align="center">
  <img width="460" height="300" src="https://github.com/johnbyrs/Rob-tica/blob/master/Reconstrucci%C3%B3n3d/imgs/imgcanny.jpg">
</p>

## Segundo paso

Una vez obtenidos los puntos característicos de cada imagen se procede a hacer una correspondencia de estos entre las imágenes obtenidas de cada cámara. Se deberá trazar la línea epipolar a cada uno de los puntos de una de las imágenes sobre la otra, el punto homólogo será uno de los que esté en esa línea epipolar, por lo que se usará la función de opencv de matchtemplate sobre los puntos de la línea para encontrar los puntos homólogos

## Tercer paso 

Rectificar la imagen y transformar las coordenadas 2D de las imágenes obtenidas por la cámara a coordenadas 3D, este proceso se realiza mediante las matrices de proyección, se consigue triangular triangular la posición de cada punto.

## Cuarto paso

Una vez obtenidos los puntos en 3D solo queda pintarlos dando lugar a la siguiente imagen donde se puede ver una muestra del resultado final.

<p align="center">
  <img width="350" height="460" src="https://github.com/johnbyrs/Rob-tica/blob/master/Reconstrucci%C3%B3n3d/imgs/Resultados.png">
</p>


