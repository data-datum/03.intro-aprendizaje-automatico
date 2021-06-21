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


### Laboratorio 1

En esta primer entrega se trabajó con el dataset de *Boston House Prices*, el cual está disponible en el UCI Machine Learning
https://archive.ics.uci.edu/ml/machine-learning-databases/housing/

#### Descripción de las variables dentro del dataset

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


*Este dataset no contiene valores nulos, por lo que no es necesario hacer imputaciones.* 

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
Se eligieron 2 variables más a partir del item de visualización de datos, y se repitió la regresión polinomial con las variables seleccionadas. 



