# Aprendizaje Avanzado (Advanced Machine Learning)

**Autor:** Miguel Ángel Ortiz Roldán  
**Usuario de GitHub:** [miguelortizruao](https://github.com/miguelortizruao)  
**Rama de entrega:** `Miguel-Angel-Ortiz-R`  
**Repositorio Base:** [Nick-profe/Advanced-ML](https://github.com/Nick-profe/Advanced-ML)

---

## 📋 Descripción del Repositorio

Este repositorio contiene el desarrollo completo y riguroso de los talleres de la asignatura **Aprendizaje Avanzado**, implementados con estándares de código limpio, reproducibilidad, arquitecturas modulares de preprocesamiento (`Pipelines` / `ColumnTransformer`) y optimización de hiperparámetros.

### Contenido Principal:

1. **`Taller/` (Taller 1 - Redes Neuronales Perceptrón Multicapa / MLP):**
   - **Notebook:** `M1_Taller_MLP.ipynb`
   - **Punto 1 (Clasificación):** Predicción multiclase con *Dry Bean Dataset*.
   - **Punto 2 (Regresión):** Estimación continua de demanda con *Bike Sharing Dataset (hour.csv)*.
   - Implementación con Keras / TensorFlow, regularización, capas densas y análisis de curvas de aprendizaje.

2. **`Taller_2/` (Taller 2 - Métodos de Ensamble y Optimización):**
   - **Notebook:** `M2_Taller_Ensamble.ipynb`
   - **Punto 1 (Clasificación):** Predicción de suscripción a depósitos bancarios (*Bank Marketing Dataset - UCI*). Comparación de Árbol de Decisión Base vs. Random Forest, AdaBoost y Gradient Boosting con validación cruzada estratificada (5-Fold). Análisis detallado del desbalance de clases, la trampa del *Accuracy* y solución mediante **Ajuste del Umbral de Decisión (Threshold Tuning)** optimizando *F1-Score*.
   - **Punto 2 (Regresión):** Estimación de la resistencia a la compresión del concreto (*Concrete Compressive Strength Dataset - UCI*). Comparativa de ensambles, búsqueda dual de hiperparámetros (**RandomizedSearchCV vs. GridSearchCV**) fundamentada en el **Principio de Parsimonia**, y diagnóstico de regresión ($R^2$, RMSE, MAE y análisis de residuos).

3. **`Data_entrenamiento/`:**
   - Contiene todos los conjuntos de datos originales y procesados para garantizar que cualquier notebook pueda ejecutarse de inicio a fin sin descargas externas.

---

## ⚙️ Entorno de Desarrollo y Dependencias con `uv`

El proyecto está gestionado con **[`uv`](https://github.com/astral-sh/uv)**, el gestor de paquetes y entornos virtuales de Python de ultra alto rendimiento, garantizando compatibilidad determinista mediante `pyproject.toml` y `uv.lock`.

* **Versión de Python:** `>=3.13` (CPython 3.13.15)
* **Librerías principales:**
  - `scikit-learn >= 1.9.1` (Árboles de decisión, Ensambles, GridSearchCV, RandomizedSearchCV, Pipelines, Métricas)
  - `tensorflow >= 2.21.0` (Redes neuronales MLP, Keras)
  - `pandas >= 3.0.5` y `numpy >= 2.5.3` (Manipulación vectorial de datos)
  - `matplotlib >= 3.11.2` y `seaborn >= 0.13.2` (Visualización estadística y diagnósticos)
  - `xlrd >= 2.0.2` y `openpyxl >= 3.1.5` (Lectura de hojas de cálculo)
  - `ipykernel >= 7.3.0` y `jupyter >= 1.1.1` (Ejecución de Jupyter Notebooks)

---

## 🚀 Instrucciones de Instalación y Ejecución Local

### 1. Clonar el repositorio y ubicarse en la rama:
```bash
git clone -b Miguel-Angel-Ortiz-R https://github.com/miguelortizruao/Advanced-ML.git
cd Advanced-ML
```

### 2. Sincronizar el entorno virtual con `uv`:
Si tienes `uv` instalado, simplemente ejecuta:
```bash
uv sync
```
Esto creará el entorno `.venv` e instalará de forma automática y reproducible todas las librerías con las versiones exactas definidas en `uv.lock`.

*(Si aún no tienes `uv`, puedes instalarlo con: `curl -LsSf https://astral.sh/uv/install.sh | sh` o usar `pip install -r requirements.txt`).*

### 3. Ejecutar los Notebooks:
Para abrir y trabajar en Jupyter Lab / Notebook dentro del entorno:
```bash
uv run jupyter lab
```
O directamente con VS Code seleccionando el intérprete en `.venv/bin/python`.

---

## 📂 Estructura del Directorio

```text
├── Data_entrenamiento/
│   ├── Punto_1_Clasificacion/          # Datasets Taller 1 (Dry Bean)
│   ├── Punto_1_Clasificacion_Taller2/   # Datasets Taller 2 (Bank Marketing)
│   ├── Punto_2_Regresion/              # Datasets Taller 1 (Bike Sharing)
│   └── Punto_2_Regresion_Taller2/      # Datasets Taller 2 (Concrete Strength)
├── Taller/
│   ├── M1_Taller_MLP.ipynb             # Notebook Taller 1 (Redes Neuronales MLP)
│   └── Guia_Implementacion_Comandos.md
├── Taller_2/
│   ├── M2_Taller_Ensamble.ipynb        # Notebook Taller 2 (Métodos de Ensamble)
│   └── Clases/                         # Material teórico y lecturas de apoyo
├── pyproject.toml                      # Especificación de dependencias del proyecto
├── uv.lock                             # Bloqueo de versiones reproducible
├── .gitignore                          # Exclusión de entornos, cachés y videos pesados
└── README.md                           # Documentación general del repositorio
```
