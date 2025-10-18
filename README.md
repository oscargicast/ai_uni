# Regresión Lineal Múltiple para Predicción de Precios de Viviendas en Boston

Proyecto de ciencia de datos que aplica análisis de regresión lineal múltiple para predecir precios de viviendas en Boston usando Python, scikit-learn, statsmodels y Plotly.

## Inicio Rápido

```bash
# Instalar dependencias
uv sync

# Iniciar Jupyter
jupyter lab
```

Abrir `notebooks/boston_housing_regression.ipynb` y ejecutar las celdas secuencialmente.

## Características

- **EDA Completo**: Análisis de correlación, distribuciones y visualizaciones
- **Múltiples Modelos**: Construcción progresiva con diferentes combinaciones de características (1, 2, 5, 13, 7 características)
- **Selección de Características**: RFE (Recursive Feature Elimination) automática
- **Análisis Estadístico**: Pruebas de hipótesis, p-valores y diagnósticos con statsmodels
- **Evaluación Integral**: Métricas completas (R² Train/Test, R² Ajustado, RMSE, MAE, detección de overfitting)
- **Visualizaciones Interactivas**: Tablas y dashboard de 6 paneles con Plotly
- **Prevención de Data Leakage**: División train-test antes del entrenamiento
- **Análisis de Residuos**: Validación mediante gráficos de residuos y Q-Q

## Requisitos

- Python 3.12+
- [uv](https://github.com/astral-sh/uv) (gestor de paquetes)
- Dataset Boston Housing en `data/housing.csv`

## Dataset: Boston Housing

El dataset contiene 506 observaciones con 13 características predictoras y 1 variable objetivo (MEDV - precio medio de vivienda en $1000s).

**Características principales:**
- **CRIM**: Tasa de criminalidad per cápita
- **RM**: Número promedio de habitaciones
- **LSTAT**: % población de estatus bajo
- **PTRATIO**: Relación alumno-maestro
- **NOX**: Concentración de óxidos nítricos
- Y 8 características más

**Nota**: El archivo CSV no tiene encabezados. El notebook asigna automáticamente los nombres de columnas correctos.

## Pipeline de Análisis

1. **Importar Librerías** - Incluyendo Plotly para visualizaciones interactivas
2. **Cargar Dataset** - Desde `data/housing.csv`
3. **EDA** - Mapas de calor, distribuciones, pairplots
4. **Preprocesamiento & Train-Test Split** - División 80/20
5. **Regresión Lineal Simple** - Análisis con una característica (RM)
6. **Regresión Lineal Múltiple** - Modelos progresivos (2, 5, 13 características)
7. **Selección de Características** - RFE selecciona 7 mejores características
8. **Entrenamiento** - Todos los modelos usan solo datos de entrenamiento
9. **Análisis de Residuos** - Gráficos de residuos y Q-Q
10. **Predicciones vs Reales** - Visualización de rendimiento
11. **Comparación de Modelos** - Tabla interactiva Plotly con todas las métricas
12. **Dashboard Interactivo** - 6 paneles de visualización
13. **Conclusiones** - Hallazgos e insights

## Métricas de Evaluación

Todas las métricas se muestran en una **tabla interactiva Plotly**:

- **R² Train/Test**: Rendimiento en conjuntos de entrenamiento y prueba
- **R² Ajustado**: R² ajustado por número de predictores
- **Estadístico F**: Significancia estadística del modelo
- **p-valor**: Significancia (< 0.05 indica significancia)
- **RMSE Test**: Error cuadrático medio en datos de prueba
- **MAE Test**: Error absoluto medio en datos de prueba
- **Overfitting**: Diferencia entre R² Train y Test (< 0.05 es bueno)
- **Error %**: Error porcentual relativo al precio medio

## Estructura del Proyecto

```
.
├── notebooks/
│   └── boston_housing_regression.ipynb  # Notebook principal de análisis
├── data/
│   └── housing.csv                      # Dataset Boston Housing
├── pyproject.toml                        # Dependencias y configuración
└── README.md                             # Este archivo
```
