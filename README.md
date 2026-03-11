📊 Telecom X - Predicción de Churn (Parte 2)

🎯 Propósito del Proyecto

El objetivo principal de este análisis es construir y validar un modelo de Machine Learning capaz de predecir la evasión de clientes (Churn). Al identificar patrones en el comportamiento de los usuarios de Telecom X, la empresa puede implementar estrategias de retención proactivas, enfocándose en los perfiles con mayor riesgo de abandono.

📂 Estructura del Proyecto

notebooks/: Cuaderno principal con el flujo de análisis y modelado.

data/: Archivo datos_tratados.csv (salida de la Parte 1).

visualizations/: Gráficos de correlación, importancia de variables y matrices de confusión.

models/: Modelos serializados en formato .pkl (Pickle).

⚙️ Preparación de Datos y Modelado

En esta fase, se transformaron los datos crudos en información procesable para los algoritmos:

1. Clasificación de Variables
Numéricas: Tenure (antigüedad), MonthlyCharges, TotalCharges.

Categóricas: Gender, InternetService, ContractType, PaymentMethod.

2. Ingeniería de Características
Codificación: Se utilizó OneHotEncoder para transformar variables categóricas, asegurando que el modelo interprete correctamente las etiquetas sin jerarquías arbitrarias.

Normalización: Aplicación de StandardScaler para equilibrar el impacto de variables con diferentes magnitudes (ej. Cargos vs. Meses de antigüedad).

3. Estrategia de Validación
Split: División de datos en Entrenamiento (80%) y Prueba (20%) con el parámetro stratify=y para manejar el desbalance de clases.

Validación Cruzada: Uso de K-Fold para obtener métricas estables y evitar el sobreajuste.

📈 Insights y Visualización (EDA)

Durante el análisis exploratorio dirigido, se identificaron factores clave:

Correlación: Los clientes con contratos "Mes a mes" presentan una correlación significativamente alta con el Churn.

Importancia: Los cargos mensuales y el tipo de soporte técnico son predictores críticos en el modelo.

🛠️ Instrucciones de Ejecución

Para replicar este análisis, sigue estos pasos:

Requisitos: Tener instalado Python 3.8+ y las siguientes bibliotecas:

Bash
pip install pandas numpy scikit-learn matplotlib seaborn yellowbrick
Carga de Datos: Asegúrate de que el archivo datos_tratados.csv esté en la carpeta /data.

Ejecución: Abre el notebook churn_prediction.ipynb en Google Colab o Jupyter Notebook y ejecuta todas las celdas.
