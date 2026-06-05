# Laboratorio4_ia2
Laboratorio4_ia2
 # DCGAN para Generación de Espectrogramas Musicales con GTZAN

## Descripción

Este proyecto implementa una **Deep Convolutional Generative Adversarial Network (DCGAN)** utilizando PyTorch para generar imágenes sintéticas de espectrogramas musicales a partir del conjunto de datos GTZAN. El objetivo es que el modelo aprenda los patrones visuales presentes en los espectrogramas reales y sea capaz de producir nuevas muestras con características similares.

El proyecto fue desarrollado y entrenado utilizando aceleración por GPU mediante CUDA, permitiendo reducir significativamente los tiempos de entrenamiento.

---

## Objetivos

- Comprender el funcionamiento de las Redes Generativas Antagónicas (GAN).
- Implementar una arquitectura DCGAN utilizando PyTorch.
- Entrenar un generador y un discriminador de forma simultánea.
- Analizar el comportamiento del entrenamiento mediante métricas de pérdida.
- Generar espectrogramas sintéticos a partir de ruido aleatorio.

---

## Dataset

Se utilizó el conjunto de datos **GTZAN Genre Collection**, ampliamente empleado en tareas de clasificación y análisis musical.

Características principales:

- 10 géneros musicales.
- 100 archivos de audio por género.
- 1000 canciones en total.
- Conversión de audio a espectrogramas para el entrenamiento.

---

## Tecnologías Utilizadas

- Python
- PyTorch 2.5.1
- CUDA 12.1
- NumPy
- Matplotlib
- Pillow
- Kaggle API

---

## Arquitectura del Modelo

### Generador

El generador recibe un vector de ruido aleatorio y produce una imagen sintética de espectrograma mediante capas convolucionales transpuestas, Batch Normalization y funciones de activación ReLU.

### Discriminador

El discriminador recibe imágenes reales o generadas y determina la probabilidad de que pertenezcan al conjunto de datos original utilizando capas convolucionales y funciones de activación LeakyReLU.

---

## Hiperparámetros Utilizados

| Parámetro | Valor |
|------------|---------|
| Épocas | 200 |
| Learning Rate | 0.0002 |
| Beta1 | 0.5 |
| Tamaño de lote | 64 |
| Dimensión del vector latente | 100 |
| Optimizador | Adam |
| Función de pérdida | Binary Cross Entropy (BCE) |

---

## Resultados del Entrenamiento

Resultados obtenidos al finalizar las 200 épocas:

| Métrica | Valor |
|----------|---------|
| Loss Generador (G) | 0.9379 |
| Loss Discriminador (D) | 1.2183 |
| D(x) | 0.5025 |
| D(G(z)) | 0.3989 |

---

## Interpretación de Resultados

Los resultados muestran que el entrenamiento fue estable y mantuvo un equilibrio adecuado entre el generador y el discriminador. El generador alcanzó una pérdida de **0.9379**, mientras que el discriminador obtuvo una pérdida de **1.2183**, indicando que ambos modelos aprendieron de manera conjunta sin evidencias de colapso o divergencia.

Además, el discriminador asignó una confianza promedio de **0.5025** a las muestras reales y **0.3989** a las muestras generadas. Esto sugiere que el generador logró producir ejemplos cada vez más parecidos a los datos originales, dificultando la tarea del discriminador. En conjunto, los resultados indican que el modelo fue capaz de aprender los patrones principales presentes en los espectrogramas musicales y generar nuevas muestras sintéticas con una calidad aceptable.

---


## Conclusiones

La implementación de DCGAN permitió generar espectrogramas sintéticos aprendiendo directamente de las características visuales presentes en el conjunto de datos GTZAN. Los resultados obtenidos evidencian un entrenamiento estable y una adecuada interacción entre el generador y el discriminador. Este trabajo demuestra el potencial de las redes generativas profundas para la creación de contenido sintético y constituye una base sólida para futuras investigaciones relacionadas con generación de audio, aumento de datos y modelos generativos avanzados.
