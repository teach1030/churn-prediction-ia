# Churn Prediction – Machine Learning Project
## Descripción

Este proyecto tiene como objetivo predecir la probabilidad de que un cliente abandone el servicio (churn) utilizando técnicas de Machine Learning.

Se construyó un pipeline completo que incluye:

-Limpieza y preprocesamiento de datos
-División en entrenamiento y prueba
-Entrenamiento de modelos
-Evaluación con métricas avanzadas
-Optimización de hiperparámetros
-Ajuste del threshold basado en negocio

## Dataset

Dataset de clientes de telecomunicaciones que incluye:

-Tipo de contrato
-Tiempo de permanencia (tenure)
-Cargos mensuales
-Servicios contratados
-Variable objetivo: Churn

Se detectó que:
Los clientes que abandonan el servicio tienden a tener cargos mensuales más altos en promedio.

## Pipeline

Se implementó un Pipeline de Scikit-Learn para integrar:

-Transformaciones numéricas y categóricas
-One-Hot Encoding
-Escalado
-Modelo de clasificación

Esto garantiza:

-Reproducibilidad
-Prevención de data leakage
-Flujo profesional de ML

## Modelo Base – Regresión Logística

Se entrenó inicialmente una Regresión Logística como modelo base.

Resultados iniciales:

-Accuracy ≈ 0.86
-Recall (Churn) ≈ 0.68
-F1-score (Churn) ≈ 0.72

## Comparación con Random Forest

Se probó un modelo más complejo (Random Forest).

Resultado:

-No mejoró el recall
-No superó al modelo base

Conclusión:

En este dataset, la Regresión Logística ofrece mejor equilibrio entre desempeño y simplicidad.

## Ajuste del Threshold

En problemas de churn, el recall es más importante que la accuracy.

Se evaluaron distintos thresholds:

Threshold	  Recall (Churn)	 Precision (Churn)
0.5	        0.68	           0.76
0.4	        0.76	           0.71
0.3	        0.84	           0.65

Se seleccionó 0.4 como punto de equilibrio entre detección y falsos positivos.

## Optimización con GridSearch

Se aplicó GridSearchCV optimizando el parámetro C de la Regresión Logística:

Mejor parámetro:

-C = 100

Modelo optimizado + threshold 0.4:

-Recall (Churn) = 0.78
-Accuracy ≈ 0.86

## Curva ROC y AUC

Se evaluó el modelo con la curva ROC.

Resultado:

-AUC = 0.926

Interpretación:

El modelo tiene excelente capacidad de separar clientes que abandonan vs los que no.

## Conclusión

Se construyó un pipeline completo de Machine Learning para predicción de churn, aplicando buenas prácticas profesionales:

-Evaluación con múltiples métricas
-Optimización de hiperparámetros
-Ajuste estratégico del threshold
-Validación con ROC y AUC

El modelo final logra excelente capacidad de discriminación (AUC 0.92) y mejora la detección de clientes en riesgo.


### Autor Juan Esteban Guerrero Vera
### Proyecto realizado como práctica de Machine Learning aplicado a negocio.