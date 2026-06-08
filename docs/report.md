# Titulo: Proyecto Final 
## Asignatura: Aprendizaje Profundo - Avanzado.
## Doccente: Prof.MSc Evelyn Valenzano.
## Fecha: 2026-06-07

## Autores:
- Dario Gaona
- Juan Galeano
- Gabriel Park

## Resumen ejecutivo.
Hemos diseñado un portafolio de Deep Learning con cinco proyectos reproducibles y monitoreados, los cinco modelos implementados son: 1) CNN, 2)DCGAN, 3) RAG QA, 4) LSTM Bidireccional y por ultimo 4) Fine-Tuning de un Transformer. En estos proyectos delegamos el calculo del computo matricial a una GPU T4 en la nube.

## Problemas y Datasets.
Para todos los proyectos recurrimos a Datasets publicos:
 - Cifar-10 para CNN
 - SQuAD para RAG QA
 - Datos propios generados para LSTM.
 - IMDB para Transformers

## Metodologia por modulo.
### Modulo 1: Clasificación de imágenes (CNN)
Arquitectura: Una CNN personalizada de 2 capas convolucionales. \
Hiperparámetros Clave: Optimizador Adam (Funciones de pérdida CategoricalCrossentropy. Batch Size = 64) \
Recursos Computacionales: CPU para el Análisis de datos y GPU Nvidia T4 (Google Colab) para el entrenamiento acelerado. \

### Módulo 2: Generación de Imágenes (DCGAN)
Arquitectura:  El modelo utiliza un Generador basado en convoluciones transpuestas y un Discriminador convolucional. Las imágenes se preprocesan a 64x64x3 y se normalizan en el rango [-1, 1]. \
Hiperparámetros Clave: Tamaño Imagen 64, 3 Canales (RGB), Learning Rate = 2e-4.
Recursos Computacionales: GPU Nvidia T4 obligatoria (Google Colab) debido alalto costo computacional del entrenamiento simultáneo de ambas redes.

### Módulo 2: Sistema de Preguntas y Respuestas (RAG QA)
Arquitectura: Ollama con llama3. \
Hiperparámetros Clave: Modelo de Embeding ollama pull all-minilm, top_k por defecto,   \
Recursos Computacionales: CPU y GPU Nvidia T4 (Google Colab). \

### Modulo 4:  LSTM Time Series 
Arquitectura: Modelo de tipo sequential, capa de entrada que recibe un tensor, capa LSTM con 64 neuronas, capa densa intermedia de 32 neuronas con activación ReLU, capa de salida densa. ). \
Hiperparámetros Clave: longitud de secuencia 50, divsion de datos (train/test) 80/20, optimizador Adam, Funcion de Perdida MSE, epocas 10, batch size 32  \
Recursos Computacionales: CPU y GPU Nvidia T4 (Google Colab). \

### Modulo 5:  Transformer Fine Tunning. 
Arquitectura: Capa de entrada fijo de 100 tokens, Capa Embeding con Token y positional embeding, TransformerBlock MHA, FFN, Pooling y Salida con capa Densa. \
Hiperparámetros: Embeding (vocab_size 10000, maxlen 100, embed_dim 32), Transformer (num_heads 2, ff_fim 32, rate 0.1), Train (optimizer Adam, loss binary_crossentropy, batch_size 64, epochs 3    \
Recursos Computacionales: CPU y GPU Nvidia T4 (Google Colab). \

## Resultados y lecciones aprendidas.
Los resultados fueron satisfactorios en todos los modelos, se logro ahorrar tiempo usando el EarlyStopping de manera adecada para ahorrar la GPU T4, esta demostrado que el transfer learning y el fine-tunning son mucho mas eficientes que entrenar modelos desde cero.


