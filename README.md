# Proyecto XAI - INF473

Este proyecto ha sido desarrollado para el ramo **INF473 INTRODUCCIÓN A LA INTELIGENCIA ARTIFICIAL EXPLICABLE**.

## Descripción## Descripción del Proyecto

Este proyecto se enfoca en la clasificación de imágenes reales versus aquellas generadas por IA, utilizando el dataset "CIFAKE" de Kaggle. Se implementa una Red Neuronal Convolucional en TensorFlow para distinguir entre imágenes La clasificabión de las imágenes.

El flujo de trabajo principal incluye:
1.  **Preparación de Datos:** Carga, preprocesamiento (normalización, redimensión a 224x224) y división de datos en conjuntos de train, validación y test. Se utilizan `tf.data.Dataset` para la ingesta eficiente de datos.
2.  **Modelo CNN:** Construcción de una CNN secuencial con bloques convolucionales (Conv2D, MaxPooling2D, Dropout) y capas densas, compilada con Adam y 'binary_crossentropy'.
3.  **Entrenamiento y Evaluación:** Entrenamiento del modelo utilizando callbacks como **EarlyStopping** para prevenir el sobreajuste y optimizar la duración del entrenamiento. Se realiza la visualización de curvas de aprendizaje y una evaluación final con matriz de confusión.
4.  **Explicabilidad (XAI):** Aplicación de técnicas **LIME** y **Grad-CAM** para interpretar las predicciones del modelo, visualizando las regiones de las imágenes que más influyen en la decisión de la CNN.

El objetivo es no solo lograr una clasificación precisa, sino también comprender cómo el modelo toma sus decisiones, gracias a las técnicas de XAI.


## Notebook del Proyecto

Puedes abrir y ejecutar el notebook directamente en Google Colab usando el siguiente botón:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/santii0135/proyecto_xai/blob/main/Proyecto_XAI.ipynb)
