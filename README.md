# VC_P5

Tarea: Tras mostrar opciones para la detección y extracción de información de caras humanas con deepface, la tarea a entregar consiste en proponer un escenario de aplicación y desarrollar un prototipo de temática libreque provoque reacciones a partir de la información extraida del rostro. Los detectores proporcionan información del rostro, y de sus elementos faciales. Ideas inmediatas pueden ser filtros, aunque no hay limitaciones en este sentido. La entrega debe venir acompañada de un gif animado o vídeo de un máximo de 30 segundos con momentos seleccionados de la propuesta. 

# Introducción

A priori la idea de esta práctica era la realización de un filtro de pirata (sombrero y parche) que se activase al guiñar un ojo, el detector de parpadeos dectaba muchos falsos positivos al enfocarme en un solo ojo por lo que finalmente en lugar de complicarme hice que se activase y desactivase simplemente al parpadear. Aproveche esto y tambien añadí un contador de parpadeos.

Para el desarrollo de esta práctica hice uso de mediapipe pues contaba con la experiencia previa de la práctica 2. 
La elaboración de este filtro se puede dividir en tres fases principales. En primer lugar la extraccion de los objetos a añadir al video, en segundo lugar la detección del parpadeo y en tercer y último lugar la insersición de los objetos en el frame.

# Extracción de Objetos 

Para la extracción de los objetos, en este caso el parche y el sombrero probablemente me compliqué mas de las cuenta. Lo que hice fue umbralizar el frame previamente convertido a escala de grises, aproximación por contornos para entraer la forma del objeto y a continuación hacer uso de una máscara con dicha forma comparandola a la imagen orginal para extraer el objeto en cuestión.


![image](https://github.com/user-attachments/assets/c25d1b75-86e8-4270-bcc0-89580368cfa6)

# Detección del parpadeo

# Inserción de los objetos en la imagen 

# Video demostración



