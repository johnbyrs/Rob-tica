Práctica Follow Line de la asignatura de Robótica

![Problema](https://github.com/johnbyrs/Rob-tica/blob/master/Follow_Line/imgs/problema.png)

En la imagen se ve reflejado el problema que se quiere resolver, se encuentra un coche en medio de una pista y se quiere que este sea capaz de circular por el circuito usando de guía la línea roja que hay en el suelo.

El coche va equipado con una cámara la cual será el sensor que se usará para establecer la lógica del controlador que guiará al coche por la pista.

El primer paso para resolver el problema es leer las imágenes dadas por la cámara incorporada y encontrar la línea roja.
Las imágenes leidas por la cámara son como la siguiente 

![img_camara](https://github.com/johnbyrs/Rob-tica/blob/master/Follow_Line/imgs/Fotoraw.png)

Aplicando un filtro de color a esta imagen original se consigue extraer la información de la línea roja, resultando en imágenes así

![img_filtrada](https://github.com/johnbyrs/Rob-tica/blob/master/Follow_Line/imgs/imagen_filtrada.png)

El segundo paso será calcular la distancia entre la posición de la línea roja y el coche(se asume que el coche siempre está en la posición central de la imagen). Esta distancia es el error de posición, que se deberá corregir para que el coche siga la línea correctamente. Como se aprecia en la siguiente imagen cuando aparece una curva la línea se desplaza y se calcula el error sobre esto.
![curva](https://github.com/johnbyrs/Rob-tica/blob/master/Follow_Line/imgs/curva.png)

Una vez obtenido el error se procede al tercer paso que consiste en corregir el rumbo por medio de un controlador PID, el cual recibe el error y calcula los cambios que corrigen el rumbo. Se calculan los valores de PID mediante las formulas siguientes y se actualizan los valores. Los valores kp, ki, kd se han obtenido a base de prueba y error, llegando a unos valores que devuelven un resultado aceptable.

![pid_formulas](https://github.com/johnbyrs/Rob-tica/blob/master/Follow_Line/imgs/PID.png)

<p align="center">
  <img width="460" height="300" src="https://github.com/johnbyrs/Rob-tica/blob/master/Follow_Line/imgs/PID.png">
</p>


