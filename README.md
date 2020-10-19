# Streamlit-lab1-
Algoritmic digital marketing - lab 1
Streamlit

Summary
Here we will try to understand how to use Streamlit on a very basic level
Author
Jugal Sheth



Add Headings (Format > Paragraph styles) and they will be displayed in your table of contents.

Streamlit intro:
"Streamlit is an open-source python based app framework and is the easiest way for data scientists and machine learning engineers to create beautiful, performant apps in only a few hours! All in pure Python. All for free!"
It is a tool to create Web-based front ends with a focus for the Machine Learning scientist or engineer.
Specifically, Streamlit uses HTML, CSS, and Javascript but does not need the developer to know HTML, CSS, and Javascript.
The Streamlit team is enabling the Data scientists to deploy their models without using Flask, Django, or other tools.
PS - It is not a replacement for Flask or FastAPI.




How to install and start
Make sure that you have Python 3.6 or greater installed.
#Check your python version with the below command
Python --version

#pip install streamlit

I have already installed so requirements satisfied

#Run hello*
Streamlit hello



Example
#code
import streamlit as st
import os 
import pandas as pd


os.chdir('C:/Users/jugal/OneDrive/Desktop/Courses neu/Algorithmic dm/Lab 1')#your directory

st.title('Heart Disease Diagnosis Assistant')
st.markdown('This application is meant to **_assist_ _doctors_ _in_ diagnosing**, if a patient has a **_Heart_ _Disease_ _or_ not** using few details about their health')


df = pd.read_csv('heart.csv')

if st.checkbox('Show me Training Data'):
        st.dataframe(df)

st.markdown('Please **Enter _the_ _below_ details** to know the results -')

age = st.text_input(label='Age')

gender_ls = ['Male', 'Female']
sex = st.selectbox('Gender', gender_ls)

cp_ls = ['Typical Angina', 'Atypical Angina', 'Non-anginal pain', 'Asymptomatic']
cp = st.multiselect('Chest pain Type', cp_ls)

restbp = st.slider('Resting Blood Pressure', 0, 220, 120)

chol = st.slider('Serum Cholesterol in mg/dl', 0, 600, 150)

fbs_ls = ['fasting blood sugar > 120 mg/dl', 'fasting blood sugar < 120 mg/dl']
fbs = st.selectbox('Fasting Blood Sugar (>126 mg/dL signals diabetes)', fbs_ls)



if st.button('Check Diagnosis'):

        st.header('A Machine Learning Model would predict this') 
#to run it, type this in the command prompt after giving your directory

Streamlit run app.py 


