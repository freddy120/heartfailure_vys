---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---


## Proyecto Final
Este proyecto final del curso de  Visualización y storytelling de la Maestría en Inteligencia Analítica de Datos MIAD

Elaborado por: Freddy Mendoza Ticona, ...


### Recursos:
* Jupyter notebook del modelado de datos [notebook](https://github.com/freddy120/heartfailure_vys/blob/main/Proyecto_Final_VyS.ipynb) [![Foo](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/freddy120/heartfailure_vys/blob/main/Proyecto_Final_VyS.ipynb)
* Base de datos [dataset](https://www.kaggle.com/fedesoriano/heart-failure-prediction)
* Dashboard en google data studio [dashboard](https://datastudio.google.com/reporting/c5b2c862-0ce9-4b05-9fe3-7027ceb9c09b)


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

* Se descarga la basa de datos en formato csv del enlace.
* Se usa jupyter notebook para hacer el modelado, se puede usar colab para abrirlo.
* Se carga el archivo 'Ask A Manager Salary Survey 2021 (Responses) - Form Responses 1.csv’ en la ubicación del notebook para poder cargarlo con pandas.

```python
df = pd.read_csv('Ask A Manager Salary Survey 2021 (Responses) - Form Responses 1.csv', thousands=',')
df.head()
```



* Se realiza la traduccion del nombre de las variables.

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


### Dashboard
[google data studio](https://datastudio.google.com/reporting/c5b2c862-0ce9-4b05-9fe3-7027ceb9c09b)