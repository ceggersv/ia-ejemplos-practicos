# 🌱 Introducción a la Clasificación con Scikit-learn

En este cuaderno, vamos a construir nuestro **primer modelo de Machine Learning supervisado** usando Python y la biblioteca `scikit-learn`. Específicamente, resolveremos un problema de **clasificación**, en el que el objetivo es predecir **la categoría a la que pertenece un ejemplo**.

> Imagina que eres un botánico y tienes varias flores. Quieres predecir de qué especie es cada flor basándote en características como el largo y ancho de sus pétalos y sépalos. ¡Eso es clasificación!

---

## 🔍 Paso 1: Cargar un dataset real

```python
from sklearn.datasets import load_iris

iris = load_iris()
X = iris.data      # Características de entrada (features)
y = iris.target    # Etiquetas de salida (clases)
