# 📊 Machine Learning - Algoritmos No Supervisados: Clusterización y Reducción de Dimensionalidad

## Segmentación de datos con K-Means y PCA

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter" />
  <img src="https://img.shields.io/badge/scikit--learn-ML-green?logo=scikitlearn" />
  <img src="https://img.shields.io/badge/K--Means-Clustering-purple" />
  <img src="https://img.shields.io/badge/PCA-Reducción-red" />
  <img src="https://img.shields.io/badge/Status-Completo-brightgreen" />
</p>

---

## 📋 Descripción

Repositorio con dos proyectos de aprendizaje no supervisado que aplican **K-Means** para segmentación y **PCA** para reducción de dimensionalidad. Cada proyecto trabaja con un dataset diferente, demostrando cómo descubrir patrones ocultos y perfilar grupos sin etiquetas predefinidas.

---

## 📂 Estructura del Repositorio

```
Machine-learning---Algoritmos-No-supervisados/
│
├── Body_Clusterizacion.ipynb              # Proyecto 1: Segmentación por características corporales
├── Vinos_Clusterizacion.ipynb             # Proyecto 2: Segmentación de vinos por propiedades químicas
├── body.csv                               # Dataset de características físicas de personas
├── caracteristicas_de_vinos.csv           # Dataset de propiedades químicas de vinos
└── README.md                              # Documentación del proyecto
```

---

## 🍷 Proyecto 1: Segmentación de Vinos

### Objetivo

Agrupar vinos según sus propiedades químicas y sensoriales (alcohol, acidez, fenoles, prolina, etc.) para identificar perfiles diferenciados sin usar la etiqueta original de tipo de vino.

### Variables del Dataset

`Alcohol`, `Malic` (ácido málico), `Ash` (cenizas), `Alcalinity`, `Magnesium`, `Phenols`, `Flavanoids`, `Nonflavanoids`, `Proanthocyanins`, `Color`, `Hue`, `Dilution`, `Proline`.

### Metodología

1. **EDA** — Inspección de estructura, tipos de datos y verificación de nulos.
2. **Escalado** — Normalización con `MinMaxScaler` para igualar escalas entre variables.
3. **Método del codo** — Evaluación de inercia para K de 1 a 10, determinando **K=3** como óptimo.
4. **K-Means** — Clusterización con 3 clusters y 300 iteraciones máximas.
5. **PCA (2 componentes)** — Reducción de dimensionalidad para visualización 2D de los clusters.
6. **Biplot** — Gráfico de flechas que muestra la contribución de cada variable original a las componentes principales, permitiendo interpretar qué características definen cada cluster.

### Hallazgos

- Las dos primeras componentes de PCA capturan una proporción significativa de la varianza total.
- Los 3 clusters se separan claramente en el espacio PCA, validando la segmentación.
- Variables como `Flavanoids`, `Proline` y `Color` son las que más contribuyen a la diferenciación entre grupos.

---

## 🏋️ Proyecto 2: Segmentación por Características Corporales

### Objetivo

Segmentar personas según métricas físicas (densidad corporal, porcentaje de grasa, edad, peso, altura) para identificar perfiles de salud y composición corporal.

### Variables del Dataset

`Sexo`, `Estado civil`, `Densidad corporal`, `Porcentaje de grasa`, `Edad`, `Peso (libras)`, `Altura (pulgadas)`.

### Metodología

1. **EDA** — Detección de codificación del archivo con `chardet`, carga con encoding `ISO-8859-1`.
2. **Selección de variables** — Se excluyen las categóricas (`Sexo`, `Estado civil`) para el modelo, reintegrándolas después para el perfilamiento.
3. **Escalado** — `MinMaxScaler` para normalizar todas las variables numéricas.
4. **Método del codo** — Evaluación de K de 2 a 10, determinando **K=4** como óptimo.
5. **K-Means** — Clusterización con 4 clusters.
6. **PCA (2 componentes)** — Reducción a 2D con análisis de varianza explicada (89.32% acumulada entre PCA_1 y PCA_2).
7. **Heatmap de componentes** — Visualización de la contribución de cada variable a las componentes principales.
8. **Perfilamiento de clusters** — Análisis descriptivo (`describe()`) de cada grupo + tops por grasa, peso y altura.

### Hallazgos

- **Cluster 1:** Personas adultas mayores, más bajas y con mayor porcentaje de grasa — perfil con mayor riesgo de salud.
- **Cluster 2:** Personas jóvenes con menor porcentaje de grasa, posiblemente por metabolismo más acelerado.
- **Cluster 0:** Personas con mayor altura.
- **PCA_1 explica el 57.92%** y **PCA_2 el 31.40%** de la varianza, logrando una representación del 89.32% en solo 2 dimensiones.
- La población del dataset es predominantemente mujeres casadas.

---

## 🛠️ Stack Tecnológico

- **Lenguaje:** Python 3.x
- **Análisis de datos:** Pandas, NumPy
- **Visualización:** Matplotlib, Seaborn
- **Preprocesamiento:** Scikit-learn (`MinMaxScaler`)
- **Clusterización:** Scikit-learn (`KMeans`)
- **Reducción de dimensionalidad:** Scikit-learn (`PCA`)
- **Detección de encoding:** chardet

---

## 🚀 Cómo Ejecutar

1. Clona el repositorio:
   ```bash
   git clone https://github.com/Mateo-Rua/Machine-learning---Algoritmos-No-supervisados---Clusterizaci-n-y-Reduccion-de-dimencionalidad.git
   cd Machine-learning---Algoritmos-No-supervisados---Clusterizaci-n-y-Reduccion-de-dimencionalidad
   ```

2. Instala las dependencias:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn chardet
   ```

3. Ejecuta los notebooks:
   ```bash
   jupyter notebook Body_Clusterizacion.ipynb
   jupyter notebook Vinos_Clusterizacion.ipynb
   ```

---

## 💡 Principales Conclusiones

1. **K-Means + PCA es una combinación poderosa** para descubrir y visualizar segmentos naturales en datos multidimensionales sin etiquetas previas.

2. **El escalado es imprescindible** antes de aplicar K-Means y PCA, ya que ambos algoritmos son sensibles a la escala de las variables.

3. **El método del codo** permitió determinar el número óptimo de clusters en ambos datasets, evitando segmentaciones arbitrarias.

4. **PCA no solo reduce dimensionalidad**, sino que permite interpretar qué variables originales definen cada componente, aportando explicabilidad al modelo.

5. **El perfilamiento post-clustering** transforma los grupos numéricos en insights accionables para el negocio (perfiles de riesgo de salud, tipos de vino diferenciados).


---

## 👤 Autor

**Mateo Rua**

[![GitHub](https://img.shields.io/badge/GitHub-Mateo--Rua-181717?logo=github)](https://github.com/Mateo-Rua)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Mateo_Londoño_Rúa-0077B5?logo=linkedin)](https://www.linkedin.com/in/mateo-londono-rua117/)

---

> *Proyectos de aprendizaje no supervisado aplicando K-Means y PCA para segmentación y descubrimiento de patrones en datos de salud y enología.*
