<h1>📊 Telecom X - Predicción de Evasión de Clientes (Churn) - Parte 2<h1>
  
<h2>🎯 Propósito del Proyecto<h2>
  
Este proyecto tiene como misión desarrollar modelos de Machine Learning capaces de identificar qué clientes tienen una mayor probabilidad de cancelar sus servicios en la empresa Telecom X. El objetivo es transformar datos históricos en estrategias de retención proactivas, permitiendo a la empresa actuar antes de que el cliente abandone el servicio.

<h2>📂 Estructura del Proyecto<h2>
  
- **datos_tratados.csv:** Dataset limpio y estandarizado (resultado de la Fase ETL).

- **TelecomX_Predictivo.ipynb:** Notebook de Google Colab con el análisis y modelado.

- **README.md:** Documentación del proyecto.

<h2>⚙️ Preparación de los Datos<h2>
  
Para asegurar la eficacia de los modelos, se aplicó un pipeline de ingeniería de datos:

1. Eliminación de Irrelevantes: Se descartó la columna customerID por ser un identificador único sin valor predictivo.

2. Encoding: Transformación de variables categóricas (Contrato, Método de Pago, etc.) mediante One-Hot Encoding.

3. Estandarización: Uso de StandardScaler para normalizar las variables numéricas (tenure, MonthlyCharges), evitando que las diferencias de escala distorsionen los modelos.

4. Balanceo: Se analizó la proporción de Churn (26.5%), priorizando métricas de evaluación que consideran el desbalance de clases.

<h2>📊 Análisis de Correlación e Insights<h2>
  
Antes del modelado, se realizaron análisis estadísticos dirigidos que revelaron:

- Tipo de Contrato: Los clientes con contratos mensuales (Month-to-month) son los más propensos a la evasión.

- Cargos Mensuales: Existe una tendencia donde los clientes con cargos mensuales elevados tienen una mayor tasa de cancelación.

- Antigüedad (Tenure): Los nuevos clientes representan el mayor riesgo de fuga para Telecom X.

<h2>🤖 Modelado y Evaluación<h2>
  
Se entrenaron y compararon dos modelos de clasificación:

1. Regresión Logística: Modelo lineal para entender el impacto directo de cada variable.

2. Random Forest: Modelo de ensamble para capturar relaciones complejas y no lineales.

Resultados Técnicos:

- Recall (Sensibilidad): Se priorizó esta métrica para capturar la mayor cantidad de posibles cancelaciones. La Regresión Logística obtuvo un 55.7% en validación cruzada.

- Accuracy: Ambos modelos mantuvieron una precisión general cercana al 80%.

<h2>🔍 Importancia de las Variables<h2>
  
El modelo identificó los 3 factores críticos que impulsan el Churn en Telecom X:

1. Tenure (Antigüedad): Clientes con menos tiempo en la empresa.

2. Contract_Month-to-month: La flexibilidad del contrato mensual facilita la salida.

3. OnlineSecurity_No: La falta de servicios adicionales de seguridad aumenta la probabilidad de fuga.

<h2>💡 Conclusión y Estrategia de Retención<h2>
  
Basado en los resultados, se proponen las siguientes acciones estratégicas:

- Incentivos de Migración: Ofrecer beneficios exclusivos a clientes con contratos mensuales para que cambien a contratos anuales.

- Programa de Lealtad Temprana: Enfocar las campañas de retención en los clientes que tienen entre 1 y 6 meses de antigüedad.

- Check-up de Servicio: Revisar proactivamente a los clientes con cargos mensuales altos para asegurar que el valor percibido justifique el costo.

<h2>🛠️ Cómo ejecutar el proyecto<h2>
  
1. Clona este repositorio.

2. Asegúrate de tener instalado: **pandas, scikit-learn, seaborn, matplotlib.**

3. Ejecuta el notebook en Google Colab cargando el archivo **datos_tratados.csv.**
