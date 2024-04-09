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

## Ejemplo (C++)
Aquí hay un ejemplo básico de cómo usar SVM en C++ utilizando la biblioteca de aprendizaje automático de código abierto, LIBSVM:

```cpp
#include <iostream>
#include "svm.h"

int main() {
    // Datos de entrenamiento
    svm_problem prob;
    prob.l = 3;
    prob.y = new double[prob.l] {1, -1, 1};
    prob.x = new svm_node*[prob.l];
    prob.x[0] = new svm_node[3] { {1, 1}, {2, 1}, {-1, 1} };
    prob.x[1] = new svm_node[3] { {1, 1}, {2, -1}, {-1, 1} };
    prob.x[2] = new svm_node[3] { {1, -1}, {2, 1}, {-1, 1} };

    // Configuración del modelo SVM
    svm_parameter param;
    param.svm_type = C_SVC;
    param.kernel_type = RBF;
    param.gamma = 0.5;
    param.C = 1;

    // Entrenamiento del modelo
    svm_model* model = svm_train(&prob, &param);

    // Predicción
    svm_node x[3] { {1, 1}, {2, 1}, {-1, 1} };
    double pred_label = svm_predict(model, x);

    std::cout << "Etiqueta predicha: " << pred_label << std::endl;

    // Limpieza
    svm_free_and_destroy_model(&model);
    delete[] prob.y;
    delete[] prob.x[0];
    delete[] prob.x[1];
    delete[] prob.x[2];
    delete[] prob.x;

    return 0;
}
```

## Ejemplo (Python)
```python
from sklearn import svm
from sklearn import svm

# Datos de entrenamiento
X = [[0, 0], [1, 1]]
y = [0, 1]

# Configuración del modelo SVM
clf = svm.SVC()

# Entrenamiento del modelo
clf.fit(X, y)

# Predicción
print("Etiqueta predicha:", clf.predict([[2., 2.]]))
```

##BITACORA
(9/04/2024) Inicia la página del ejemplo. 
            ESTADO: en desarrollo.
