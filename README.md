<div align="center">

# 📡 Telecom X — Predicción de cancelación de clientes

### 🤖 Parte 2 · Machine Learning para anticipar el churn

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Análisis-150458?logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Scikit-learn](https://img.shields.io/badge/scikit--learn-Modelado-F7931E?logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![Plotly](https://img.shields.io/badge/Plotly-Visualización-3F4F75?logo=plotly&logoColor=white)](https://plotly.com/python/)
[![Colab](https://img.shields.io/badge/Google_Colab-Abrir-F9AB00?logo=googlecolab&logoColor=white)](https://colab.research.google.com/github/MaferVelde/Telecom-X-parte-2/blob/main/Telecom_X_parte_2.ipynb)

**[Parte 1: análisis exploratorio](https://github.com/MaferVelde/Telecom-X)** · **[Parte 2: modelado predictivo](https://github.com/MaferVelde/Telecom-X-parte-2)**

</div>

---

## 📖 Descripción

Esta segunda fase convierte los hallazgos exploratorios de Telecom X en un problema de **clasificación supervisada**. El objetivo es identificar clientes con riesgo de cancelar el servicio y aportar información útil para orientar acciones preventivas de retención.

El proyecto abarca preparación de datos, codificación, análisis de correlación, comparación de algoritmos, tratamiento del desbalance, ajuste de hiperparámetros e interpretación del modelo final.

## 🎯 Objetivos

- Preparar los datos obtenidos en la Parte 1 para el modelado.
- Analizar el balance de la variable objetivo.
- Entrenar y comparar algoritmos de clasificación.
- Evaluar modelos con métricas apropiadas para churn.
- Optimizar modelos mediante pipelines y ajuste de hiperparámetros.
- Interpretar las variables relacionadas con el riesgo de cancelación.
- Traducir los resultados en recomendaciones de negocio.

## 🔄 Flujo de trabajo

1. 🧹 **Preparación:** eliminación de identificadores y separación de predictores y objetivo.
2. ⚙️ **Transformación:** codificación de variables categóricas y normalización cuando se requiere.
3. 🔍 **Análisis:** revisión del balance, correlaciones y variables relevantes.
4. 🤖 **Modelado:** baseline, Árbol de Decisión, KNN y Regresión Logística.
5. 🎛️ **Optimización:** validación cruzada, remuestreo y ajuste de hiperparámetros.
6. 📏 **Evaluación:** accuracy, precision, recall, F1-score y matrices de confusión.
7. 💡 **Interpretación:** análisis de coeficientes y acciones de retención.

## 🤖 Modelos evaluados

| Modelo | Función en el análisis |
|---|---|
| DummyClassifier | Establecer el desempeño mínimo de referencia |
| Árbol de Decisión | Evaluar una alternativa interpretable sin normalización |
| K-Nearest Neighbors | Probar un enfoque por proximidad y optimizar el número de vecinos |
| Regresión Logística | Combinar desempeño e interpretación de coeficientes |

También se probaron estrategias de balanceo como **oversampling**, **undersampling** y **SMOTEENN**.

## 🏆 Resultado del modelo final

La **Regresión Logística con normalización y regularización L2** obtuvo el mejor desempeño global y fue seleccionada como modelo final.

| Métrica | Resultado |
|---|---:|
| Accuracy | 0.8057 |
| Precision — churn | 0.6563 |
| Recall — churn | 0.5651 |
| F1-score — churn | 0.6073 |

La evaluación no se limitó a la accuracy. Debido al desbalance moderado y al costo de no detectar clientes que podrían cancelar, se consideraron especialmente **recall** y **F1-score** para la clase churn.

> Las métricas corresponden al conjunto de prueba registrado en el notebook. El modelo es un ejercicio académico y requiere validación adicional antes de utilizarse en producción.

## 🔎 Interpretación de variables

Las señales con mayor asociación positiva con la cancelación incluyen:

- cargos totales y mensuales elevados;
- contrato mensual;
- facturación sin papel y cheque electrónico;
- ausencia de soporte, seguridad, respaldo o protección del dispositivo;
- servicio de internet por fibra óptica.

Las señales asociadas con menor probabilidad de cancelación incluyen:

- mayor antigüedad;
- contratos de uno o dos años;
- servicio telefónico;
- determinados métodos de pago automáticos;
- servicios adicionales de soporte y protección.

> Los coeficientes permiten interpretar asociaciones dentro del modelo, pero no demuestran causalidad.

## 💡 Recomendaciones de negocio

1. Activar campañas de retención temprana para clientes de baja antigüedad.
2. Incentivar la transición de contratos mensuales a planes de uno o dos años.
3. Promover soporte, seguridad, respaldo y protección como paquetes de valor agregado.
4. Fomentar métodos de pago automáticos.
5. Investigar la experiencia de los clientes con fibra óptica.
6. Usar el riesgo estimado para priorizar campañas, acompañado de reglas de negocio y monitoreo.

## 🛠️ Tecnologías y competencias

- **Python, Pandas y NumPy:** preparación y manipulación de datos.
- **Scikit-learn:** pipelines, clasificación, validación, métricas y ajuste.
- **Matplotlib, Seaborn y Plotly Express:** exploración y comunicación visual.
- **Google Colab:** desarrollo y ejecución del flujo analítico.
- **Competencias:** clasificación, evaluación, desbalance, interpretación e insights de negocio.

## 📁 Estructura del repositorio

```text
Telecom-X-parte-2/
├── Telecom_X_parte_2.ipynb  # Preparación, modelado y evaluación
├── datos_tratados.csv        # Dataset procesado en la Parte 1
├── champion (1).pkl          # Modelo serializado del proyecto
└── README.md                 # Documentación
```

## 🚀 Cómo ejecutarlo

### ☁️ Google Colab

[![Abrir en Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MaferVelde/Telecom-X-parte-2/blob/main/Telecom_X_parte_2.ipynb)

Abre el notebook, selecciona **Conectar** y ejecuta las celdas en orden o utiliza **Entorno de ejecución → Ejecutar todas**.

### 💻 Entorno local

```bash
git clone https://github.com/MaferVelde/Telecom-X-parte-2.git
cd Telecom-X-parte-2
jupyter notebook Telecom_X_parte_2.ipynb
```

Requiere `pandas`, `numpy`, `scikit-learn`, `imbalanced-learn`, `matplotlib`, `seaborn` y `plotly`.

## 🔗 Origen de los datos

Este repositorio continúa **[Telecom X — Parte 1: análisis exploratorio](https://github.com/MaferVelde/Telecom-X)**, donde se realizaron la extracción, limpieza, transformación y exploración.

## 🧭 Limitaciones y siguientes pasos

- Validar el modelo con datos nuevos o de otro periodo.
- Ajustar el umbral según el costo de falsos positivos y falsos negativos.
- Comparar modelos adicionales y documentar los experimentos.
- Evaluar calibración, estabilidad y posible deriva de datos.
- Crear un prototipo que muestre el riesgo y los factores relevantes por cliente.

## 👩‍💻 Autora

**María Fernanda Velderrain Parra**<br>
Ingeniera en Biotecnología en transición hacia Ciencia de Datos

[![LinkedIn](https://img.shields.io/badge/LinkedIn-María_Fernanda_Velderrain-0077B5?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/maria-fernanda-velderrain-parra/)
[![GitHub](https://img.shields.io/badge/GitHub-MaferVelde-181717?logo=github&logoColor=white)](https://github.com/MaferVelde)

## 🎓 Contexto académico

Proyecto desarrollado como parte del **Challenge Telecom X — Parte 2** de **Alura Latam**, con fines educativos y de portafolio profesional.
