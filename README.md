# **eye-movements-modelos-ll-2025-2**

## **Modelos ll - Proyecto (2025-2)**


Jasmin Juliana Jaramillo Tapias - jasmin.jaramillo@udea.edu.co

Andres Dario Higuita Perez - adario.higuita@udea.edu.co

Juan Guillermo Preciado Zapata - guillermo.preciado@udea.edu.co

### **Basado en Proyecto de OpenML:**

**DataSet:**
https://www.openml.org/search?type=data&sort=runs&status=active&qualities.NumberOfFeatures=between_10_100&qualities.NumberOfInstances=between_10000_100000&qualities.NumberOfClasses=gte_2&id=1044

**NoteBook:**
Proyecto_Machine_Learning_Movimiento_Ocular_grupo21_EntregaFinal.ipynb

**Url de Presentación:**

**Profesor: JULIAN DAVID ARIAS LONDOÑO correo: julian.ariasl@udea.edu.co**

**UNIVERSIDAD DE ANTIOQUIA**

## Segunda entrega

Este repositorio contiene el análisis completo del dataset de **movimientos oculares (eye movements)**, con énfasis en:

- Preprocesamiento avanzado  
- Entrenamiento de múltiples modelos supervisados  
- Evaluación comparativa  
- Reducción de dimensionalidad mediante **PCA** y **UMAP**  
- Construcción de pipelines reproducibles

El desarrollo completo se encuentra en el notebook:

📄 **Proyecto_Machine_Learning_Movimiento_Ocular_grupo21_EntregaFinal.ipynb**

*Por favor ejecutar en el orden del contenido del notebook de arriba hacia abajo*

---

## 📑 **Contenido del Notebook**

### **1. Carga de Librerías y Dependencias**

Incluye todas las librerías necesarias para:

- Procesamiento de datos (`pandas`, `numpy`)  
- Visualización (`matplotlib`, `seaborn`)  
- Modelos (`sklearn`)  
- Reducción dimensional (`PCA`, `UMAP`)  
- Construcción de pipelines  

---

### **2. Carga del Dataset**

Se cargan los datos del experimento de movimientos oculares y se realiza:

- Revisión de estructura  
- Validación de tipos  
- Revisión de valores faltantes  
- Distribución de la variable objetivo  

---

### **3. Análisis Exploratorio y Transformación de Datos**

Se desarrollan:

- Histogramas de variables continuas  
- Matrices de correlación  
- Detección de outliers  
- Inspección de relación entre características y clases  
- Selección y limpieza preliminar de variables  

---

### **4. División en Entrenamiento y Prueba**

Los datos se dividen en:

- `X_train` / `X_test`  
- `y_train` / `y_test`  

Usando muestreo estratificado para mantener la proporción de clases.

---

### **5. Preprocesamiento de Datos**

Se construye un `ColumnTransformer` que aplica:

- **StandardScaler** a variables numéricas  
- **OneHotEncoder** a variables categóricas  

Este preprocesador es reutilizado en todos los pipelines.

---

### **6. Entrenamiento de Modelos**

Se entrenan distintos enfoques:

---

#### 🔹 Modelos Paramétricos

- Regresión Logística Multiclase  
- LDA  
- QDA  

---

#### 🔹 Modelos No Paramétricos

- K-Nearest Neighbors  
- Random Forest  
- Support Vector Classifier (SVC)  
- MLPClassifier (red neuronal multicapa)  

Cada modelo se entrena dentro de un **Pipeline**:

```
(preprocesamiento) → (modelo)
```

---

## **7. Reducción de Dimensionalidad**

### 🟦 PCA

- Cálculo de varianza explicada  
- Determinación del número óptimo de componentes  
- Integración en pipeline:  
  ```
  preprocesamiento → PCA → modelo
  ```

---

### 🟪 UMAP

- Reducción supervisada o no supervisada  
- Visualización del embedding  
- Entrenamiento de modelos directamente sobre el espacio reducido  

---

## **8. Comparación Final de Modelos**

Se genera una tabla consolidada con todas las métricas:

- Accuracy  
- Recall  
- Precision  
- F1-score  

Comparando:

- Modelos base  
- Modelos con PCA  
- Modelos con UMAP  

---

## 🏁 **Conclusiones Principales**

- Random Forest mostró el mejor desempeño general.  
- PCA ofrece una ligera mejora en algunos modelos.  
- UMAP depende fuertemente de los hiperparámetros y del preprocesamiento.  
- Se identificaron características con baja capacidad discriminativa.  
- PCA seleccionó un número óptimo de ~16 componentes (90% varianza).  

---

## 📂 Estructura del Repositorio

```
notebook/Proyecto_Machine_Learning_Movimiento_Ocular_grupo21_EntregaFinal.ipynb      # Notebook principal
notebook/hiperparametros_modelos.json                                                # Hiperparametros de los modelos
reporte/Proyecto_Machine_Learning_Movimiento_Ocular_grupo21.pdf                      # Informe realizado en PDF
README.md                                                                            # Este archivo
