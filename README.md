# Clasificación de Imágenes Reales vs Generadas por IA con Técnicas de Explicabilidad

Este repositorio contiene el código y los resultados del proyecto de investigación sobre la detección de imágenes sintéticas desarrollado para el ramo **INF473 INTRODUCCIÓN A LA INTELIGENCIA ARTIFICIAL EXPLICABLE**.

**➡️ [Leer el Informe Completo del Proyecto (PDF)](https://usmcl-my.sharepoint.com/:b:/g/personal/santiago_anwandter_usm_cl/EfBlXOpQMe9KuUcKAlu6gmsB9gBThs9-kFH_p3zzKDrgKQ?e=mw4IIL)**

## Descripción del Proyecto

Este proyecto implementa un sistema completo de clasificación binaria para distinguir entre imágenes reales e imágenes generadas por IA, utilizando el dataset [CIFAKE](https://www.kaggle.com/datasets/birdy654/cifake-real-and-ai-generated-synthetic-images) de Kaggle. El enfoque principal está en la aplicación de múltiples técnicas de Inteligencia Artificial Explicable (XAI) para interpretar y visualizar las decisiones del modelo.

### Características Principales

- **Dataset**: CIFAKE con imágenes reescaladas a 224x224 pixels clasificadas como REAL o FAKE
- **Múltiples Arquitecturas**: Modelo CNN personalizado, VGG16 y InceptionV3 con Transfer Learning
- **Técnicas XAI Avanzadas**: Implementación de 6 técnicas diferentes de explicabilidad
- **Evaluación Completa**: Métricas de rendimiento con visualizaciones detalladas

### Flujo de Trabajo

1. **Preparación de Datos**
   - Preprocesamiento específico para cada arquitectura (VGG16/InceptionV3)
   - Augmentación de datos (RandomFlip, RandomRotation, RandomZoom)
   - División eficiente con `tf.data.Dataset` y optimización con `AUTOTUNE`

2. **Arquitecturas de Modelos**
   - **CNN Personalizada**: Modelo secuencial con bloques Conv2D, BatchNormalization, MaxPooling y Dropout
   - **VGG16 Transfer Learning**: Con fine-tuning desde el ultimo bloque convolucional
   - **InceptionV3 Transfer Learning**: Con fine-tuning desde la capa 'mixed9'

3. **Entrenamiento y Optimización**
   - Callbacks avanzados: EarlyStopping y ModelCheckpoint
   - Métricas múltiples: Accuracy, Binary Crossentropy Loss, F1-Score
   - Estrategia de fine-tuning con learning rates adaptativos

4. **Técnicas de Explicabilidad (XAI)**
   - **Grad-CAM**: Mapas de activación de gradientes usando tf-keras-vis
   - **SmoothGrad**: Gradientes suavizados con tf-keras-vis

5. **Visualización y Análisis**
   - Comparación visual de predicciones vs etiquetas reales
   - Mapas de calor superpuestos para cada técnica XAI

### Objetivo

El proyecto no solo busca lograr una clasificación precisa de imágenes reales vs generadas por IA, sino principalmente **comprender y explicar cómo el modelo toma sus decisiones** mediante la implementación y comparación de múltiples técnicas de XAI, proporcionando insights valiosos sobre las características que el modelo considera más importantes para la clasificación.

## Técnicas XAI Implementadas

### 1. Grad-CAM (Gradient-weighted Class Activation Mapping)
- Visualiza las regiones de la imagen que más contribuyen a la predicción
- Utiliza gradientes de la capa convolucional final
- Genera mapas de calor superpuestos sobre la imagen original

### 2. SmoothGrad
- Mejora la calidad de los gradientes mediante promediado de múltiples muestras con ruido
- Implementado con tf-keras-vis y saliency.core
- Reduce el ruido en las visualizaciones de gradientes

## Notebook del Proyecto

Puedes abrir y ejecutar el notebook directamente en Google Colab usando el siguiente botón:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/santii0135/proyecto_xai/blob/main/Proyecto_XAI.ipynb)

## Contribuciones

Este proyecto forma parte del curso INF473 y está enfocado en demostrar la implementación práctica de técnicas de XAI en clasificación de imágenes. 
