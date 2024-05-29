# Máquinas de Vectores de Soporte (SVM)

En las Máquinas de Vectores de Soporte (SVM), las variables W y b desempeñan papeles cruciales en la definición del hiperplano que separa los puntos de datos pertenecientes a diferentes clases.

## W (Vector de Peso)

### Definición
El vector de peso (W) es un vector de alta dimensión que representa la dirección del hiperplano. Determina la orientación y la pendiente del hiperplano en el espacio de características.

### Interpretación
El vector W apunta hacia el vector normal del hiperplano. Esto significa que es perpendicular al hiperplano e indica la dirección en la que el hiperplano es más sensible a los cambios en los datos de entrada.

### Significado
El vector W es crucial para definir la frontera de decisión, que es la línea o plano que separa los puntos de datos de una clase de los de la otra. Al maximizar el margen entre el hiperplano y los puntos de datos más cercanos (vectores de soporte), las SVM buscan encontrar un hiperplano que sea lo más robusto posible a las variaciones en los datos.

## b (Término de Sesgo - “bias”)

### Definición
El término de sesgo (b) es un valor escalar que representa el desplazamiento del hiperplano desde el origen. Determina la posición del hiperplano en el espacio de características.

### Interpretación
El término b desplaza el hiperplano a lo largo de su vector normal (representado por W). Asegura que el hiperplano no esté restringido a pasar por el origen, lo que le permite adaptarse mejor a la distribución de los datos.

### Significado
El término b es esencial para ajustar la posición del hiperplano, especialmente cuando se trata de datos no separables linealmente. Al ajustar b, el hiperplano puede moverse para acomodar puntos de datos que pueden estar ligeramente fuera del margen óptimo.

## Ecuación del Hiperplano

Juntos, W y b definen la ecuación del hiperplano en el espacio de características:

\[ w<sup>T</sup> * x + b = 0 \]

donde:
- \( w<sup>T</sup> \) es la transpuesta del vector de peso W
- \( x \) es el punto de datos de entrada
- \( b \) es el término de sesgo

Esta ecuación representa la frontera de decisión, clasificando los puntos de datos como pertenecientes a una clase si la expresión es positiva, y a la otra clase si la expresión es negativa.

## Resumen

W y b son parámetros fundamentales en las SVM, determinando la orientación, la posición y la frontera de decisión del hiperplano que separa los puntos de datos. Su interacción permite a las SVM clasificar eficazmente los datos en espacios de alta dimensión.
