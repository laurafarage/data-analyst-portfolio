Welcome to my data analyst portfolio, showcasing diverse projects in diffent areas. Each project highlights my skills in data cleaning, analysis, and visualization. Explore to see how I transform data into actionable insights across various domains.


# Project 1

In this project, we will embark on a comprehensive journey through a healthcare dataset, meticulously cleaning and refining the data to ensure accuracy and relevance. Our focus will be on extracting and synthesizing key insights that drive meaningful conclusions. The final deliverable will feature clear and compelling data visualizations that effectively communicate these insights, aiding decision-making and enhancing understanding.


# 1) DATA VALIDATION
![image](https://github.com/user-attachments/assets/f3d1d70b-25a8-42d7-9031-d0fdb87e7113)

   
# 2) DATA CLEANING 

Tools: Python - Google Colab

Como estava o dataframe:
![image](https://github.com/user-attachments/assets/7b0065b1-3e2e-46b7-add0-472b09e0d83d)

##CÓDIGO##

#Imports

import pandas as pd

import math as mt

import statistics as st

from datetime import datetime


___________________________________________

#Importar e ler o dataframe

df = pd.read_csv('healthcare_dataset.csv')

print(df.dtypes)

___________________________________________

#Aplicar a transformação na coluna 'Name'

df['Name'] = df['Name'].str.title()

df.to_csv('healthcare_dataset1.csv', index=False)

___________________________________________


#Código para separar as idades em grupos

#Definir os grupos de idade

bins = range(0, 105, 15) 

#Definir os rótulos para os grupos

labels = [f'{i}-{i+14}' for i in bins[:-1]]

df['Age Group'] = pd.cut(df['Age'], bins=bins, labels=labels, right=False)

df.to_csv('healthcare_dataset1.csv', index=False)


___________________________________________


#Distribuição de frequência da condição médica

#Contar a frequência de cada valor único na coluna 'Medical Condition'

freq_distribution = df['Medical Condition'].value_counts().sort_index()

#Exibir a distribuição de frequência

print(freq_distribution)

![image](https://github.com/user-attachments/assets/54b59d05-f9a2-410b-988a-268806e26931)

___________________________________________


#Converter a coluna para datetime, ignorando erros

df['Date of Admission'] = pd.to_datetime(df['Date of Admission'], errors='coerce')
df['Discharge Date'] = pd.to_datetime(df['Discharge Date'], errors='coerce')

#Definindo a coluna Tempo de Internação

df['Tempo de Internação'] = df['Discharge Date'] - df['Date of Admission']
df.to_csv('healthcare_dataset1.csv', index=False)
df.head()

#Mudando os formatos de data para dd/mm/aa

df['Date of Admission'] = df['Date of Admission'].dt.strftime('%d/%m/%y')
df['Discharge Date'] = df['Discharge Date'].dt.strftime('%d/%m/%y')

df.to_csv('healthcare_dataset1.csv', index=False)

___________________________________________

Como ficou o dataframe:
![image](https://github.com/user-attachments/assets/65141850-f736-4559-be18-6a082f382710)




# 3) DATA VISUALIZATION

Tools:

Objectives:
