# Guía de Comandos de Implementación - Punto 1

Esta guía documenta los comandos de terminal que se han ejecutado paso a paso para configurar el entorno de trabajo, instalar dependencias con `uv` y versionar el código utilizando `git`. 

## 1. Instalación de Dependencias con `uv`

Dado que el directorio raíz de `Aprendizaje Avanzado` ya estaba inicializado con `uv` (existía el archivo `pyproject.toml`), simplemente agregamos las librerías necesarias para el análisis de datos y la creación de la red neuronal.

```bash
uv add jupyter pandas scikit-learn tensorflow matplotlib seaborn
```

*Nota: Este comando descarga e instala todas estas librerías en el entorno virtual de Python gestionado por `uv`, de manera sumamente rápida, y actualiza el archivo `pyproject.toml`.*

## 2. Inicialización y Estado de Git

Se verificó el estado de Git para asegurarnos de que el proyecto está bajo control de versiones.

```bash
git status
```
*(Al verificar, notamos que ya estabas en la rama `master` de un repositorio git existente en la carpeta superior).*

## 3. Versionamiento del Trabajo Inicial (Git)

Una vez que se generó el Jupyter Notebook (`Exploracion_Parkinson.ipynb`) y se colocó junto con los datos (`parkinsons.data`), se añadieron todos estos nuevos archivos a Git y se hizo el primer "commit".

```bash
# Se agregan todos los archivos de la carpeta Punto_1 al "Stage" de git
git add "Data_entrenamiento/Punto_1"

# Se confirma el cambio con un mensaje descriptivo siguiendo el formato de commits convencionales (feat)
git commit -m "feat: agregar dataset de parkinson y notebook inicial de exploración"
```

---

> **Próximos Pasos (Fase 2):**
> Cuando pasemos a la Fase 2 (refactorización a scripts de Python modulares), añadiremos nuevos archivos como `data_preprocessing.py`, `model.py`, etc. Repetiremos el proceso de `git add` y `git commit` para seguir guardando los avances.
