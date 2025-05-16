# 📧 Proyecto Detector de Spam

Este proyecto tiene como objetivo la detección automática de mensajes **spam** utilizando algoritmos de aprendizaje automático. Está dividido en dos fases principales: análisis exploratorio y desarrollo de un modelo de clasificación.

## 🧠 Descripción general

Utilizamos el dataset **SMS Spam Collection**, que contiene 5,572 mensajes etiquetados como "ham" (no spam) o "spam". A partir de estos datos, se realiza un análisis exhaustivo seguido de la construcción y evaluación de un modelo de clasificación binaria.

---

## 🧩 Parte I — Análisis Exploratorio

**Notebook:** `ProyectoDSParteI+TuApellido.ipynb`

- Limpieza de datos (valores nulos, duplicados, outliers)
- Visualizaciones univariadas, bivariadas y multivariadas
- Formulación de hipótesis:
  - Los mensajes spam tienden a ser más largos.
  - Palabras como money, “free”, claim aparecen más en spam.
  - Los mensajes spam tienen más signos de exclamación o letras mayúsculas.
  - ¿Los trigramas en mensajes spam son más directos y repetitivos que en mensajes legítimos?
- Análisis estadístico descriptivo
- Detección de valores faltantes

---

## 🤖 Parte II — Clasificación con Machine Learning

**Notebook:** `ProyectoParteIII+TuApellido.ipynb`

### ✔️ Objetivo

Desarrollar y evaluar un modelo de clasificación que determine si un mensaje es spam o no.

### 🧱 Etapas realizadas

- **Vectorización de texto:** mediante `TF-IDF`
- **Selección de características:** usando Chi-cuadrado (`chi2`) con `SelectKBest`
- **Modelos evaluados:**
  - `Multinomial Naive Bayes` (modelo principal)
  - Comparación opcional con `Logistic Regression`
- **Evaluación:**
  - `Accuracy`, `Precision`, `Recall`, `F1-Score`
  - `Matriz de confusión`
  - Interpretación de resultados

### 🧠 Conclusión:

> A lo largo de este proyecto se exploraron diferentes configuraciones para construir un modelo efectivo de detección de mensajes spam, utilizando representaciones basadas en n-gramas y distintos algoritmos de clasificación.

| Modelo                          | Accuracy  | F1 (spam) | Recall (spam) | Comentario                     |
| ------------------------------- | --------- | --------- | ------------- | ------------------------------ |
| **Naive Bayes (TF-IDF + Chi2)** | 91.1%     | 0.68      | 51%           | Rápido y simple, pero limitado |
| **Logistic Regression**         | **96.1%** | **0.89**  | **89%**       | Muy preciso y balanceado       |

Los modelos basados exclusivamente en bigramas o trigramas mostraron limitaciones claras. En particular, el modelo con trigramas presentó un recall más bajo, que los otros dos.

En contraste, el uso de regresión logística con regularización de clases (class_weight='balanced') permitió alcanzar un rendimiento óptimo :

Detecta correctamente el 89% de los mensajes spam, con una precisión del 90%.

Mantiene un accuracy general de más del 96%, superando significativamente al modelo Naive Bayes.

---

## 📁 Estructura del proyecto

📦 spam-detector
┣ 📄 ProyectoDSParteI+Sabido.ipynb
┣ 📄 ProyectoParteIII+Sabido.ipynb
┣ 📄 README.md
┗ 📂 data
┗ 📄 ham-spam.csv
┗ 📄 sms.tsv

## 🔧 Requisitos

- Python 3.8+
- Librerías:
  - `pandas`
  - `scikit-learn`
  - `seaborn`
  - `matplotlib`

```bash
pip install pandas scikit-learn seaborn matplotlib
```
