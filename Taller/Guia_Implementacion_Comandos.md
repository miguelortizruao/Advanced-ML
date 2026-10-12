# Guía de Comandos de Implementación - Punto 1

Esta guía documenta los comandos de terminal que se han ejecutado paso a paso para configurar el entorno de trabajo, instalar dependencias con `uv` y versionar el código utilizando `git`. 

## 0. Inicialización del Proyecto (Reproducibilidad)

Para garantizar que cualquier persona que clone este repositorio pueda arrancar el entorno exactamente en la misma versión de Python, el proyecto se inicializó originalmente definiendo la versión de Python:

```bash
uv init --python 3.13
```
*Esto crea el archivo `pyproject.toml` y el archivo oculto `.python-version` fijando la versión a 3.13. Si alguien se descarga el proyecto y ejecuta los comandos siguientes, `uv` descargará y usará automáticamente Python 3.13.*

## 1. Instalación de Dependencias con `uv`

Dado que el directorio raíz de `Aprendizaje Avanzado` ya estaba inicializado con `uv` (existía el archivo `pyproject.toml`), simplemente agregamos las librerías necesarias para el análisis de datos y la creación de la red neuronal.

```bash
uv add jupyter pandas scikit-learn tensorflow matplotlib seaborn
```

*Nota sobre Python y `uv`: ¿No necesitamos instalar Python? ¡No manualmente! Una de las grandes ventajas de `uv` es que gestiona Python por ti. Al crear el proyecto (cuando se generó el archivo `.python-version`), se definió qué versión de Python usar. Cuando ejecutamos `uv add`, `uv` automáticamente descarga esa versión exacta de Python (si no la tenías), crea un entorno virtual aislado (`.venv`) y descarga allí todas las librerías.*
## 2. Inicialización y Estado de Git

Se verificó el estado de Git para asegurarnos de que el proyecto está bajo control de versiones.

```bash
git status
```
*(Al verificar, notamos que ya estabas en la rama `master` de un repositorio git existente en la carpeta superior).*

## 3. Versionamiento del Trabajo Inicial (Git)

## 4. Estructura de Datasets Seleccionados (UCI Machine Learning Repository)

Para cumplir con el nivel de rigor académico del taller y trabajar con volúmenes de datos representativos para Deep Learning, se seleccionaron y descargaron dos datasets oficiales de UCI:

1. **Punto 1 (Clasificación Multiclase):** `Data_entrenamiento/Punto_1_Clasificacion/Dry_Bean_Dataset.csv`
   - 13,611 registros y 16 características biométricas de granos.
   - Objetivo: 7 clases morfológicas de semillas.

2. **Punto 2 (Regresión Continua):** `Data_entrenamiento/Punto_2_Regresion/hour.csv`
   - 17,379 registros con mediciones ambientales y temporales.
   - Objetivo: Demanda horaria de alquiler de bicicletas (`cnt`).

## 5. Notebook Principal

El archivo maestro del taller se encuentra en:
- `Taller/M1_Taller_MLP.ipynb`

Contiene todas las secciones del informe académico (Autores, Introducción, Marco Teórico, Metodología, Resultados y Conclusiones), funciones modulares universales reutilizables, y la experimentación de 3 arquitecturas x 3 optimizadores para ambos puntos.


```bash
# Agregar los nuevos datasets y el notebook actualizado al Stage de git
git add Data_entrenamiento Taller

# Confirmar con mensaje descriptivo
git commit -m "feat: migrar a datasets UCI Dry Bean y Bike Sharing con pipeline universal MLP"
```

---

## 6. Configurar el "Kernel" en Visual Studio Code

Dado que instalamos las librerías en un entorno virtual aislado con `uv`, debemos decirle a VSCode que use ese entorno para ejecutar el Notebook:

1. Abre el archivo `.ipynb` en VSCode.
2. Haz clic en el botón **"Select Kernel"** (o "Seleccionar Kernel") situado en la esquina superior derecha del editor.
3. En el menú desplegable que aparece en el centro, elige **"Python Environments"** (Entornos de Python).
4. Selecciona la opción que hace referencia a la carpeta `.venv` de tu proyecto (suele estar marcada con una estrella ⭐, ej. `Python 3.13.X (.venv)`).

*¡Y listo! Al hacer esto, el cuaderno podrá importar librerías como Pandas y TensorFlow sin arrojar el error "ModuleNotFoundError".*

---

> **Próximos Pasos (Fase 2):**
> Cuando pasemos a la Fase 2 (refactorización a scripts de Python modulares), añadiremos nuevos archivos como `data_preprocessing.py`, `model.py`, etc. Repetiremos el proceso de `git add` y `git commit` para seguir guardando los avances.
