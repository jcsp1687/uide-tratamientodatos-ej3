Predicción de Mortalidad y Monitoreo Crítico en UCI mediante Machine Learning

Este proyecto desarrolla un sistema analítico para predecir el riesgo de mortalidad en Unidades de Cuidados Intensivos (UCI), utilizando un dataset de monitoreo de 15,000 registros sintéticos diseñados para simular entornos clínicos reales. El análisis se centra en identificar los indicadores biológicos y operativos que determinan la supervivencia del paciente.

Propósito del Proyecto:

El objetivo principal es proporcionar una herramienta de soporte a la decisión clínica que permita:

- Identificar tempranamente a pacientes en riesgo inminente de deterioro.
- Priorizar recursos hospitalarios en entornos de alta demanda (como los hospitales en Quito).
- Descubrir patrones de género en la manifestación de signos vitales críticos.

Requisitos del Entorno

- Lenguaje: Python 3.10+

- Librerías principales:

    * pandas y numpy: Procesamiento y limpieza de datos (ETL).

    * matplotlib y seaborn: Visualización avanzada.

    * scikit-learn: Implementación del modelo de Random Forest.

Desarrollo

1. Procesamiento de Datos (ETL)

El dataset fue analizado con detenimiento y sometido a un proceso de limpieza y transformación:

- Traducción Técnica: Se renombraron los indicadores clínicos del inglés al español para facilitar la interpretación médica (ej. apache_score a Puntaje_APACHE_II).

- Ingeniería de Características: Se aplicó LabelEncoder para la variable Género y One-Hot Encoding para los tipos de admisión (Emergencia, Urgente, Electiva).

- Escalado: Se utilizó StandardScaler para normalizar variables con rangos dispares como la Glucosa y la Escala de Glasgow.

2. Análisis Exploratorio (EDA)

Se realizaron visualizaciones para entender la distribución del riesgo:

- Distribución de Edad: Identificación de la correlación entre el envejecimiento y la reducción de la reserva funcional.

- Mapa de Calor: Análisis de colinealidad entre signos vitales y la etiqueta de mortalidad.

3. Implementación de Machine Learning

Se utilizó un modelo de Random Forest Classifier de la librería scikit-learn. Este algoritmo fue elegido por su capacidad para manejar relaciones no lineales y su resistencia al sobreajuste (overfitting).

Principales Hallazgos e Insights (Calidad Técnica)

Basado en el análisis de importancia de características (Feature Importance), los indicadores más críticos para predecir la mortalidad son:

- Puntaje de Comorbilidad: Es el predictor más fuerte, lo que indica que el historial médico previo es determinante en la recuperación del paciente crítico.

- Puntaje APACHE II y SOFA: La alta relevancia de estos scores valida la calidad del dataset, ya que coinciden con los estándares internacionales de medicina intensiva.

- Gasto Urinario Total: Identificado como una variable de alto peso, reflejando la importancia de la perfusión renal en el pronóstico.

Adicional a los resultados de los indicadores se realiza un análisis por género:

- Análisis de Género: El modelo revela diferencias en la estabilidad de la Presión Sistólica Media y la Temperatura Media entre hombres y mujeres, sugiriendo la necesidad de umbrales de alerta diferenciados.

4. Conclusiones

- Relevancia: El uso de un dataset externo con variables de alta fidelidad clínica permite generar conocimiento valioso sobre la gestión de pacientes críticos.

- Impacto: Los resultados sugieren que el monitoreo automatizado de scores de severidad (APACHE/SOFA) puede reducir la carga cognitiva del personal médico.

- Género: A pesar de existir diferencias en los indicadores, las predicciones de mortalidad son casi las mismas para ambos géneros, lo cual nos indica que los pacientes en UCIs independientemente del género su mortalidad se relaciona con los mismos síntomas. 