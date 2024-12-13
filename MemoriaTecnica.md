# Memoria Técnica

## Portada
- **Nombre del Proyecto**: Clasificador de Emociones en imágenes de rostros

- **Profesor**:
  - Francisco Pérez Carbajal
  
  -**Ayudante**:
  - José Eduardo Rodriguez Barrios

- **Integrantes**:  
  - Lara Bustillos Damaris Aylin
  - Evaristo Ramírez Erik
  - Juárez Millán Ángel Andrés

![Emociones]()


## Glosario

-**A**

- **Activación (Activation)**: Función matemática que introduce no linealidad a las salidas de una neurona. Ejemplos: ReLU, Sigmoid, Tanh.

-**Arquitectura (Architecture)**: Diseño estructural de la red neuronal, incluyendo las capas y cómo están conectadas.


-**B**

-**Batch Size (Tamaño del Lote)**: Número de muestras procesadas antes de actualizar los pesos del modelo.


-**C**

-**Capas convolucionales (Convolutional Layers)**: Componentes de una CNN que extraen características locales de las imágenes mediante convoluciones.

-**Capas densas o completamente conectadas (Fully Connected Layers)**: Capas donde cada neurona está conectada a todas las neuronas de la capa previa.

-**Convolución (Convolucion)**: Operación matemática que aplica un filtro sobre una imagen para detectar patrones.


-**D**

-**Dropout**: Técnica de regularización que desactiva aleatoriamente neuronas durante el entrenamiento para prevenir sobreajuste.
Dataset: Conjunto de datos utilizado para entrenar, validar y probar el modelo.


-**E**

-**Epoch**: Una iteración completa sobre todo el conjunto de datos durante el entrenamiento.

-**Extracción de características (Feature Extraction)**: Proceso de identificar patrones relevantes en los datos para clasificarlos.


-**F**

-**Filtro (Kernel)**: Matriz pequeña usada en las convoluciones para detectar características específicas.

-**Función de pérdida (Loss Function)**: Métrica utilizada para medir el error entre las predicciones del modelo y las etiquetas verdaderas.


-**G**

-**Gradiente (Gradient)**: Derivada del error respecto a los pesos de la red, utilizada para actualizarlos.

-**Gradiente descendente (Gradient Descent)**: Algoritmo de optimización que minimiza el error ajustando los pesos de la red.


-**H**

-**Hiperparámetros (Hyperparameters)**: Parámetros configurados manualmente antes del entrenamiento, como la tasa de aprendizaje o el número de filtros.

-**Pooling (Submuestreo)**: Reducción del tamaño de las características mediante operaciones como max pooling o average pooling.


-**M**

-**Matriz de confusión (Confusion Matrix)**: Herramienta para evaluar el rendimiento del clasificador mostrando verdaderos positivos, falsos positivos, etc.


-**O**

-**Overfitting (Sobreajuste)**: Problema en el que el modelo aprende demasiado bien el conjunto de entrenamiento pero falla en generalizar a nuevos datos.

-**Optimización**: Proceso de ajustar los pesos para minimizar la función de pérdida.


-**P**

-**Precision (Precisión)**: Proporción de predicciones correctas en las clases positivas.
Preprocesamiento: Transformaciones aplicadas a los datos para hacerlos adecuados para el modelo.


-**R**

-**Red Neuronal Convolucional (CNN)**: Tipo de red neuronal diseñada para procesar datos con estructura de cuadrícula, como imágenes. Las CNN son especialmente eficaces en tareas de visión por computadora, como la clasificación de imágenes, la detección de objetos y la segmentación semántica.

-**ReLU (Rectified Linear Unit)**: Función de activación que convierte valores negativos en ceros, manteniendo valores positivos.
Regularización: Métodos que evitan que el modelo se ajuste demasiado al conjunto de entrenamiento, como L2 o Dropout.


-**S**
-**Stride (Paso)**: Desplazamiento del filtro en una convolución. Un stride mayor reduce el tamaño de la salida.

-**Softmax**: Función utilizada en la última capa de clasificación para convertir salidas en probabilidades.


-**T**

-**Test Set (Conjunto de pruebas)**: Subconjunto de datos utilizado exclusivamente para evaluar el rendimiento del modelo.
Tensor: Arreglo multidimensional de datos, como una extensión de matrices.


-**V**

-**Validación cruzada (Cross-Validation)**: Técnica para evaluar un modelo dividiendo los datos en varios subconjuntos de entrenamiento y validación.

-**Volumen de salida (Output Volume)**: Dimensiones de los datos resultantes después de aplicar una operación en la red (convolución, pooling, etc.).

## Alcance del proyecto

### Objetivo:

Desarrollar un clasificador capaz de identificar emociones en rostros humanos a partir de imágenes, utilizando técnicas de aprendizaje automático e inteligencia artificial.

### Introducción:

El proyecto busca construir un sistema eficiente que, a través de modelos de aprendizaje profundo, identifique con precisión emociones como alegría, tristeza, sorpresa, enojo, entre otras. Este clasificador será útil en aplicaciones como atención al cliente, análisis de marketing y sistemas educativos.

### Fuentes de información y procedimientos aplicados

Por modelo

-**1. Construcción del modelo**:

### Datasets utilizados: 

FER2013 
Facial Emotion Recognition
Facial Emotion Dataset
Human Face Emotions

-**Algoritmos empleados**: Redes neuronales convolucionales (CNNs), fueron utilizadas varias redes y estrategias para entrenar la red; en una solo una fue entrenada una vez con un mayor número de parámetros(1017575) como un dataset de entrenamiento de 99737 imagenes;  En otra fue usada un red con 684935 parámetros, con 43824 imágenes de entrenamiento, y fue entrenada varias veces modificando el dataset. 
Redes neuronales pre entrenadas.

Frameworks: TensorFlow y Keras.



-**2. Resultados del modelo**:

Precisión promedio alcanzada: 
   *usando la primera red: 50%
   *usando la segunda red: 79%
Indicar métricas de evaluación
	 *una pérdida de 157% para la primera red
	 *una pérdida de  30% para la segunda red


-**3. Pruebas sobre el modelo**:

Realizamos pruebas tales como gráficas del rendimiento del modelo en las fases de entrenamiento y validación, un ajuste de umbrales para reducir falsos positivos o falsos negativos, también calculamos la matriz de confusión para ver cómo se comportan las predicciones con respecto a las etiquetas y nos dimos cuenta que algunas clases estaban desbalanceadas (en parte porque algunos datasets tenían más datos de algunas clases), de esta forma pudimos ajustar el modelo para tener un mejor rendimiento.

![Reporte de_clasificacion_ajustado](../images/reporte_clasi.png)

![Distribución de Clases](../images/matriz_confusion.png)

La matriz muestra que algunas clases están más confundidas que otras. Las principales áreas de confusión entre clases incluyen:
### Clase 0 (Angry):
       Se confunde principalmente con Clase 1 (30 veces), Clase 3 (111 veces) y otras clases en menor medida. Esto sugiere que el modelo tiene dificultades para distinguir entre la Clase 0 y estas clases, probablemente debido a 
       características similares entre ellas.

### Clase 1 (Neutral):
       Se confunde con Clase 0 (383 veces) y Clase 3 (189 veces). Esta clase tiene una alta tasa de falsos negativos con respecto a la Clase 0, pero un buen desempeño en otras clases.

### Clase 2 (Disgust):
       Se confunde con la Clase 3 (208 instancias). Esto sugiere que las características de estas dos clases son similares, y el modelo tiene dificultades para diferenciarlas. Tal vez haya una superposición de características entre estas dos clases que el modelo no puede desentrañar de manera efectiva. También hay 54 instancias de confusión con la Clase 0.

### Clase 3 (Fear):
       Tiene un desempeño relativamente bueno en términos de predicciones correctas (3513), pero aún tiene confusión con varias clases como la Clase 1 y Clase 5 (80 veces). La Clase 3 parece ser una de las más difíciles de predecir correctamente en comparación con las otras clases.

### Clase 4 (Happy):
       Es la clase que tiene un desempeño sobresaliente con más de 2891 predicciones correctas y pocas confusiones, especialmente con Clase 3 y Clase 5. Esto puede indicar que el modelo está bien entrenado para esta clase.

### Clase 5 (Sad):
       Aunque tiene un desempeño razonable, se confunde con la Clase 3 (367 veces) y otras clases como Clase 1. Las clases 3 y 5 parecen estar relacionadas en términos de características.
### Clase 6 (Surprise):
       La Clase 6 tiene el mejor rendimiento en términos de precisión, con 1309 predicciones correctas. Sin embargo, también tiene algunas confusiones con Clase 3 y Clase 4. 


-**4. Conclusiones parciales:**

Observaciones sobre el rendimiento del modelo inicial:
Iniciamos trabajando con una red neuronal convolucional con 5 capas y sin hacer aumentó de datos, lo cual nos arrojaba una precisión baja, de alrededor de 0.5 y tardaba bastante en entrenarse, por lo que nos vimos en la necesidad de aumentar los datos con técnicas de aumento de datos y a probar diferentes estrategias, tales como el uso de redes pre entrenadas, variación en el número de capas y parámetros, balanceo de clases, etc.


Comparativo de modelos

Se probaron múltiples arquitecturas para determinar la mejor combinación de rendimiento y eficiencia:

Modelo A: Una red que hacía uso de redes pre entrenadas como Visual Geometry Group (VGG16), la cual es una red neuronal profunda, con capas convolucionales y de agrupamiento, sin embargo resultó ser muy pesada para nuestro hardware y constantemente cerraba el entorno por falta de RAM. Al hacerle modificaciones para aligerar el modelo, la precisión caía hasta el 60%.



Modelo B: Usamos otras redes ya existentes como MobileNetV2 y EfficientNetB0 que son más eficientes en términos de computación, pues usan menos parámetros y menos recursos del sistema, sin embargo, aún con esto, fallaban y cerraban el entorno, además de que al ajustarlas, la precisión no superó el 70%

Pruebas sobre el desempeño de los modelos destacados
A todos los modelos que trabajamos se les realizaron pruebas como la matriz de confusión, gráficos de desempeño en el entrenamiento y la validación, esto claramente repercute en el parámetro que usamos para elegir el modelo que es el accuracy


-**Selección del modelo final**

Al final se usó el modelo de red neuronal convencional de menos parámetros, pero que fue entrenada de tal forma que el conjunto aun siendo no tan extenso pero sí el más equilibrado, al modificar las imágenes como haciendo zoom, rotarlas o caminando el brillo, a la categoria de imagenes de menor número, aún siendo una red no tan compleja se tiene una mejor precisión y una menor pérdida     




-**Conclusiones generales**

El modelo seleccionado tiene un buen desempeño global para identificar emociones en imágenes con una exactitud del 79%, pero hay algunas clases que están más confundidas que otras, especialmente la Clase 0 y la Clase 1, lo que podría indicar que esas clases tienen características similares que dificultan su separación.

Podríamos mejorar el modelo si encontramos la forma de utilizar redes pre entrenadas, por ejemplo; o si podemos aumentar significativamente los datos de nuestro modelo. Esta última es la parte más complicada pues se necesitan demasiados datos y los datasets que existen en la red no son tan fiables ya que en muchos casos las categorías son ambiguas, las imágenes que vienen en alguna categoría no necesariamente describen lo que dice esta categoría y revisar cada una de estas, en conjuntos muy grandes, resulta ser una tarea pesada.
También se puede intentar correr en algún entorno mejor, que permita ejecutar redes neuronales pesadas como VGG16 para ver cómo se comporta el modelo.





-**Anexos**
-[Repositorio Github](https://github.com/AylinLara/2025-I-proyecto-I/blob/c8c15622e03d37f98cfd2ae5a2e5d09e4225a9af/Clasificador_emociones.ipynb)

- [Conjunto de Datos para la Detección de Conductores Distraídos en Kaggle]()

