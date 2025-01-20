Este repositorio contiene proyectos prácticos enfocados en la implementación de algoritmos de aprendizaje automático no supervisados, con especial énfasis en la **clusterización** y la **reducción de dimensionalidad**. Estos métodos permiten identificar patrones y agrupar datos similares sin la necesidad de etiquetas predefinidas, lo cual es útil para explorar datos desconocidos, realizar segmentación o incluso como preprocesamiento para tareas de aprendizaje supervisado.

### Proyectos

Este repositorio actualmente contiene los siguientes proyectos que aplican tanto **clusterización** como **reducción de dimensionalidad**:

- **Body_Clusterizacion.ipynb**: Un proyecto que aplica tanto la clusterización como la reducción de dimensionalidad en un conjunto de datos de características del cuerpo humano. Se agrupan individuos según métricas físicas como el peso, altura y otras características, y se usa reducción de dimensionalidad para visualizar mejor los resultados.
  
- **Vinos_Clusterizacion.ipynb**: Este proyecto aplica técnicas de clusterización y reducción de dimensionalidad en un conjunto de datos sobre características de vinos. Se agrupan diferentes tipos de vino según propiedades químicas y organolépticas, y se realiza una reducción de dimensionalidad para obtener una visión más clara de las relaciones entre las características de los vinos.

- **body.csv**: Conjunto de datos utilizado para el análisis de clusterización sobre características del cuerpo humano.
  
- **caracteristicas_de_vinos.csv**: Conjunto de datos utilizado para el análisis de clusterización en vinos, con diferentes características como sabor, acidez y aroma.

### Objetivo del Proyecto
El objetivo principal de los proyectos presentes en este repositorio es aplicar técnicas de **clusterización** y **reducción de dimensionalidad** a conjuntos de datos con el fin de descubrir patrones ocultos y realizar segmentaciones significativas. Esto incluye:

- Exploración y preprocesamiento de los datos.
- Selección de las características relevantes para el análisis.
- Aplicación de algoritmos de **clusterización**, como **K-means** y **DBSCAN**, para segmentar los datos.
- Aplicación de técnicas de **reducción de dimensionalidad**, como **PCA**, para visualizar los resultados en espacios de menor dimensión y analizar la importancia relativa de las variables.
- Evaluación de la calidad de los clústeres generados mediante métricas de validación, como la **silhouette score**.
- Análisis de los resultados obtenidos y ajuste de los parámetros para mejorar los modelos.

### Metodologías utilizadas:

- **K-means**: Algoritmo de agrupamiento basado en la cercanía de los puntos en el espacio multidimensional. Muy utilizado en clasificación de mercados y segmentación.
  
- **DBSCAN**: Algoritmo de clustering que define los clústeres en términos de la densidad de puntos cercanos. Es útil cuando los clústeres no tienen una forma esférica uniforme.

- **PCA (Principal Component Analysis)**: Una técnica de reducción de dimensionalidad utilizada para reducir la cantidad de variables sin perder información importante. Esto ayuda a mejorar la visualización y permite comprender mejor las estructuras de los datos.
