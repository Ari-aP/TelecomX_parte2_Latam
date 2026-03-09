# TelecomX_parte2_Latam

Proyecto de **Machine Learning** enfocado en predecir la cancelación de clientes (Churn) en una empresa de telecomunicaciones utilizando técnicas de preparación de datos, análisis exploratorio y modelos de clasificación.

Este proyecto forma parte del desafío **ONE - Data Science LATAM** y tiene como objetivo identificar los factores que influyen en la cancelación del servicio para apoyar la toma de decisiones estratégicas de retención de clientes.

---

# 🎯 Objetivo del Proyecto

El objetivo principal es **desarrollar modelos predictivos capaces de identificar clientes con alta probabilidad de cancelar el servicio**.

A partir de los datos históricos de clientes se busca:

- Identificar variables que influyen en la cancelación
- Preparar los datos para modelado predictivo
- Entrenar modelos de Machine Learning
- Evaluar el desempeño de los modelos
- Generar insights estratégicos para reducir el churn

---

# 📁 Estructura del Proyecto

```
TelecomX_parte2_Latam
│
├── TelecomX_parte2_Latam.ipynb   # Notebook principal con todo el análisis
├── datos_tratados.csv            # Dataset limpio listo para modelado
└── README.md                     # Documentación del proyecto
```

---

# 🧹 Preparación de los Datos

Antes de entrenar los modelos se realizaron varias etapas de preparación de datos.

## 1️⃣ Eliminación de columnas irrelevantes

Se eliminaron variables que no aportaban valor al modelo predictivo, como identificadores únicos.

Ejemplo:

- `customerID`

---

## 2️⃣ Codificación de variables categóricas

Las variables categóricas fueron transformadas a formato numérico mediante **One-Hot Encoding** para poder ser utilizadas por los modelos de Machine Learning.

Se utilizó:

```python
pd.get_dummies()
```

Esto permitió transformar variables como:

- Tipo de contrato
- Método de pago
- Tipo de servicio de internet

---

## 3️⃣ División del conjunto de datos

Los datos se separaron en conjuntos de:

- **Entrenamiento (80%)**
- **Prueba (20%)**

Utilizando:

```python
train_test_split()
```

Esto permite evaluar el desempeño del modelo en datos que no fueron utilizados durante el entrenamiento.

---

## 4️⃣ Balanceo de clases

El dataset presentaba **desbalance entre clientes que cancelaron y los que permanecieron activos**.

Para mejorar el aprendizaje del modelo se aplicó:

**SMOTE (Synthetic Minority Over-sampling Technique)**

Este método genera ejemplos sintéticos de la clase minoritaria.

Librería utilizada:

```
imbalanced-learn
```

---

## 5️⃣ Normalización de datos

Para modelos sensibles a la escala de los datos se aplicó **estandarización** utilizando:

```python
StandardScaler()
```

Esto permite que variables con diferentes magnitudes no afecten el desempeño del modelo.

---

# 📈 Análisis Exploratorio (EDA)

Se realizaron visualizaciones para entender los factores asociados a la cancelación.

Entre los análisis realizados:

- Distribución de churn
- Relación entre **tiempo de permanencia y cancelación**
- Relación entre **cargos mensuales y cancelación**
- Correlación entre variables
- Importancia de variables en los modelos

---

# 🤖 Modelos de Machine Learning

Se entrenaron dos modelos de clasificación para predecir la cancelación:

## 📌 Regresión Logística

Modelo lineal utilizado frecuentemente para problemas de clasificación binaria.

Ventajas:

- Interpretabilidad
- Rapidez de entrenamiento

---

## 🌳 Random Forest

Modelo basado en árboles de decisión que permite capturar relaciones no lineales en los datos.

Ventajas:

- Alta capacidad predictiva
- Manejo robusto de variables

---

# 📊 Evaluación de Modelos

Los modelos fueron evaluados utilizando las siguientes métricas:

- Accuracy
- Precision
- Recall
- F1-score
- Matriz de confusión

### Resultados obtenidos

| Modelo | Accuracy | Precision | Recall | F1-score |
|------|------|------|------|------|
| Regresión Logística | 0.79 | 0.64 | 0.54 | 0.58 |
| Random Forest | 0.78 | 0.60 | 0.47 | 0.52 |

La **Regresión Logística mostró un desempeño ligeramente superior**, especialmente en las métricas de precisión y recall.

---

# 🔎 Variables más importantes

El análisis de importancia de variables mostró que los factores más influyentes en la cancelación son:

- **Charges.Total**
- **tenure (tiempo de permanencia)**
- **Charges.Monthly**
- **InternetService_Fiber optic**
- **PaymentMethod_Electronic check**
- **Tipo de contrato**

Esto sugiere que el **precio del servicio, el tiempo de relación con la empresa y las condiciones del contrato** son factores clave en la decisión de cancelar.

---

# 💡 Insights Estratégicos

A partir del análisis se identificaron oportunidades para mejorar la retención de clientes.

## 1️⃣ Clientes nuevos tienen mayor riesgo de cancelación

Clientes con bajo **tenure** presentan mayor probabilidad de cancelar.

**Estrategia recomendada:**  
Implementar programas de **fidelización durante los primeros meses del cliente**.

---

## 2️⃣ Contratos largos reducen la cancelación

Los clientes con contratos de **1 o 2 años cancelan menos**.

**Estrategia recomendada:**  
Incentivar contratos largos mediante **descuentos o beneficios adicionales**.

---

## 3️⃣ Los cargos del servicio influyen en el churn

Los clientes con mayores cargos mensuales muestran mayor probabilidad de cancelar.

**Estrategia recomendada:**  
Ofrecer **planes personalizados o promociones para clientes con alto gasto mensual**.

---

# ⚙️ Tecnologías Utilizadas

- Python
- Pandas
- Numpy
- Matplotlib
- Seaborn
- Scikit-learn
- Imbalanced-learn

---

# ▶️ Cómo ejecutar el proyecto

1️⃣ Clonar el repositorio

```bash
git clone https://github.com/Ari-aP/TelecomX_parte2_Latam.git
```

2️⃣ Instalar dependencias

```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn
```

3️⃣ Abrir el notebook

```bash
jupyter notebook TelecomX_parte2_Latam.ipynb
```

---

# 📌 Conclusión

Este proyecto demuestra cómo el uso de **análisis de datos y modelos de Machine Learning** puede ayudar a anticipar la cancelación de clientes y apoyar la toma de decisiones estratégicas en empresas de telecomunicaciones.

La identificación temprana de clientes con alto riesgo de cancelación permite diseñar estrategias de retención más efectivas, reduciendo pérdidas y mejorando la experiencia del cliente.

---

# 👩‍💻 Autor

Proyecto desarrollado por Ariadne Arambulo
