# Práctica Reconstrucción 3D

El problema que se quiere resolver en esta práctica consiste en a partir de un par de cámaras que están situadas a a cierta distancia y apuntando al mismo sitio, reconstruir en 3D la escena que capturan. Como se aprecia en la imagen se quiere recontruir la escena con los personajes del universo Mario.

<p align="center">
  <img width="460" height="300" src="https://github.com/johnbyrs/Rob-tica/blob/master/Reconstrucci%C3%B3n3d/imgs/problema.png">
</p>

##Primer paso

Para empezar el proceso se deberá encontrar los puntos carácteristicos de las imágenes capturadas, en este caso se ha usado el detector de bordes canny para extraer esa información de cada imagen capturada por cada cámara. Resultando en la siguiente imagen.

<p align="center">
  <img src="https://github.com/johnbyrs/Rob-tica/blob/master/Reconstrucci%C3%B3n3d/imgs/imgcanny.jpg">
</p>

