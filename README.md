# Proyecto final IA - Stroke Prediction 

Juan Camilo Riveros Pinzón
Darwin Felipe Castro

## Introduccion

Se quiso desarrolla un modelo que predijera segun ciertas caracteristicas de una persona si esta tendria o no un derrame cerebral, mediante diferentes metodos de machine learning.
### Contexto.

Segun la organizacion mundial de la salud, los derrames cerebrales son la causa de aproximadamente el 11% de las muertes a nivel mundial. 

El siguiente dataset se utiliza para predecir si una persona con determinadas caracteristicas puede sufrir un derrame cerebral o no: https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset?datasetId=1120859&sortBy=commentCount

Informacion de los atributos:
```
1) id: unique identifier
2) gender: "Male", "Female" or "Other"
3) age: age of the patient
4) hypertension: 0 if the patient doesn't have hypertension, 1 if the patient has hypertension
5) heart_disease: 0 if the patient doesn't have any heart diseases, 1 if the patient has a heart disease
6) ever_married: "No" or "Yes"
7) work_type: "children", "Govt_jov", "Never_worked", "Private" or "Self-employed"
8) Residence_type: "Rural" or "Urban"
9) avg_glucose_level: average glucose level in blood
10) bmi: body mass index
11) smoking_status: "formerly smoked", "never smoked", "smokes" or "Unknown"*
12) stroke: 1 if the patient had a stroke or 0 if not

```
### Desarrollo

Se utilizo la libreria pandas con el fin de manipular el conjunto de datos, asi mismo para limpiar algunos datos faltantes, posteriormente, se remplazaron los datos no numericos por valores numericos. Seleccionamos nuestros atributos como entrada, la prediccion como la salida y realizamos la particion del conjunto de datos. 
En este caso, el dataset esta bastante desbalanceado, cosa que puede ser mala para el entrenamiento del metodo, esto se puede solucionar con la funcion SMOTE(), la cual crea salidas a partir de entradas similares, con el fin de balancear las muestras.
Escalizamos los datos, y procedemos a realizar una descomposicion dimensional.
En este caso, se utilizaron los siguientes metodos:
-KNN
-SVM
-ANN
-RandomForest
-DecisionTree

En cada metodo, se hizo un grid search en primera instancia para optimizar los hiperparametros, con los mejores se volvia a entrenar el metodo, y se sacaba el MCC  y el F1.

## Resultados
```
|-----------------------------|
|  METODO  |   MCC   |   F1   |
|   KNN    |  0.539  | 0.774  |
|   SVM    |  0.041  | 0.458  |
|   ANN    |  0.589  | 0.808  |
|   RF     |  0.869  | 0.927  |
|   DT     |  0.095  | 0.671  |
|-----------------------------|

```
### Conclusiones

Explain what these tests test and why

```
Give an example
```