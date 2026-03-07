# Challenge_03_TelecomX-Predicci-n
Challenge_03_TelecomX-Predicción

# Análisis de Retención de Clientes (Churn) - TelecomX 📡

Este proyecto presenta un análisis integral de los datos de clientes de la empresa TelecomX, con el objetivo de identificar patrones de comportamiento que conducen a la cancelación del servicio y desarrollar un modelo predictivo eficaz.

## 📊 Hallazgos Principales del Negocio
A través del Análisis Exploratorio de Datos (EDA), se identificaron los siguientes factores críticos de riesgo:
* **Servicio de Internet:** Los usuarios de **Fibra Óptica** tienen una tasa de deserción del **41.89%** (1,297 cancelaciones de 3,096 clientes).
* **Tipo de Contrato:** El contrato **Mes a mes** es el más vulnerable con un **42.71%** de churn. En contraste, los contratos a dos años son altamente estables con solo un **2.83%** de abandono.
* **Antigüedad (Tenure):** El riesgo es máximo en el **primer mes**, donde el **61.99%** de los clientes nuevos cancelan el servicio.
* **Método de Pago:** El **Cheque Electrónico** está asociado a la mayor tasa de fuga, alcanzando un **45.29%**.

## 🤖 Modelado Predictivo
Se evaluaron y compararon **4 modelos de Machine Learning** distintos para determinar cuál ofrece la mejor capacidad de detección de clientes en riesgo:

| Modelo | Celda de Referencia | Accuracy (Test) | Recall (Churn: Yes) |
| :--- | :---: | :---: | :---: |
| **Random Forest (Optimizado)** | **In [44, 45]** | **76.79%** | **0.80** |
| **Regresión Logística** | In [35] | 79.42% | 0.54 |
| **LinearSVC (SVM)** | In [32] | 79.13% | 0.52 |
| **K-Nearest Neighbors (KNN)** | In [38] | 76.51% | 0.58 |

### **Modelo Seleccionado**
El modelo ganador es el **Random Forest Classifier** optimizado en la celda 44. 
* **Estrategia:** Se aplicó un "podado" del árbol (`max_depth=5`) para evitar el sobreajuste y mejorar la generalización.
* **Eficacia:** Aunque tiene un Accuracy ligeramente menor, posee el **Recall más alto (0.80)**, lo que permite al negocio identificar correctamente al 80% de los desertores reales.
* **Estabilidad:** Se logró un Gap de Accuracy mínimo de **0.0102** entre entrenamiento y prueba.

## 🛠️ Tecnologías y Librerías
* **Lenguaje:** Python.
* **Procesamiento:** `Pandas`, `NumPy`.
* **Visualización:** `Matplotlib`, `Seaborn`.
* **ML & Balanceo:** `Scikit-learn`, `Imbalanced-learn` (SMOTE).
