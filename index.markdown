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

Datos de predicción de insuficiencia cardíaca:

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


Datos de enfermedad cardiovascular: 

| Nombre         | Descripción                                                              | Tipo      |
| -------------- |--------------------------------------------------------------------------|-----------|
| age            | Edad del paciente                                                        | numérico  |
| gender            | Sexo del paciente                                                        | texto     |
| height  | Altura del paciente                                                   | numérico     |
| weight      |Peso del paciente                                             | numérico  |
| ap_hi    | Presión sanguínea sistólica                                                         | numérico  |
| ap_lo      |Presión arterial diastólica                                            | numérico |
| cholesterol     | colesterol                              | texto |
| gluc          | glucosa                                  | texto  |
| smoke | fumar                                 | texto |
| alco        | consumo de alcohol | texto  |
| active      | actividad fisica  | texto |
| cardio      | si presenta enfermedad cardiovascular                                  | texto |


Causas de muerte de colombia en 2019:

| Nombre         | Descripción                                                              | Tipo      |
| -------------- |--------------------------------------------------------------------------|-----------|
| Cause            | causa de muerte                                                   | texto  |
| ISO3            | pais                                                       | texto     |
| Year  | año                                                  | numérico     |
| Sex      | sexo                                         | texto  |
| Age Group    | grupo de edad                                                       | texto  |
| Population      | poblacion                                             | numérico |
| Deaths     | cantidad de muertes                            | numérico |
| Death rate per 100 000 population          | tasa de muertes por 100 000 habitantes                                     | numérico  |
| DALY | DALY                                | numérico |
| DALY rate per 100 000 population        | tasa de DALY por 100 000 habitantes     | numérico  |


### Variables luego del modelado:

Luego de aplicar la limpieza, minado y filtrado de los datos nos quedamos con las siguientes variables.

Datos de predicción de insuficiencia cardíaca:

| Nombre         | Descripción                                                              | Tipo      |
| -------------- |--------------------------------------------------------------------------|-----------|
| Edad            | Edad del paciente                                                        | numérico  |
| Sexo            | Sexo del paciente                                                        | texto     |
| Dolor de pecho  | Tipo de dolor de pecho                                                   | texto     |
| Presión arterial en reposo(mm Hg)      | Presión arterial en reposo                                               | numérico  |
| Colesterol total(mm/dl)    | Colesterol total                                                         | numérico  |
| Glucosa sanguínea en ayunas      | Glucosa sanguínea en ayunas                                              | texto |
| EEG en reposo     | Resultados del electrocardiograma en reposo                              | texto |
| Max Frecuencia cardíaca          | Frecuencia cardíaca máxima alcanzada                                     | numérico  |
| Angina de ejercicio | Dolor de pecho inducida por el ejercicio                                 | texto |
| Depresión del ST inducida        | Depresión del ST inducida por el ejercicio en relación con el reposo     | numérico  |
| Pendiente ST     | La pendiente del segmento ST del electrocardiograma en ejercicio máximo  | texto |
| Enfermedad cardíaca      | predictor de enfermedad del corazón                                      | texto |


Datos de enfermedad cardiovascular: 

| Nombre         | Descripción                                                              | Tipo      |
| -------------- |--------------------------------------------------------------------------|-----------|
| Edad            | Edad del paciente                                                        | numérico  |
| Sexo            | Sexo del paciente                                                        | texto     |
| altura(cm)  | Altura del paciente                                                   | numérico     |
| Peso(kg)      |Peso del paciente                                             | numérico  |
| Presión sanguínea sistólica    | Presión sanguínea sistólica                                                         | numérico  |
| Presión arterial diastólica      |Presión arterial diastólica                                            | numérico |
| Nivel de Colesterol     | colesterol                              | texto |
| Nivel de Glucosa          | glucosa                                  | texto  |
| De fumar | fumar                                 | texto |
| Consumo de alcohol        | consumo de alcohol | texto  |
| Actividad física      | actividad fisica  | texto |
| Enfermedad cardíaca      | si presenta enfermedad cardiovascular                                  | texto |


Causas de muerte de colombia en 2019:

| Nombre         | Descripción                                                              | Tipo      |
| -------------- |--------------------------------------------------------------------------|-----------|
| Causa            | causa de muerte                                                   | texto  |
| Población      | poblacion                                             | numérico |
| Muertes     | cantidad de muertes                            | numérico |
| Tasa de mortalidad por 100 000 habitantes          | tasa de muertes por 100 000 habitantes                                     | numérico  |



### Modelado

* Se descargan las bases de datos en formato csv o excel, a la fecha se utilizaron los siguientes:
  * Datos de predicción de insuficiencia cardíaca: [https://freddy120.github.io/heartfailure_vys/files/heart.csv](https://freddy120.github.io/heartfailure_vys/files/heart.csv)
  * Datos de enfermedad cardiovascular: [https://freddy120.github.io/heartfailure_vys/files/cardio_train.csv](https://freddy120.github.io/heartfailure_vys/files/cardio_train.csv)
  * Causas de muerte de colombia en 2019: [https://freddy120.github.io/heartfailure_vys/files/causesofdeath_colombia_2019.xlsx](https://freddy120.github.io/heartfailure_vys/files/causesofdeath_colombia_2019.xlsx)
* Se usa jupyter notebook para hacer el modelado, se puede usar colab para abrirlo.
* Se carga los archivos csv y/o excel en la ubicación del notebook para poder cargarlo con pandas.

```python
heart_df = pd.read_csv("heart.csv")
cardio_df = pd.read_csv("cardio_train.csv", delimiter=';')
causas_muerte_df = pd.read_excel("causesofdeath_colombia_2019.xlsx")
```
* se realiza la limpieza de datos.
  * Eliminación de registros duplicados.
  * Eliminación de registros con datos nulos.
  * Eliminar columnas de ID.
  * Eliminación de columnas que no aportan al problema.
  * Análisis exploratorio inicial.
  * Buscamos con las distribuciones alguna variable que más contribuya a la predicción de falla cardíaca o enfermedad cardiovascular.
  * En el dataset de causas de muerte observamos que existen muchas causas de muerte, nos interesa solo el top 15.

```python
heart_df = heart_df.dropna().drop_duplicates()
cardio_df = cardio_df.dropna().drop_duplicates()
cardio_df = cardio_df.drop(columns=['id'])
causas_muerte_df = causas_muerte_df.dropna().drop_duplicates()
causas_muerte_df = causas_muerte_df.drop(columns=['Code', 'ISO3', 'Sex', 'Age Group'])
```

* Transformacion de variables, cambio de unidades.
* Se realiza la traducción de nombres de variables del inglés al español.
* Estandarizar etiquetas de variables categóricas y traducción al español.

```python
heart_df['Sex'] = heart_df['Sex'].apply(lambda x: "Masculino" if x=='M' else 'Femenino')
heart_df['FastingBS'] = heart_df['FastingBS'].apply(lambda x: "> 120 mg/dl" if x ==1 else "<= 120 mg/dl")
heart_df['ExerciseAngina'] = heart_df['ExerciseAngina'].apply(lambda x: "Si" if x=='Y' else 'No')
heart_df['HeartDisease'] = heart_df['HeartDisease'].apply(lambda x: "Si" if x==1  else 'No')
heart_df["ChestPainType"].replace({"ATA": "Angina atípica", "NAP": "Dolor no anginoso", "ASY": "Asintomático", "TA": "Angina típica"}, inplace=True)

heart_df = heart_df.rename(columns = {'Age': 'Edad', 'Sex': 'Sexo', 'ChestPainType': 'Dolor de pecho', 
                                      'RestingBP': 'Presión arterial en reposo(mm Hg)', 'Cholesterol': 'Colesterol total(mm/dl)', 
                                      'FastingBS': 'Glucosa sanguínea en ayunas', 'RestingECG': 'EEG en reposo', 
                                      'MaxHR': 'Max Frecuencia cardíaca', 'ExerciseAngina': 'Angina de ejercicio', 
                                      'Oldpeak': 'Depresión del ST inducida', 'ST_Slope': 'Pendiente ST', 'HeartDisease': 'Enfermedad cardíaca'}, inplace = False)
```

```python
cardio_df['age'] = cardio_df['age'].apply(lambda x: round(x*0.0027))
cardio_df['gender'] = cardio_df['gender'].apply(lambda x: "Masculino" if x==2 else 'Femenino')
cardio_df['cardio'] = cardio_df['cardio'].apply(lambda x: "Si" if x==1  else 'No')
cardio_df["cholesterol"].replace({1: "Normal", 2: "Encima de lo normal", 3: "Muy por encima de lo normal"}, inplace=True)
cardio_df["gluc"].replace({1: "Normal", 2: "Encima de lo normal", 3: "Muy por encima de lo normal"}, inplace=True)
cardio_df["smoke"].replace({0: "No fumador", 1: "Fumador"}, inplace=True)
cardio_df["alco"].replace({0: "No Consumo de alcohol", 1: "Consumo de alcohol"}, inplace=True)
cardio_df["active"].replace({0: "No actividad física", 1: "Actividad física"}, inplace=True)

cardio_df = cardio_df.rename(columns = {'age': 'Edad', 'gender': 'Sexo', 'height': 'altura(cm)', 
                                      'weight': 'Peso(kg)', 'ap_hi': 'Presión sanguínea sistólica', 
                                      'ap_lo': 'Presión arterial diastólica', 'cholesterol': 'Nivel de Colesterol', 
                                      'gluc': 'Nivel de Glucosa', 'smoke': 'De fumar', 
                                      'alco': 'Consumo de alcohol', 'active': 'Actividad física', 'cardio': 'Enfermedad cardíaca'}, inplace = False)


```

```python
causas_muerte_df["Cause"].replace({"Ischaemic heart disease": "Enfermedad isquémica del corazón", 
                                           "Interpersonal violence": "Violencia interpersonal", 
                                           "Chronic obstructive pulmonary disease": "Afección pulmonar obstructiva crónica", 
                                           "Stroke": "Derrame cerebral",
                                           "Road injury": "Accidente automovilístico",
                                           "Lower respiratory infections": "Neumonía",
                                           "Stomach cancer": "Cáncer de estómago",
                                           "Kidney diseases": "Enfermedad renal",
                                           "Prostate cancer": "Cancer de prostata",
                                           "Hypertensive heart disease": "Hipertensión arterial",
                                           "Trachea, bronchus, lung cancers": "Tráquea, bronquios, cánceres de pulmón",
                                           "Neonatal conditions":"Condiciones neonatales",
                                           "HIV/AIDS": "VIH/SIDA",
                                           "Diabetes mellitus": "Diabetes mellitus",
                                           "Colon and rectum cancers": "Cánceres de colon y recto"}, inplace=True)


causas_muerte_df = causas_muerte_df.rename(columns = {'Cause': 'Causa', 'Population': 'Población',
                                                      'Death rate per 100 000 population': 'Tasa de mortalidad por 100 000 habitantes',
                                                      'Deaths': "Muertes"}, inplace = False)
causas_muerte_df = causas_muerte_df.drop(columns=['Year', 'DALY', 'DALY rate per 100 000 population'])
```

* Por último, se crea un nuevo csv después de ejecutar todo el jupyter notebook, el cual utilizaremos para crear el dashboard.

```python
heart_df.to_csv('heart_procesado.csv',  index=False)
```


### Datos procesados
* Base de datos procesado [dataset procesado](https://freddy120.github.io/heartfailure_vys/files/heart_procesado.csv)
