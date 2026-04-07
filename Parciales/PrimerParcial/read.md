## RegresionBike_Completo.ipynb

**Dataset:** Bike Sharing Dataset (Número 4) - Predicción de demanda diaria de bicicletas alquiladas

### Métodos implementados:
1. **Descenso por el Gradiente (Gradient Descent)**
   - Entrenado sobre 548 ejemplos (75% del dataset)
   - Parámetro de aprendizaje: α = 0.1
   - Iteraciones: 400
   - Monitoreo de convergencia del costo J

2. **Normalización de características**
   - Aplicada normalización Z-score a todos los 11 features
   - Permite que el gradient descent converja eficientemente

3. **Split Training/Test**
   - **75% Entrenamiento** (548 ejemplos)
   - **25% Prueba** (183 ejemplos)
   - Separación temporal para evaluar generalización

4. **Evaluación del modelo**
   - **Métricas calculadas:** MSE, RMSE, R²
   - **Evaluadas en ambos sets:** Training y Test

### Control de Overfitting:
- **Detección automática:** Si diferencia |R²_test - R²_train| > 0.1
- **Ridge Regression (L2):** Aplicada cuando hay overfitting detectado (λ=10)
- **Resultado:** Redujo la diferencia de R² de 0.2158 a 0.2100

### Visualizaciones:
- Gráfico de convergencia del modelo
- Scatter plots: Predicciones vs Valores Reales (Training y Test)
- Tabla comparativa de métricas

