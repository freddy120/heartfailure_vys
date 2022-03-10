---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---


## Proyecto Final
Este proyecto final del curso de  Visualización y storytelling de la Maestría en Inteligencia Analítica de Datos MIAD

Elaborado por: 
* Freddy Rodrigo Mendoza Ticona. 
* William Alexander Romero Bolívar. 
* Maria Paula Salamanca Delgado.
* Jorge Oswaldo Suárez Rodríguez.


### Notebook de procesamiento:
* Jupyter notebook del modelado de datos [notebook](https://github.com/freddy120/heartfailure_vys/blob/main/Proyecto_Final_VyS.ipynb) [![Foo](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/freddy120/heartfailure_vys/blob/main/Proyecto_Final_VyS.ipynb)

### Fuentes de datos:
El tema de nuestro proyecto es analizar e identificar los factores más importantes que pueden producir un problema cardiaco, para ello contamos con 3 fuentes de datos.
* Causas de muerte de colombia en 2019. 
  * Global Health Estimates 2020: Deaths by Cause, Age, Sex, by Country and by Region, 2000-2019. Geneva, World Health Organization; 2020. [https://www.who.int/data/gho/data/themes/mortality-and-global-health-estimates/ghe-leading-causes-of-death](https://www.who.int/data/gho/data/themes/mortality-and-global-health-estimates/ghe-leading-causes-of-death)
* Datos de predicción de insuficiencia cardíaca: Aquí tenemos 918 observaciones de pacientes con 11 variables de interés. 
  * fedesoriano. (September 2021). Heart Failure Prediction Dataset. Retrieved [Date Retrieved] from [https://www.kaggle.com/fedesoriano/heart-failure-prediction](https://www.kaggle.com/fedesoriano/heart-failure-prediction). 
* Datos de enfermedad cardiovascular: Aquí tenemos 70000 observaciones de pacientes con 11 variables de interés relativamente diferentes al dataset anterior y que nos permiten aumentar el análisis. 
  * [https://www.kaggle.com/fedesoriano/heart-failure-prediction](https://www.kaggle.com/fedesoriano/heart-failure-prediction)



### Variables de la fuente de datos original:

Las variables mantienen su nombre original.

| Nombre         | Descripción                                                              | Tipo      |
| -------------- |--------------------------------------------------------------------------|-----------|
| Age            | Edad del paciente                                                        | numérico  |
| Sex            | Sexo del paciente                                                        | texto     |
| ChestPainType  | Tipo de dolor de pecho                                                   | texto     |
| RestingBP      | Presión arterial en reposo                                               | numérico  |
| Cholesterol    | Colesterol total                                                         | numérico  |
| FastingBS      | Glucosa sanguínea en ayunas                                              | texto |
| RestingECG     | Resultados del electrocardiograma en reposo                              | texto |
| MaxHR          | Frecuencia cardíaca máxima alcanzada                                     | numérico  |
| ExerciseAngina | Dolor de pecho inducida por el ejercicio                                 | texto |
| Oldpeak        | Depresión del ST inducida por el ejercicio en relación con el reposo     | numérico  |
| ST\_Slope      | La pendiente del segmento ST del electrocardiograma en ejercicio máximo  | texto |
| HeartDisease      | predictor de enfermedad del corazón                                      | texto |


### Variables luego del modelado:

Luego de aplicar la limpieza, minado y filtrado de los datos nos quedamos con las siguientes variables, se traducen el nombre de las variables al español.

| Nombre         | Descripción                                                              | Tipo      |
| -------------- |--------------------------------------------------------------------------|-----------|
| Edad            | Edad del paciente                                                        | numérico  |
| Sexo            | Sexo del paciente                                                        | texto     |
| Dolor de pecho  | Tipo de dolor de pecho                                                   | texto     |
| Presión arterial en reposo      | Presión arterial en reposo                                               | numérico  |
| Colesterol total    | Colesterol total                                                         | numérico  |
| Glucosa sanguínea en ayunas      | Glucosa sanguínea en ayunas                                              | texto |
| EEG en reposo     | Resultados del electrocardiograma en reposo                              | texto |
| Max Frecuencia cardíaca          | Frecuencia cardíaca máxima alcanzada                                     | numérico  |
| Angina de ejercicio | Dolor de pecho inducida por el ejercicio                                 | texto |
| Depresión del ST inducida        | Depresión del ST inducida por el ejercicio en relación con el reposo     | numérico  |
| Pendiente ST     | La pendiente del segmento ST del electrocardiograma en ejercicio máximo  | texto |
| Enfermedad cardíaca      | predictor de enfermedad del corazón                                      | texto |


### Modelado

* Se descargan las bases de datos en formato csv o excel, a la fecha se utilizaron los siguientes:
  * Datos de predicción de insuficiencia cardíaca: [https://freddy120.github.io/heartfailure_vys/files/heart.csv](https://freddy120.github.io/heartfailure_vys/files/heart.csv)
  * Datos de enfermedad cardiovascular: [https://freddy120.github.io/heartfailure_vys/files/cardio_train.csv](https://freddy120.github.io/heartfailure_vys/files/cardio_train.csv)
  * Causas de muerte de colombia en 2019: [https://freddy120.github.io/heartfailure_vys/files/causesofdeath_colombia_2019.xlsx](https://freddy120.github.io/heartfailure_vys/files/causesofdeath_colombia_2019.xlsx)
* Se usa jupyter notebook para hacer el modelado, se puede usar colab para abrirlo.
* Se carga el archivo 'heart.csv’ en la ubicación del notebook para poder cargarlo con pandas.

```python
heart_df = pd.read_csv("heart.csv")
```

* Se realiza un análisis de las variables numéricas y categóricas y no se encuentran problemas que sea necesario de estandarizar.

![img.png](img.png)

* Se eliminan posibles nulos y datos duplicados.

```python
heart_df = heart_df.dropna()
heart_df = heart_df.drop_duplicates()
```


* Se realiza la traducción del nombre de las variables.

```python
heart_df = heart_df.rename(columns = {'Age': 'Edad', 'Sex': 'Sexo', 'ChestPainType': 'Dolor de pecho', 
                                      'RestingBP': 'Presión arterial en reposo', 'Cholesterol': 'Colesterol total', 
                                      'FastingBS': 'Glucosa sanguínea en ayunas', 'RestingECG': 'EEG en reposo', 
                                      'MaxHR': 'Max Frecuencia cardíaca', 'ExerciseAngina': 'Angina de ejercicio', 
                                      'Oldpeak': 'Depresión del ST inducida', 'ST_Slope': 'Pendiente ST', 'HeartDisease': 'Enfermedad cardíaca'}, inplace = False)
```

* Por último, se crea un nuevo csv después de ejecutar todo el jupyter notebook, el cual utilizaremos para crear el dashboard.

```python
heart_df.to_csv('heart_procesado.csv',  index=False)
```


### Datos procesados
* Base de datos procesado [dataset procesado](https://freddy120.github.io/heartfailure_vys/files/heart_procesado.csv)
