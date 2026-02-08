# Análisis de Factores que Influyen en la Venta de Productos

## 1. Objetivo y pregunta central

**Objetivo general:**  
Analizar y modelar los factores que influyen en la cantidad vendida de productos, utilizando técnicas de análisis de datos y aprendizaje automático, con el fin de identificar las variables más relevantes para la toma de decisiones comerciales.

**Pregunta central:**  
> ¿Qué factores influyen más en la venta (cantidad vendida) de un producto?

---

## 2. Fuente de los datos y proceso de limpieza

### Fuente de los datos
El conjunto de datos corresponde a registros de ventas de productos, donde cada fila representa una transacción individual.  
Las variables incluyen información del producto, precio, ciudad, vendedor, fecha y cantidad vendida.

### Proceso de limpieza y preparación
Se realizaron las siguientes acciones:

- Conversión de la columna `fecha` a formato datetime.
- Estandarización de variables categóricas (ciudad, categoría, vendedor).
- Eliminación de variables identificadoras sin valor explicativo (`id_producto`, `nombre_producto`).
- Manejo de valores faltantes en la variable `nombre_vendedor` mediante la categoría *“No asignado”*.
- Creación de variables derivadas:
  - `mes`: extraído de la fecha.
  - `ingreso`: calculado como `precio × cantidad_vendida`.

---

## 3. Técnicas de minería de datos aplicadas

Se aplicaron las siguientes técnicas:

- **Análisis exploratorio de datos (EDA)**  
  Para comprender la distribución de las variables, detectar patrones y posibles relaciones entre ellas.

- **Preprocesamiento de datos**  
  - One-Hot Encoding para variables categóricas.
  - Uso de `Pipeline` y `ColumnTransformer` para garantizar un flujo reproducible.

- **Modelo de Machine Learning: Random Forest Regressor**  
  - Seleccionado por su capacidad para modelar relaciones no lineales.
  - Permite obtener la **importancia relativa de las variables**.
  - Evaluado mediante el coeficiente de determinación (R²).

---

## 4. Resultados obtenidos y conclusiones

### Evaluación del modelo
- **R² del modelo:** 0.62  
  El modelo explica aproximadamente el **62 % de la variabilidad** de la cantidad vendida, lo que indica un buen desempeño para un problema de negocio real.

### Factores más influyentes
Según la importancia de variables del Random Forest:

1. **Ingreso**
2. **Precio**
3. **Mes**
4. Ciudad
5. Categoría
6. Vendedor

### Conclusiones principales
- El **ingreso generado por la venta** es el factor más influyente en la cantidad vendida.
- El **precio del producto** tiene un impacto significativo en el comportamiento de compra.
- Existe un **efecto temporal** (mes) que sugiere cierta estacionalidad.
- Variables operativas como ciudad y vendedor influyen, pero de forma secundaria.

En general, los resultados indican que las ventas están principalmente impulsadas por factores económicos y temporales más que por factores operativos.

---

## 5. Limitaciones y recomendaciones futuras

### Limitaciones
- El tamaño del conjunto de datos es limitado.
- No se incluyen variables externas como promociones, campañas de marketing o características del cliente.
- La importancia de variables en Random Forest no indica causalidad.

### Recomendaciones futuras
- Incorporar variables adicionales (descuentos, tipo de cliente, canal de venta).
- Probar otros modelos (XGBoost, LightGBM).
- Realizar análisis de dependencia parcial (Partial Dependence Plots).
- Validar el modelo con datos de otros periodos temporales.

---

📌 *Este proyecto demuestra cómo el análisis de datos y el aprendizaje automático pueden apoyar la toma de decisiones comerciales basadas en evidencia.*
