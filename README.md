# Momentum Integral Trading

Este repositorio contiene el material experimental y los notebooks que respaldan el paper académico:

**“Modelado Dinámico del Precio como Función Continua:  
Una Estrategia Basada en Derivadas para Capturar Dirección y Momentum en Criptoactivos”**

El proyecto explora una interpretación del movimiento del precio inspirada en conceptos físicos, modelando el precio de criptoactivos como un proceso continuo en el tiempo y utilizando aproximaciones discretas de sus derivadas para generar señales de trading.

---

## 📌 Descripción general

Los indicadores técnicos tradicionales suelen basarse en transformaciones retardadas del precio, lo que puede limitar su capacidad para detectar cambios tempranos en la dinámica del mercado, especialmente en marcos temporales de alta frecuencia.  
Este trabajo propone un modelo de trading determinístico, basado en reglas explícitas, que utiliza derivadas discretas suavizadas de primer y segundo orden para capturar dirección y momentum de forma más dinámica e interpretable.

El repositorio documenta el proceso completo de investigación, desde análisis exploratorios iniciales hasta el modelo final evaluado y reportado en el paper.

---

## 📁 Estructura del repositorio

momentum-integral-trading/
│
├── notebooks/
│ ├── paper_support/
│ │ ├── 04_momentum_optimization.ipynb
│ │ ├── 05_momentum_speed_integral_final.ipynb
│ │ └── README.md
│ │
│ └── exploratory/
│ ├── 01_trading_signals_local.ipynb
│ ├── 02_take_profit_tester.ipynb
│ ├── 03_momentum_model_dataset.ipynb
│ └── README.md
│
├── html/
│ ├── 04_momentum_optimization.html
│ └── 05_momentum_speed_integral_final.html
│
├── figures/
│ └── btc_signals.png
│
├── requirements.txt
│
└── LICENSE


---

## 📓 Descripción de los notebooks

### 🔹 Notebooks de soporte del paper

Los notebooks ubicados en `notebooks/paper_support/` corresponden **directamente** a la metodología, resultados y comparaciones presentadas en el paper.

- **04_momentum_optimization.html**
Desarrollo y calibración del modelo de momentum basado en derivadas discretas suavizadas, incluyendo la optimización de parámetros por activo.

- **05_momentum_speed_integral_final.html**
Evaluación final del modelo, análisis de desempeño, visualización de señales y comparación con el indicador técnico MACD.

- **06_refinamiento_modelo_trading.html Análisis detallado del comportamiento intra-operación del modelo base, con el objetivo de caracterizar regímenes frágiles y robustos a nivel de trade. Este notebook introduce las reglas híbridas de deterioro temprano utilizadas como teacher para la construcción del dataset supervisado.

- **07_modelos_ml_con_regimenes.html** Construcción del dataset de aprendizaje supervisado a partir de características tempranas de cada operación. Entrenamiento y evaluación de múltiples modelos de clasificación (árboles, ensambles, SVM, KNN, LDA, QDA) para la detección temprana de regímenes frágiles, incluyendo validación cruzada estratificada y análisis de desempeño.

- **08_competicion_modelo_estatico_vs_ml.html** Comparación final entre el modelo de momentum físico puro, el modelo combinado con reglas estáticas de régimen y el modelo combinado con un clasificador supervisado de regímenes. Incluye tanto la evaluación cruzada como un análisis exploratorio fuera de muestra (forward), utilizado únicamente como evidencia complementaria.

Estos notebooks constituyen la referencia principal para la reproducibilidad de los resultados reportados en el paper.

---

### 🔹 Notebooks exploratorios

Los notebooks ubicados en `notebooks/exploratory/` documentan **etapas tempranas y exploratorias** del proceso de investigación.  
Incluyen enfoques alternativos que fueron evaluados, pero que no fueron adoptados en el modelo final.

- **01_trading_signals_local.ipynb**  
  Exploración de indicadores técnicos tradicionales, zonas de absorción y análisis del order book.

- **02_take_profit_tester.ipynb**  
  Evaluación de distintos esquemas de take-profit y stop-loss basados en ratios riesgo–beneficio, ATR, momentum y estructura de mercado.

- **03_momentum_model_dataset.ipynb**  
  Construcción de datasets para clasificación supervisada (BUY / HOLD / SELL) y experimentación con diversos modelos de aprendizaje automático.

Estos notebooks se incluyen con fines de transparencia y documentación del proceso, pero **no son necesarios** para reproducir los resultados finales del paper.

---

## 📊 Datos

Todos los experimentos utilizan datos públicos de velas OHLCV obtenidos a través de la API de Binance, basados en velas de cinco minutos para pares de criptoactivos líquidos (BTCUSDT, ETHUSDT, ADAUSDT, XRPUSDT, BNBUSDT).

No se utiliza información propietaria.

---

## ♻️ Reproducibilidad

Para reproducir los principales resultados del paper, es suficiente enfocarse en los notebooks ubicados en:

notebooks/paper_support/


Las versiones exportadas en HTML de estos notebooks se encuentran disponibles en el directorio `html/`, permitiendo su consulta sin necesidad de ejecutar el código.

---

## 📎 Material suplementario

Este repositorio se referencia como material suplementario en el paper y tiene como objetivo apoyar la transparencia, reproducibilidad y posibles extensiones futuras del enfoque propuesto.


