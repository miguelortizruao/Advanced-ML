# 🧠 Guía Avanzada: Redes Neuronales Artificiales (Enfoque MATLAB y UV-SRNA)

> ¡Tienes toda la razón! Al darme libertad me enfoqué en el estado del arte actual (PyTorch, AdamW, etc.) y pasé por alto la joya que tenías en tus materiales: el libro **"Una aproximación práctica a las redes neuronales artificiales"** (Caicedo y López, Universidad del Valle). 
> Esta nueva versión está construida **estrictamente sobre tu libro base**, pero expandida al 1000% para que entiendas a fondo la matemática y la implementación en **MATLAB** y **UV-SRNA** que te van a evaluar.

---

## 1. De la Biología a la Matemática (Capítulo 1)

El libro establece una analogía directa entre el cerebro (un procesador paralelo masivamente distribuido) y la Red Neuronal Artificial (RNA).

La neurona artificial se define matemáticamente en dos pasos:
1. **Entrada Neta (Neta):** La suma ponderada de las entradas $x_i$ multiplicadas por sus pesos sinápticos $w_{ji}$, más un sesgo o umbral $\theta_j$.
   $$Neta_j = \sum_{i=1}^{N} x_i w_{ji} + \theta_j$$
2. **Función de Activación:** Decide el nivel de salida de la neurona. El libro resalta funciones escalón binario/bipolar para redes simples, y sigmoidales/lineales para redes multicapa.

### El Aprendizaje
El conocimiento de la red reside en los **pesos sinápticos**. Aprender significa modificar la matriz de pesos $W$ iterativamente usando un algoritmo. El libro destaca dos enfoques:
- **Supervisado:** Hay un "maestro" y conocemos la salida deseada $d_p$. Calculamos el error $e_p = d_p - y_p$.
- **No-Supervisado:** La red descubre patrones por sí sola (ej. Mapas de Kohonen).

---

## 2. Redes de Primera Generación: Perceptrón y ADALINE (Capítulo 2)

### El Perceptrón de Rosenblatt
Es una red de capa única (solo capa de entrada y capa de salida). 
- **La gran limitación (Minsky y Papert):** Solo puede resolver problemas **linealmente separables**. Por ejemplo, resuelve perfectamente la compuerta AND, pero fracasa catastróficamente con la compuerta **XOR** (exclusiva), porque no puedes separar los puntos de la XOR con una sola línea recta.
- **Implementación en MATLAB:**
  ```matlab
  % Definimos entradas (X) y salidas deseadas (D) para la compuerta AND
  X = [0 0 1 1; 0 1 0 1];
  D = [0 0 0 1];
  % Creamos la red perceptrón
  red = newp([0 1; 0 1], 1); 
  % Entrenamos
  red = train(red, X, D);
  ```

### Red ADALINE (Adaptive Linear Element)
Desarrollada por Widrow y Hoff. A diferencia del Perceptrón, su función de activación es **lineal**. 
Su algoritmo de aprendizaje se basa en el **Gradiente Descendente** aplicado a los mínimos cuadrados (LMS - Least Mean Square). Es excelente para **Filtros Adaptativos** (ej. limpiar ruido de señales biomédicas como un ECG).

---

## 3. Perceptrón Multicapa (MLP) y Backpropagation (Capítulo 3)

Para vencer el problema del XOR, se añadieron **capas ocultas**. Pero surgió un problema: ¿Cómo calculamos el error en las neuronas ocultas si no sabemos cuál debería ser su salida deseada?
La solución fue el **Algoritmo Backpropagation** (Retropropagación del error).

### ¿Cómo funciona matemáticamente?
1. **Feedforward:** Los datos pasan de la entrada a la salida.
2. **Cálculo del Error Global ($E_p$):** Basado en la diferencia entre la salida real de la capa final y la deseada.
3. **Retropropagación:** Se usa la **Regla de la Cadena** (Cálculo Multivariable) para derivar el error global con respecto a los pesos de las capas ocultas ($\frac{\partial E_p}{\partial w_{ji}}$). El error "fluye" hacia atrás.

### Optimizadores de Alto Desempeño
El libro resalta que el Gradiente Descendente estándar es muy lento. Por ello, en aplicaciones reales de MATLAB usamos algoritmos avanzados:
1. **Gradiente Conjugado:** Evita el costoso cálculo de la Matriz Hessiana moviéndose en direcciones "conjugadas" que aceleran la convergencia.
2. **Levenberg-Marquardt (`trainlm`):** Una mezcla suave entre el método de Newton y Gradiente Descendente. **Es el algoritmo por defecto que usarás en MATLAB para MLP porque es extremadamente rápido en redes de tamaño moderado.**

### Sobre-entrenamiento y Regularización
Si tu red tiene demasiadas neuronas ocultas, "memorizará" los datos con ruido en lugar de aprender el patrón (sobre-entrenamiento). El libro propone:
- **Parada Temprana (Early Stopping):** Dividir los datos en Entrenamiento, Validación y Prueba. Si el error de validación comienza a subir mientras el de entrenamiento baja, ¡detén el entrenamiento!

### Ejemplo Clásico: Resolviendo XOR con MLP en MATLAB
```matlab
% Problema NO linealmente separable
x = [0 0 1 1; 0 1 0 1];
yd = [0 1 1 0];

% Creamos una red MLP (newff) con 10 neuronas en la capa oculta
% Activación tangente sigmoidal (tansig) en la oculta y lineal (purelin) en la salida
red = newff(minmax(x), [10 1], {'tansig', 'purelin'}, 'trainlm');

% Configuramos y entrenamos
red.trainParam.epochs = 200;
red = train(red, x, yd);

% Simulamos la salida
Yred = sim(red, x);
```

---

## 4. El uso de UV-SRNA

UV-SRNA es el simulador desarrollado en la Universidad del Valle. Para usarlo eficientemente:
1. **Formato de Patrones:** Debes crear archivos `.pat`. La primera línea es la cantidad de patrones, la segunda las entradas por patrón, la tercera las salidas, y luego la matriz de datos.
2. **Ventaja:** Permite visualizar gráficamente y sin programar cómo se mueve la recta de separación en el Perceptrón, o cómo evoluciona la superficie de error en el MLP.

---
*Esta guía integra los conceptos fundamentales de tu material oficial, explicados con un nivel superior de ingeniería para que domines tanto la teoría como los laboratorios en MATLAB/Simulink.*
