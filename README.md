# Analisis de datos
---------------------------------
## Ejercicio de analisis de datos
#### Este ejercico de analisis de datos fue desarrollado durante el curso de python impartido por samsung innovation campus.
#### Indicaciones:
 -  Obtenga la fecha en la que se ejecuta el script.Para ambos archivos.
 
 -  Cree un DataFrame para cada escuela, con el formato de nombre “nombrecolegio_curso” que reúna los datos de las columnas:  `school, sex, age, address, Pstatus, guardian, traveltime, studytime, failures, paid, internet, health, absences, G1, G2, G3.`.
 
 -  Verifique que no haya data de valor nulo `(NaN)`, en caso de encontrar algún valor `NaN` se deberá eliminar toda la fila.
 
 -  Para cada escuela muestre un gráfico circular **(pastel)**  donde se evidencie el porcentaje de estudiantes hombres y mujeres de cada curso.
 
 -  Para cada escuela muestre un gráfico de barras donde se muestre la cantidad de estudiantes que tienen la misma edad.
 
 - Muestre el promedio de las edades de cada curso de cada escuela
 
 - Muestre el promedio de las notas `G1, G2, G3` de cada curso de cada escuela
 
 - Grafique el promedio de las notas en un gráfico de barras horizontal

- Halle el valor máximo de las ausencias y considere dicho valor como el total de clases del curso, de manera que pueda sacar un porcentaje de asistencia para cada estudiante
 
 - Cree una nueva columna llamada __“extra”__
 
 - Cree una nueva columna llamada __“approved”__ en la cual determine si el estudiante aprueba o reprueba el curso (1 para aprueba, 0 para reprueba), considerando:
     - Si el estudiante tiene un porcentaje de asistencia menor al 80% del curso reprueba 
     -	Si el estudiante tiene un porcentaje de asistencia mayor al 80% del curso, pero la nota `G3` es menor a **10** reprueba
     -	Si el estudiante tiene un porcentaje de asistencia mayor al 80% del curso, pero la nota `G3` está entre **10** y **15** aprueba y se asigna **1** a la columna extra
     -	Si el estudiante tiene un porcentaje de asistencia mayor al 80% del curso y la nota `G3` es mayor a **15** aprueba y se asigna **0** a la columna extra
  
  - Grafique el porcentaje de alumnos aprobados de cada curso
#### Resultado:
El resultado que se espera despues de realizar las operaciones es el siguiente.
1. Generar un archivo en formato csv con nombre: “Resultado + Fecha en la que se ejecuta el script”, este archivo debe quedar en la carpeta donde se encuentren los datos originales y el archivo de Python
2. Entregar en un archivo PDF todas las gráficas solicitadas
----------------------------------
# Resolucion
#### Importamos las librerias
```python 
import pandas as pd: #Importa la biblioteca Pandas y la renombra como pd.     
import numpy as np: #Importa la biblioteca NumPy y la renombra como np.    
import matplotlib.pyplot as plt: #Importa la biblioteca Matplotlib para generar gráficos y la renombra como plt.         
import time: #Importa la biblioteca Time para trabajar con fechas y horas.      
import statistics: #Importa la biblioteca Statistics para realizar cálculos e stadísticos.       
from IPython.display import display: #Importa la función display de IPython para mostrar resultados.    
```
----------------------------------
### Funciones
```python 
#-----Abrir csv-----:

def open_csv(file): #Define una función llamada open_csv que lee un archivo CSV utilizando la función pd.read_csv. Devuelve los datos leídos.
file y file2: #Nombres de los archivos CSV a leer.

#-----Eliminación de valores vacíos-----:

def valorvacio(data): #Define una función llamada valorvacio que elimina filas con valores vacíos utilizando la función dropna de Pandas. Devuelve los datos sin valores vacíos.

#Creación de dataframes:

df_mat y df_por: #Dataframes que contienen los datos leídos de los archivos CSV correspondientes, filtrando columnas específicas.
df_gabriel_pereira_mat y df_mousinho_da_silveira_mat: #Dataframes filtrados por la escuela Gabriel Pereira y el curso de matemáticas.
df_gabriel_pereira_por y df_mousinho_da_silveira_por: #Dataframes filtrados por la escuela Gabriel Pereira y el curso de portugués.

#-----Gráficas-----:

grafica_sexo(file, nombre): #Genera una gráfica de pastel que muestra la distribución de género de los estudiantes. Los datos se obtienen del dataframe pasado como argumento.
grafica_edades(file, nombre): #Genera una gráfica de barras que muestra la cantidad de estudiantes por edad. Los datos se obtienen del dataframe pasado como argumento.
grafica_sexo(file, nombre): #Genera una gráfica de barras horizontales que muestra el promedio de las notas G1, G2 y G3. Los datos se obtienen del dataframe pasado como argumento.
ausencias_grafica(file, nombre): #Genera una gráfica de pastel que muestra el porcentaje de estudiantes aprobados y reprobados en función de las ausencias. Los datos se obtienen del dataframe pasado como argumento.

#-----cálculos estadísticos-----:

promedio_edades(file, nombre): #Calcula el promedio de las edades de los estudiantes y lo imprime. Los datos se obtienen del dataframe pasado como argumento.
promedio_notas(file, nombre): #Calcula el promedio de las notas G1, G2 y G3 de los estudiantes y lo imprime. También genera una gráfica de barras horizontales con los promedios. Los datos se obtienen del dataframe pasado como argumento.
`
```
-------------------------
# Graficos
#### Estas son algunas de las graficas generadas:
##### Grafica De Sexo mousinho da silveira matematicas   
 <img src="https://github.com/raul2811/Analisis-de-datos-ejercicio/blob/main/Graficas/Grafica_De_Sexo_mousinho_da_silveira_mat.png" alt="Grafica_De_Sexo_mousinho_da_silveira_mat" width="500"/>    

##### Grafica De cantidad de estudiantes que tienen la misma edad mousinho da silveira matematicas      
 <img src="https://github.com/raul2811/Analisis-de-datos-ejercicio/blob/main/Graficas/Grafica_De_cantidad_de_estudiantes_que_tienen_la_misma_edad_mousinho_da_silveira_mat.png" alt="Grafica_De_Sexo_mousinho_da_silveira_mat" width="500"/>   

##### Grafica De promedio de las notas de G1 G2 G3 mousinho da silveira matematicas         
 <img src="https://github.com/raul2811/Analisis-de-datos-ejercicio/blob/main/Graficas/Grafica_De_promedio_de_las_notas_de_G1_G2_G3_mousinho_da_silveira_mat.png" alt="Grafica_De_Sexo_mousinho_da_silveira_mat" width="500"/>    

-------------    
    
Por ultimo pasamos los datos limpios a un nuevo csv:
```python
variable=("student{}_resultado_.csv".format(nombre))
    csv.to_csv(variable,sep=";")
```
