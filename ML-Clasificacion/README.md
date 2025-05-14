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
```

**¿Qué es el dataset Iris?**

El *dataset Iris* es un conjunto de datos muy famoso en ciencia de datos. Contiene 150 observaciones de flores de tres especies diferentes:

- Setosa (0)
- Versicolor (1)
- Virginica (2)

Cada flor tiene 4 características numéricas:

- Largo del sépalo
- Ancho del sépalo
- Largo del pétalo
- Ancho del pétalo

👉 `X` contiene estas características (forma: `(150, 4)`), y `y` contiene las especies (forma: `(150,)`).

---

## ✂️ Paso 2: Dividir datos para entrenamiento y prueba

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)
```

Antes de entrenar un modelo, debemos dividir los datos:

- **70%** para *entrenar* al modelo (`X_train`, `y_train`)
- **30%** para *evaluar* su rendimiento (`X_test`, `y_test`)

> Es como estudiar con un grupo de ejercicios (entrenamiento) y luego rendir una prueba con otros distintos (prueba).

---

## 🧠 Paso 3: Crear el modelo de clasificación

```python
from sklearn.neighbors import KNeighborsClassifier

knn = KNeighborsClassifier(n_neighbors=3)
```

Aquí usamos el algoritmo **K-Nearest Neighbors (KNN)**, uno de los más simples y visuales:

- Para predecir una nueva flor, el algoritmo mira sus **3 vecinos más cercanos** (por eso `n_neighbors=3`) en el espacio de características.
- Luego vota: ¿Qué clase tienen esos vecinos? La mayoría gana.

---

## 🏋️‍♂️ Paso 4: Entrenar el modelo

```python
knn.fit(X_train, y_train)
```

El modelo ahora "aprende" observando los datos de entrenamiento: cómo se relacionan las características con las especies.

> En el caso de KNN, realmente no "entrena" en el sentido tradicional. Solo guarda los datos de entrenamiento para compararlos después.

---

## 🔮 Paso 5: Hacer predicciones

```python
y_pred = knn.predict(X_test)
```

Con el modelo listo, ahora intentamos predecir las especies de flores en el conjunto de prueba.

---

## ✅ Paso 6: Evaluar el rendimiento

```python
from sklearn.metrics import accuracy_score

accuracy = accuracy_score(y_test, y_pred)
print(f"Precisión del modelo: {accuracy:.2f}")
```

La **precisión (accuracy)** nos dice qué porcentaje de las predicciones fueron correctas.

> Si el modelo acierta 13 de 15 predicciones, su precisión es de `13/15 ≈ 0.87`.

---

## 🌸 Paso 7 (opcional): Predecir una flor nueva

```python
nueva_flor = [[5.1, 3.5, 1.4, 0.2]]
prediccion = knn.predict(nueva_flor)
print(f"Predicción para nueva flor: {iris.target_names[prediccion[0]]}")
```

Probamos el modelo con una flor ficticia que mide:

- 5.1 cm de sépalo largo
- 3.5 cm de sépalo ancho
- 1.4 cm de pétalo largo
- 0.2 cm de pétalo ancho

El modelo nos dice a qué especie pertenece. Si devuelve `setosa`, ¡es un buen indicio de que aprendió correctamente!

---

## 🎓 Conclusiones

- Usamos un modelo supervisado para resolver un problema de clasificación.
- Vimos cómo dividir los datos, entrenar el modelo, hacer predicciones y evaluar resultados.
- Usamos `KNeighborsClassifier`, pero existen muchos otros algoritmos (como árboles de decisión o redes neuronales).

---

## 🚀 Próximos pasos sugeridos

- Probar con otro valor de `n_neighbors` (por ejemplo, 1 o 5).
- Cambiar el algoritmo a un árbol de decisión o regresión logística.
- Graficar los datos para visualizar cómo se distribuyen las especies.
