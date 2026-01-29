
# Notebooks de soporte del paper

Esta carpeta contiene los notebooks que respaldan directamente la metodología, los resultados y las comparaciones reportadas en el paper:

“Modelado Dinámico del Precio como Función Continua:  
Una Estrategia Basada en Derivadas para Capturar Dirección y Momentum en Criptoactivos”.

Los análisis incluidos en estos notebooks corresponden al modelo final basado en momentum físico multiderivado y constituyen la referencia principal para la reproducibilidad de los resultados presentados en el documento.

## Contenido

- **04_momentum_optimization.html**  
  Desarrollo y calibración del modelo de momentum basado en derivadas discretas suavizadas, incluyendo la optimización de parámetros por activo.

- **05_momentum_speed_integral_final.html**  
  Evaluación final del modelo, análisis de desempeño, visualización de señales y comparación con el indicador técnico MACD.

- **06_refinamiento_modelo_trading.html**
Análisis detallado del comportamiento intra-operación del modelo base, con el objetivo de caracterizar regímenes frágiles y robustos a nivel de trade. Este notebook introduce las reglas híbridas de deterioro temprano utilizadas como teacher para la construcción del dataset supervisado.

- **07_modelos_ml_con_regimenes.html**
Construcción del dataset de aprendizaje supervisado a partir de características tempranas de cada operación. Entrenamiento y evaluación de múltiples modelos de clasificación (árboles, ensambles, SVM, KNN, LDA, QDA) para la detección temprana de regímenes frágiles, incluyendo validación cruzada estratificada y análisis de desempeño.

- **08_competicion_modelo_estatico_vs_ml.html**
Comparación final entre el modelo de momentum físico puro, el modelo combinado con reglas estáticas de régimen y el modelo combinado con un clasificador supervisado de regímenes. Incluye tanto la evaluación cruzada como un análisis exploratorio fuera de muestra (forward), utilizado únicamente como evidencia complementaria.

Para la lectura rápida de los resultados, se recomienda consultar las versiones exportadas en HTML disponibles en el directorio `html/`.

### 🧠 Artefactos entrenados

**regime_model_decision_tree.pkl**

Modelo final de clasificación de regímenes dinámicos entrenado con la totalidad del dataset histórico
utilizado en el paper. El artefacto contiene:

- el clasificador basado en árboles de decisión,
- la lista exacta de variables de entrada,
- metadatos de entrenamiento (fecha, métrica CV).

Este modelo se utiliza para:
- el análisis de interpretabilidad presentado en el paper,
- la evaluación exploratoria fuera de muestra (forward).

El modelo no predice precios ni retornos, sino que clasifica operaciones como regímenes
frágiles o no frágiles a partir de características tempranas del trade.


