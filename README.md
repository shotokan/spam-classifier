# 📧 Spam Detector con Machine Learning

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
  - Palabras como “win”, “free”, “cash” aparecen más en spam.
  - Los mensajes spam tienen más signos de exclamación o letras mayúsculas.
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
  - Comparación opcional con `KNN` u otros clasificadores
- **Evaluación:**
  - `Accuracy`, `Precision`, `Recall`, `F1-Score`
  - `Matriz de confusión`
  - Interpretación de resultados

### ✅ Resultado

El modelo basado en **Naive Bayes** logró una alta precisión en la detección de mensajes spam, siendo más eficiente que otros enfoques como KNN debido a la naturaleza textual y dispersa del dataset.

## 🤔 ¿Por qué se usa Naive Bayes y no KNN?

### ✅ Ventajas de Naive Bayes:

- Es un modelo **probabilístico** especialmente eficaz para datos de texto.
- Funciona muy bien con datos **altamente dispersos** como los generados por TF-IDF.
- Tiene un **entrenamiento y predicción muy rápidos**, ideal para grandes volúmenes de texto.
- Requiere poca configuración y es **robusto al ruido** en el texto.

### ⚠️ Desventajas de KNN para este caso:

- KNN es un **modelo basado en distancias**, lo que lo vuelve ineficiente para datos de texto (alta dimensionalidad).
- Requiere comparar cada nuevo mensaje con **todo el dataset**, lo cual **ralentiza la predicción**.
- Es **sensible a outliers** y **no escala bien** en tareas de clasificación textual.

### 🧠 Conclusión:

> En tareas de clasificación de texto como detección de spam, **Naive Bayes es más eficiente, preciso y adecuado que KNN**, y es una de las elecciones clásicas para este tipo de problemas.

---

## 📁 Estructura del proyecto

📦 spam-detector
┣ 📄 ProyectoDSParteI+TuApellido.ipynb
┣ 📄 ProyectoParteIII+TuApellido.ipynb
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
