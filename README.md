# Proyecto final IA - Stroke Prediction 

Integrantes: Juan Camilo Riveros Pinzón y Darwin Felipe Castro

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
   Con reduccion dimensional              
|-----------------------------|
|  METODO  |   MCC   |   F1   |
|   KNN    |  0.221  | 0.668  |
|   ANN    |  0.196  | 0.661  |
|   RF     |  0.362  | 0.671  |
|-----------------------------|
   Sin reduccion dimensional
|-----------------------------|
|  METODO  |   MCC   |   F1   |
|   KNN    |  0.493  | 0.623  |
|   ANN    |  0.722  | 0.848  |
|   RF     |  0.872  | 0.928  |
|-----------------------------|

```
### Conclusiones

```
- Se logro observar que con el metodo de random forest se logro obtener los mejores resultados tanto para 
el MCC como el F1, tambien se logro el mismo resultado realizando la reduccion dimensional y sin hacerlo.
- Teniendo en cuenta los resultados obtenidos con reduccion y sin reduccion dimensional (PCA), se puede 
concluir que no vale la pena realizar esta reduccion debido a que obtuvo para los 3 metodos un puntaje de 
evaluacion tanto para el MCC como el F1 mucho menor que sin hacer la reduccion.
- Es importante revisar si nuestro conjunto de datos tiene suficientes etiquetas de salida de cada clase, 
como para considerarlo un conjunto balanceado, si no, podemos aplicar la funcion SMOTE() para balancear 
los datos de salida y realizar un mejor modelo.
```
### Link del video
https://youtu.be/0JfcokUWoi8
