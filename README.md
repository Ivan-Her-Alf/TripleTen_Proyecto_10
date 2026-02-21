# 📊 Megaline | Modelo de Recomendación de Planes (Enfoque BI)

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-yellow)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange)
![RandomForest](https://img.shields.io/badge/Model-Random%20Forest-green)
![Accuracy](https://img.shields.io/badge/Accuracy-0.79%20Test-success)
![Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen)

---

## 📌 Descripción del Proyecto

La compañía de telecomunicaciones **Megaline** busca migrar a sus clientes desde planes heredados hacia sus nuevos planes:

- **Smart (0)**
- **Ultra (1)**

El objetivo del proyecto es desarrollar un modelo de clasificación que analice el comportamiento mensual de los usuarios y recomiende automáticamente el plan más adecuado.

Desde una perspectiva de **Business Intelligence**, este modelo permite:

- Optimizar estrategias de migración de clientes  
- Incrementar la rentabilidad por usuario  
- Apoyar decisiones comerciales basadas en datos  
- Reducir fricción en procesos de actualización de planes  

El umbral mínimo requerido de exactitud es **0.75**.

---

## 📊 Descripción del Dataset

Cada registro representa el comportamiento mensual de un cliente.

| Variable     | Descripción |
|--------------|------------|
| `calls`      | Número de llamadas |
| `minutes`    | Duración total de llamadas (minutos) |
| `messages`   | Número de mensajes enviados |
| `mb_used`    | Consumo de datos en MB |
| `is_ultra`   | Plan actual (Ultra = 1, Smart = 0) |

### 📈 Resumen del Dataset

- Registros: **3214**
- Columnas: **5**
- Valores nulos: **0**
- Duplicados: **0**

Dataset limpio y listo para modelado.

---

## 🔍 Análisis Exploratorio (EDA)

### Distribución del Target

Smart (0): 69.35%
Ultra (1): 30.65%

Existe un ligero desbalance, pero no crítico para clasificación.

### Estadísticas Relevantes

- Promedio de llamadas: 63
- Promedio de minutos: 438
- Promedio de mensajes: 38
- Promedio de consumo de datos: 17,207 MB
- Proporción Ultra: 30.6%

---

## 🧪 Prueba de Cordura (Sanity Check)

### Baseline

Se creó un modelo base que predice siempre la clase mayoritaria.

Accuracy Baseline: 0.6924

Cualquier modelo debe superar este valor para demostrar aprendizaje real.

---

## 🤖 Modelos Implementados

División del dataset:

- 60% Entrenamiento  
- 20% Validación  
- 20% Prueba  

Se realizó optimización manual de hiperparámetros mediante ciclos `for`.

---

### 1️⃣ Regresión Logística

Mejor configuración encontrada:

LogisticRegression(C=0.01, max_iter=1000, random_state=12345)

---

### 2️⃣ Árbol de Decisión

Mejor configuración encontrada:

DecisionTreeClassifier(max_depth=3, random_state=12345)

---

### 3️⃣ 🌳 Random Forest (Modelo Ganador)

Mejor configuración encontrada:

RandomForestClassifier(max_depth=8, n_estimators=40, random_state=12345)

---

## 🏆 Comparativa Final

| Modelo | Accuracy Validación |
|--------|--------------------|
| Regresión Logística | Inferior |
| Árbol de Decisión | Inferior |
| **Random Forest** | **0.8087** |

### 📌 Modelo Seleccionado: Random Forest

Accuracy Validación: 0.8087
Accuracy Test: 0.7963

El modelo supera ampliamente el baseline y el umbral requerido de 0.75.

---

## ✅ Resultado del Sanity Check
Baseline Accuracy: 0.6924
Accuracy Test Modelo: 0.7963
Modelo supera baseline: True

El modelo demuestra capacidad predictiva real y buena generalización.

---

## 📊 Impacto desde Business Intelligence

Este modelo puede integrarse en:

- Sistemas de recomendación automatizada
- Dashboards de segmentación de clientes
- Estrategias de upselling
- Modelos de scoring comercial
- Automatización de campañas dirigidas

Permite transformar datos operativos en decisiones estratégicas.

---

## 🛠 Stack Tecnológico

- Python
- Pandas
- Scikit-Learn
- Regresión Logística
- Árbol de Decisión
- Random Forest
- Optimización manual de hiperparámetros
- Evaluación con Accuracy

---

## 🚀 Mejoras Futuras

- Implementar GridSearchCV
- Incorporar validación cruzada
- Analizar matriz de confusión
- Evaluar precisión, recall y F1-score
- Visualizar importancia de variables
- Implementar pipeline productivo

---