# Sistema Automatizado de Monitoreo y Control de Ocupación en Tiempo Real Usando Transfer Learning con la Arquitectura MobileNet-SSD

## Resumen

Este proyecto desarrolla un sistema de monitoreo automatizado y control de aforo en tiempo real utilizando Transfer Learning en la arquitectura MobileNet-SSD, optimizado para dispositivos de baja capacidad computacional. MobileNet-SSD equilibra precisión y eficiencia, ideal para entornos con recursos limitados. El sistema detecta y cuenta personas en tiempo real, proporcionando datos precisos sobre el aforo. Implementado en Python y TensorFlow, el modelo se optimiza para dispositivos como Raspberry Pi. Las pruebas demuestran su efectividad en diversos escenarios, ofreciendo una solución viable para el control de aforo en seguridad, salud y gestión de eventos.

##Introducción

### Problema

El crecimiento constante de la población y la creciente necesidad de mantener el control de aforo en espacios públicos y privados han impulsado la búsqueda de soluciones tecnológicas avanzadas. La capacidad de monitorear y controlar el número de personas en un área específica es crucial para garantizar la seguridad, la salud y la eficiencia en la gestión de eventos y lugares concurridos.

### Motivación

Una de las principales motivaciones de este proyecto es desarrollar un sistema que pueda ser implementado en dispositivos de baja capacidad computacional, como Raspberry Pi, permitiendo así un despliegue económico y accesible en una variedad de entornos. La utilización de Transfer Learning en la arquitectura MobileNet-SSD permite crear un sistema eficiente y preciso para la detección y conteo de personas en tiempo real.

### Trabajos Relacionados

Trabajos previos han demostrado la eficacia de los modelos de detección de objetos en tareas similares, pero a menudo requieren recursos computacionales significativos que no son viables para dispositivos de baja capacidad. En este contexto, la elección de MobileNet-SSD es estratégica, ya que combina una arquitectura ligera con una precisión aceptable, optimizada para funcionar en entornos con recursos limitados.

## Plan General del Proyecto

El plan general seguido en este proyecto incluye la recolección de datos, la adaptación y entrenamiento del modelo utilizando Transfer Learning, y la implementación y prueba del sistema en dispositivos de baja capacidad.

### Metodología

La metodología seguida en este proyecto se divide en varias etapas clave: recolección de datos, preprocesamiento de datos, adaptación y entrenamiento del modelo, implementación en dispositivos de baja capacidad y pruebas exhaustivas del sistema.

### Recolección de Datos

Para el entrenamiento del modelo, se recolectaron imágenes de diferentes entornos que representan escenarios de aforo variados. Estas imágenes se encontraban etiquetadas para identificar y contar el número de personas presentes en cada una, se uso la base de datos INRIA person \cite{inriaperson} que proporcionaba una gran selección de imágenes con sus respectivas etiquetas, pero considerando que nuestro objetivo se enfocaba en el aforo de personas y no en la identificación de otros objetos, se uso un lote de 115 imágenes con sus respectivas etiquetas.

### Preprocesamiento de Datos

El preprocesamiento de datos incluyó seleccionar las imagenes que contenian personas en lugar de otros objetos, se agrupo todas esas imagenes en un solo fichero para que posteriormente sea comprimido y luego este pueda ser descomprimido con la ayuda de un script para seleccionar imagenes de entrenamiento, de validación y de test.

### Adaptación y Entrenamiento del Modelo

Se utilizó la técnica de Transfer Learning para adaptar un modelo MobileNet-SSD preentrenado a nuestro conjunto de datos específico. La arquitectura MobileNet-SSD fue seleccionada por su equilibrio entre precisión y eficiencia computacional. El entrenamiento se llevó a cabo en Python utilizando la biblioteca TensorFlow, aprovechando la capacidad de Transfer Learning para reducir el tiempo de entrenamiento y mejorar la precisión en escenarios específicos, para la creación de csv se usó otro script.

### Implementación en Dispositivos de Baja Capacidad

El modelo entrenado se optimizó para su implementación en dispositivos de baja capacidad computacional, como Raspberry Pi. Se realizaron ajustes en los hiperparámetros y se emplearon técnicas de cuantización para reducir el tamaño del modelo sin comprometer significativamente su precisión.

### Pruebas y Validación

El sistema se evaluó en diversos escenarios para validar su efectividad y precisión. Se realizaron pruebas en tiempo real para verificar la capacidad del sistema de detectar y contar personas en distintos entornos y condiciones de iluminación. Tambien se incluyó un script para realizar las pruebas en videos, lo cual tuvo una gran acogida para demostrar los resultados. Para lo cual se usó los scripts de Cartucho para medir el mAP y el de EdjeElectronics que proporcionaba el ejemplo de uso.
