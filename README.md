# SVM (Support Vector Machines)

## Descripción
Support Vector Machines (Máquinas de Vectores de Soporte) es un algoritmo de aprendizaje supervisado utilizado para problemas de regresión y reconocimiento de patrones. Principalmente, se utiliza para tareas de clasificación.

## Funcionamiento
SVM busca encontrar el hiperplano óptimo que mejor separa las clases en un espacio multidimensional. Este hiperplano se elige de manera que maximiza el margen entre las clases, es decir, la distancia entre el hiperplano y los puntos de datos más cercanos de cada clase.

## Ventajas
- Efectivo en espacios de alta dimensión.
- Es eficiente en la memoria, ya que utiliza un subconjunto de puntos de entrenamiento en la función de decisión (vectores de soporte).
- Es versátil, ya que diferentes funciones del núcleo pueden ser especificadas para la función de decisión. Esto permite la adaptabilidad a diferentes tipos de datos.

## Limitaciones
- No es adecuado para conjuntos de datos muy grandes, ya que el tiempo de entrenamiento puede ser considerable.
- Sensible a la elección de la función del núcleo y a los parámetros de regularización.
- No proporciona directamente probabilidades de clasificación, aunque estas pueden ser estimadas a través de métodos de post-procesamiento.

## Uso
SVM es ampliamente utilizado en una variedad de aplicaciones, incluyendo:
- Clasificación de texto y análisis de sentimientos.
- Reconocimiento de imágenes.
- Detección de anomalías.
- Bioinformática.
- Predicción financiera, entre otros.

## Ejemplo
```python
from sklearn import svm
X = [[0, 0], [1, 1]]
y = [0, 1]
clf = svm.SVC()
clf.fit(X, y)
