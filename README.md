# Repositorio de la materia "Introducción al Aprendizaje Automático". 
#### Diplomatura en Ciencia de Datos, Aprendizaje Automático y sus Aplicaciones. *Edición 2021*

Integrantes:
* Devesa, Maria Roberta. 
* Feldfeber, Ivana. 
* Finzi, Nadia. 
* Kinigsberg, Ezequiel. 
* Villafañe, Roxana Noelia


En este repositorio se encuentran los dos notebooks correspondientes a los dos entregables de la materia:
"Introducción al Aprendizaje Automático. 

* Repositorio de Github de la materia: https://github.com/DiploDatos/IntroduccionAprendizajeAutomatico


### Laboratorio 1 - Regresión

En esta primer entrega se trabajó con el dataset de *Boston House Prices*, el cual está disponible en el UCI Machine Learning
https://archive.ics.uci.edu/ml/machine-learning-databases/housing/

#### Descripción de las variables dentro del dataset 
*(Para un análisis más detallado junto a los resultados y conclusiones correspondientes ver el notebook con nombre `Labo-1-regresion.ipynb`)* 

Este conjunto de datos contiene los valores de las propiedades en la región de Boston, donde se considera la información de:

    CRIM: la taza de crimen per capita por barrio
    ZN: proporción de tierra residencial, para lotes mayores a 25000 pies cuadrados
    INDUS: proporción de hectáreas comerciales por barrio
    CHAS: variable fictia del Río Charles. Vale 1 si el tramo limita con el río, si no 0.
    NOX: concentración de óxido nítrico, en partes por millón.
    RM: promedio de habitaciones por vivienda.
    AGE: proporción de viviendas ocupadas por sus propietarios construidas antes de 1940.
    DIS: distancias ponderadas a los cinco centros de empleo de Boston.
    RAD: índice de accesibilidad a las autopistas ¿radiales?
    TAX: tasa de impuesto a la propiedad por cada $10.000.
    PTRATIO: proporción estudiante-docente por barrio.
    B: 1000.(Bk - 0,63)^2 siendo Bk la proporción de gente de color por barrio.
    LSTAT: porcentaje de población de menor status.
    MEDV: valor medio de viviendas ocupadas por sus propietarios, en miles de dólares.

**Notas**
* Este dataset no contiene valores nulos, por lo que no es necesario hacer imputaciones.
* Durante este análisis no realizaron cálculos ni transformaciones matemáticas que tengan que ver limpieza y curación de datos. 


#### Breve descripción de los análisis realizados

**Visualización de los Datos**
En esta instancia se realizaron gráficos exploratorios para identificar visualmente variables que son más importantes para los posteriores análisis, en este caso, de regresión. 

![Image text](https://github.com/data-datum/03.intro-aprendizaje-automatico/blob/main/scatterplots.jpg)

**Regresión lineal**
Se eligió una variable del dataset, se realizó una regresión lineal simple y se evaluó la recta con las métricas correspondientes. Esta variable fue `LSTAT`. 


![Image text](https://github.com/data-datum/03.intro-aprendizaje-automatico/blob/main/regresion-lineal.jpg)

**Regresión Polinomial**
Con la misma variable del punto anterior, se realizó una regresión polinomial. Se evaluaron lo resultados correspondientes. 

![Image text](https://github.com/data-datum/03.intro-aprendizaje-automatico/blob/main/reg-pol.png)


**Regresión con más de una variable**
Se eligieron 3 variables en total a partir del item de visualización de datos (`LSTAT`, `RM`y `NOX`), y se repitió la regresión polinomial con las variables seleccionadas. 

En todos los casos se analizaron los errores de train y test. La métrica seleccionada fue el *mean square error*. 



### Laboratorio 2 - Clasificación

En esta segunda entrega se trabajó con el dataset de *Home Equity dataset*, el cual está disponible en Kaggle

https://www.kaggle.com/ajay1735/hmeq-data 

#### Descripción de las variables dentro del dataset 
*(Para un análisis más detallado junto a los resultados y conclusiones correspondientes ver el notebook con nombre `Labo-2.ipynb`)* 

Variables del modelo:

    'LOAN' (préstamo): Monto de la solicitud de préstamo
    'MORTDUE': Monto adeudado de la hipoteca existente
    'VALUE': Valor de la propiedad actual
    'YOJ': Años en el trabajo actual
    'DEROG': Número de reportes derogados
    'DELINQ': Número de créditos adeudados
    'CLAGE': Antigüedad de la línea de crédito más antigua (en meses)
    'NINQ': Número de líneas de crédito recientes
    'CLNO': Número de líneas de crédito
    'DEBTINC': Relación deuda-ingresos
    'TARGET': Vale 0 cuando el cliente pagó el préstamo, y 1 cuando no. 


Variable a predecir: TARGET, que hace referencia a si se pagó o no el préstamo. 

**Notas**
* Este dataset no contiene valores nulos, por lo que no es necesario hacer imputaciones.
* Durante este análisis no realizaron cálculos ni transformaciones matemáticas que tengan que ver limpieza y curación de datos. 

#### Modelos lineales

En esta primer etapa se ajustaron modelos lineales de clasificación para predecir la variable objetivo.

##### SGDClassifier con hiperparámetros por defecto

En esta etapa se hizo un ajuste del algoritmo por defecto de `SGDClassifier()` . Solamente se fijo la semilla aleatoria para que sea reproducible. 

Se reportaron valores de

    Accuracy
    Precision
    Recall
    F1
    matriz de confusión
    
 

#####  Ajuste de Hiperparámetros de SGDClassifier

Se seleccionaron valores para los hiperparámetros del SGDClassifier. Se probaron diferentes funciones de loss, tasas de entrenamiento y tasas de regularización. 
Se utilizo un GridSearchCV y una validación cruzada de 5-fold en el conjunto de entrenamiento para explorar combinaciones posibles de valores. 
Se reportó Accuracy promedio y varianza para todas las posibles configuraciones. En cada fold (o set de datos) mediante validacion cruzada se obtuvieron diversos valores de Accuracy, estos valores se promedian y se reporta este valor promedio. 
Tambien se reportaron valores de 


    Precision
    Recall
    F1
    matriz de confusión
    


#### Árboles de decisión

##### DecisionTreeClassifier con hiperparámetros por defecto

En esta etapa se hizo un ajuste del algoritmo por defecto de `DecisionTreeClassifier()` . Solamente se fijo la semilla aleatoria para que sea reproducible. 

Se reportaron valores de 


    Accuracy
    Precision
    Recall
    F1
    matriz de confusión
    
 

##### Ajuste de Hiperparámetros de DecisionTreeClassifier

Se seleccionaron vvalores para los hiperparámetros del DecisionTreeClassifier. Se probaron diferentes criterios de partición (criterion), profundidad máxima del árbol (max_depth), y cantidad mínima de muestras (samples) por hoja (min_samples_leaf). 
Se utilizó grid search y un 5-fold CV para el conjunto de entrenamiento para explorar diferentes posibles combinaciones de valores. 
Se reportaron valores de Accuracy promedio y varianza en todos los casos. En cada fold (o set de datos) mediante validacion cruzada se obtuvieron diversos valores de Accuracy, estos valores se promedian y se reporta este valor promedio. 
También se reportaron valores de 

    Precision
    Recall
    F1
    matriz de confusión
    
    
