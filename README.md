# VC_P5

Tarea: Tras mostrar opciones para la detección y extracción de información de caras humanas con deepface, la tarea a entregar consiste en proponer un escenario de aplicación y desarrollar un prototipo de temática libreque provoque reacciones a partir de la información extraida del rostro. Los detectores proporcionan información del rostro, y de sus elementos faciales. Ideas inmediatas pueden ser filtros, aunque no hay limitaciones en este sentido. La entrega debe venir acompañada de un gif animado o vídeo de un máximo de 30 segundos con momentos seleccionados de la propuesta. 

# Introducción

A priori, la idea de esta práctica era realizar un filtro de pirata (sombrero y parche) que se activase al guiñar un ojo. Sin embargo, el detector de parpadeos daba muchos falsos positivos al enfocarse en un solo ojo, por lo que, para simplificar, decidí que se activase y desactivase simplemente al parpadear. Aproveché esta funcionalidad y también añadí un contador de parpadeos.

Para el desarrollo de esta práctica, hice uso de Mediapipe, ya que contaba con la experiencia previa de la práctica 2.
La elaboración de este filtro se puede dividir en tres fases principales: en primer lugar, la extracción de los objetos a añadir al video; en segundo lugar, la detección del parpadeo; y, en tercer y último lugar, la inserción de los objetos en el fotograma.

# Extracción de Objetos 

Para la extracción de los objetos, en este caso el parche y el sombrero, probablemente me compliqué más de la cuenta. Lo que hice fue umbralizar el fotograma previamente convertido a escala de grises, realizar una aproximación por contornos para extraer la forma del objeto y, a continuación, usar una máscara con dicha forma comparándola con la imagen original para extraer el objeto en cuestión.


![image](https://github.com/user-attachments/assets/c25d1b75-86e8-4270-bcc0-89580368cfa6)

# Detección del parpadeo

En cuanto a la detección del parpadeo, hago uso del modelo Face Mesh de Mediapipe, que segmenta la cara y asigna un valor numérico a diferentes puntos de la misma. Cada ojo, concretamente, se segmenta en los siguientes vértices.

![image](https://github.com/user-attachments/assets/4e9f0043-ba9a-42c4-9f3b-7b77e47048d4)

Una vez extraída la posición de cada ojo, el código calcula la distancia entre los vértices superiores e inferiores y obtiene la media entre ambos ojos. Cuando esta distancia es demasiado pequeña, concretamente un umbral de 0.26, significa que la cara detectada está parpadeando.

# Inserción de los objetos en la imagen 

Para la inserción de los objetos en la imagen, por un lado, utilizo Face Detection para situar el sombrero sobre la parte superior de la cabeza. Por otro lado, para el ojo, utilizo Face Mesh y coloco el parche en el vértice 263, que corresponde al centro del ojo derecho. Para el "resize" de los objetos, tomo como referencia la cara. En ambos casos, dispongo de un factor para ajustar el tamaño a voluntad en relación con esta.

Finalmente, para insertarlos en el fotograma, de manera similar a la extracción de los objetos iniciales, hago uso de máscaras y lógica entre estas y el fotograma.


# Video demostración

Enlace al video demostración:
https://drive.google.com/file/d/1XwwjLEgzUj2nTSH28UXgVegx93MXdxk4/view?usp=sharing

![image](https://github.com/user-attachments/assets/8dabc3fc-b323-4147-9a35-dd80a1e51a5b)

![image](https://github.com/user-attachments/assets/8e8021f0-62a8-4095-9a65-14690f764eb1)





