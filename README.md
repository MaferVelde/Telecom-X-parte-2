# 📊 Telecom X – Análisis de Evasión de Clientes (Parte 2)

**Autora:** Maria Fernanda Velderrain Parra  

---

## 🧠 Introducción

Este repositorio corresponde a la **Parte 2 del Challenge Telecom X**, centrada en el desarrollo de un **modelo predictivo de Machine Learning** para anticipar la cancelación de clientes (*churn*) en Telecom X.

A partir del conjunto de datos previamente tratado en la Parte 1, se diseñó un flujo completo de modelado que incluye preparación de datos, entrenamiento de múltiples algoritmos de clasificación, evaluación comparativa de métricas e interpretación de resultados. El objetivo final es transformar los hallazgos analíticos en **insights accionables** que contribuyan a mejorar la retención y la experiencia del cliente.

---

## 🎯 Objetivos del proyecto

- Preparar y transformar los datos para su uso en modelos de Machine Learning.
- Analizar el balance de clases y su impacto en el desempeño de los modelos.
- Entrenar y comparar distintos algoritmos de clasificación.
- Evaluar el desempeño utilizando métricas adecuadas para problemas de churn.
- Interpretar la relevancia de las variables predictoras.
- Formular conclusiones y recomendaciones estratégicas basadas en evidencia cuantitativa.

---

## 🧹 Preparación y preprocesamiento de datos

Durante esta etapa se llevaron a cabo las siguientes actividades:

- Carga del dataset procesado en la Parte 1.
- Eliminación de variables no predictivas (identificadores).
- Codificación de variables categóricas.
- Separación de variables numéricas y categóricas.
- Análisis de la distribución de la variable objetivo para detectar posible desbalance de clases.
- Aplicación de normalización exclusivamente en modelos sensibles a la escala.
- Implementación de pipelines para estructurar y estandarizar el flujo de entrenamiento.

Este proceso permitió garantizar consistencia, reproducibilidad y adecuada preparación del conjunto de datos para el modelado.

---

## 🤖 Modelado y evaluación

Se entrenaron y compararon los siguientes modelos:

- **Baseline (DummyClassifier):** modelo de referencia para establecer un punto de comparación inicial.
- **Árbol de Decisión:** modelo interpretable y no sensible a la escala.
- **K-Nearest Neighbors (KNN):** algoritmo basado en proximidad en el espacio de características.
- **Regresión Logística:** modelo lineal sensible a la escala, seleccionado como modelo final por su desempeño y capacidad explicativa.

### 📊 Métricas de evaluación

El desempeño se evaluó mediante:

- Accuracy  
- Precision  
- Recall  
- F1-score  
- Matrices de confusión (valores absolutos y normalizados)

Dado el desbalance moderado de clases y la relevancia de identificar correctamente a los clientes con riesgo de cancelación, se priorizaron métricas como **Recall** y **F1-score**, más representativas que la accuracy en este contexto.

---

## 📈 Importancia de las variables

A partir del modelo final (Regresión Logística), se analizó la contribución relativa de las variables al proceso de predicción.

Los principales factores asociados al churn fueron:

- Cargos mensuales y totales elevados.
- Baja antigüedad del cliente.
- Contratos de corto plazo.
- Determinadas configuraciones de servicios adicionales.
- Tipo de servicio de internet.

En contraste, una mayor permanencia y contratos de mayor duración se identificaron como factores protectores frente a la cancelación.

Este análisis aporta claridad sobre los drivers clave del abandono y facilita la toma de decisiones estratégicas.

---

## 📌 Conclusiones

La **Regresión Logística** presentó el mejor desempeño global, logrando un balance adecuado entre precisión y capacidad de detección de clientes en riesgo.

Los resultados evidencian que la cancelación es un fenómeno multifactorial, influenciado por variables contractuales, económicas y de relación con el servicio. La implementación de modelos predictivos permite anticipar comportamientos de riesgo y habilita estrategias de retención basadas en datos.

---

## 💡 Recomendaciones estratégicas

- Diseñar estrategias de retención temprana enfocadas en clientes con baja antigüedad.
- Incentivar la migración hacia contratos de mayor duración.
- Priorizar campañas comerciales dirigidas a clientes con alta probabilidad de churn.
- Integrar el modelo como sistema de alerta temprana dentro de los procesos de negocio.

---

## 🛠️ Tecnologías utilizadas

- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- Matplotlib  
- Seaborn  
- Plotly Express  
- Pipelines (Scikit-learn)  
- Google Colab  

---

## 📂 Estructura del repositorio

```
📦 Telecom-X-parte2
┣ 📜 README.md
┣ 📊 datos_tratados.csv/
┣ 🤖 champion (1).pkl/
┗ 📓 Telecom_X_parte_2.ipynb/
```

---

## 📘 Nota final

Este proyecto forma parte del **Challenge Telecom X – Parte 2** del programa de formación de Alura. Fue desarrollado con fines académicos y analíticos, aplicando metodologías de Data Science y Machine Learning a un caso de negocio realista orientado a la retención de clientes.
