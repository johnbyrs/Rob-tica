# Práctica Reconstrucción 3D

El problema que se quiere resolver en esta práctica consiste en a partir de un par de cámaras que están situadas a a cierta distancia y apuntando al mismo sitio, reconstruir en 3D la escena que capturan. Como se aprecia en la imagen se quiere recontruir la escena con los personajes del universo Mario.

<p align="center">
  <img width="460" height="300" src="https://github.com/johnbyrs/Rob-tica/blob/master/Reconstrucci%C3%B3n3d/imgs/problema.png">
</p>

## Primer paso

Para empezar el proceso se deberá encontrar los puntos carácteristicos de las imágenes capturadas, en este caso se ha usado el detector de bordes canny para extraer esa información de cada imagen capturada por cada cámara. Resultando en la siguientes imágenes tomadas desde la cámara izquierda y derecha respectivamente.

<p align="center">
  <img width="360" height="250" src="https://github.com/johnbyrs/Rob-tica/blob/master/Reconstrucci%C3%B3n3d/imgs/imgcanny.jpg">
    <img width="360" height="250" src="https://github.com/johnbyrs/Rob-tica/blob/master/Reconstrucci%C3%B3n3d/imgs/imgcannyr.jpg">
</p>

## Segundo paso

Una vez obtenidos los puntos característicos de cada imagen se procede a hacer una correspondencia de estos entre las imágenes obtenidas de cada cámara. Se deberá trazar la línea epipolar a cada uno de los puntos de una de las imágenes sobre la otra, el punto homólogo será uno de los que esté en esa línea epipolar.
Para encontrar el punto exacto se usará la función de opencv de matchtemplate que se encarga de analizar la correlación entre dos espacios de imagen. De todos los puntos de la línea el que mayor valor de correlación presente será el punto homólogo.

## Tercer paso 

Una vez conseguidos todos los puntos homólogos, se deberá triangular la posición del objeto haciendo uso de esa información. Para ello se busca el punto de corte entre las proyecciones de los puntos de cada imágen. Consiguiendo así los puntos en 3D.

<p align="center">
  <img src="https://github.com/johnbyrs/Rob-tica/blob/master/Reconstrucci%C3%B3n3d/imgs/epipolar.png">
</p>


## Cuarto paso

Una vez obtenidos los puntos en 3D solo queda pintarlos dando lugar a imagenes como la siguiente donde se puede ver una muestra del resultado final.

<p align="center">
  <img width="350" height="460" src="https://github.com/johnbyrs/Rob-tica/blob/master/Reconstrucci%C3%B3n3d/imgs/Resultados.png">
</p>


