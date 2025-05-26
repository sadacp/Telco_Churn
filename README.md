# Telco_Churn
Este proyecto tiene como objetivo **predecir y entender por qué los clientes abandonan una compañía de telecomunicaciones**, utilizando modelos de árboles de decisión y Random Forest. Se trabajó con el dataset público de IBM Telco Customer Churn, disponible en Kaggle.


> 🔗 [Dataset en Kaggle](https://www.kaggle.com/datasets/yeanzc/telco-customer-churn-ibm-dataset)

---

## 🧠 Modelos Utilizados

- Árbol de Decisión (`DecisionTreeClassifier`)
- Bosque Aleatorio (`RandomForestClassifier`)

Se evaluaron ambos modelos con métricas de desempeño y se compararon sus resultados para determinar cuál es más eficiente en este contexto.

---

## 🎯 Objetivos del Análisis

1. Calcular el porcentaje de clientes que abandonaron la compañía.
2. Evaluar si existe desbalanceo en la variable objetivo.
3. Identificar variables demográficas o de contrato que más influyen en el abandono.
4. Analizar la importancia de las variables para cada modelo.
5. Determinar qué modelo tiene mejor desempeño.

---

## 🔧 Pasos realizados

1. **Carga y limpieza de datos**
   - Lectura del dataset CSV.
   - Manejo de valores nulos.
   - Eliminación de columnas irrelevantes (por ejemplo, `customerID`).

2. **Análisis exploratorio**
   - Estadísticas descriptivas para variables numéricas.
   - Frecuencias para variables categóricas.

3. **Preprocesamiento**
   - Codificación de variables categóricas.
   - División del dataset en conjuntos de entrenamiento (70%) y prueba (30%).

4. **Entrenamiento de modelos**
   - Árbol de Decisión con `max_depth=3`.
   - Bosque Aleatorio con `n_estimators=40` y `max_depth=5`.
   - Visualización del árbol y exportación de reglas.
   - Evaluación de ambos modelos usando Accuracy, Recall y F1-Score.

5. **Predicción de nuevos casos**
   - Se realizaron predicciones para tres nuevos usuarios ficticios incluidos en la consigna.

---

## 📁 Estructura del repositorio

Telco_churn/
├── data/ # Datos sin procesar o preprocesados
    └── Telco_customer_churn.xlsx # DataSet para el Proyecto
│ └── Telco23.ipynb # Notebook principal del proyecto
├── README.md # Este archivo
└── .gitignore # Archivos y carpetas ignoradas por git


---

## 📈 Resultados destacados

- - **Porcentaje de churn**: ~26.5%
- **Desbalanceo moderado** en la variable objetivo (`Churn`).
- **Variables más correlacionadas** con el churn:
  - Tipo de contrato (`Contract`)
  - Tenencia del cliente (`tenure`)
  - Método de pago y facturación electrónica
- **Modelo más eficiente**: Random Forest, gracias a su mayor capacidad de generalización y mejores métricas globales.

---

## 💡 Conclusiones

Random Forest se presenta como el modelo más robusto para esta tarea, con un mejor equilibrio entre precisión y sensibilidad. El tipo de contrato y la duración del cliente son determinantes clave en la predicción del abandono.

| Modelo                | Ventajas                                                                                                                          | Desventajas                                                                            | Uso para el  objetivo                                                                                       |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| **Árbol de Decisión** | - Fácil de entender: se puede ver por qué al Cliente 1 lo marcó como churn (prob > 0.75).<br>- Útil para **explicar** decisiones. | - Menos robusto: decisiones como el Cliente 3 pueden ser sensibles a pequeños cambios. | Excelente para explicar **por qué** se clasificó como churn/no churn (ej. Cliente 1).                       |
| **Random Forest**     | - Da resultados **más consistentes** (coincide con el árbol, pero con mayor respaldo estadístico por múltiples árboles).          | - No muestra reglas claras, difícil saber por qué el Cliente 3 no fue claro.           | Ideal si necesitas **precisión en predicciones**, como para campañas de retención o segmentación de riesgo. |


---

## 🛠 Requisitos

- Python 3.8+
- Jupyter Notebook
- pandas, numpy, matplotlib, seaborn
- scikit-learn
