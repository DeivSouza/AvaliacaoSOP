# AvaliacaoSOP
Avaliação de Sistemas Operacionais

Este repositório contém uma aplicação Streamlit para visualizar dados financeiros.

Clone o repositório > Adicione o dataset na pasta do projeto

Execute a aplicação: streamlit run app.py

-----------------------------------------

import streamlit as st
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("MS_FinancialSample.csv")

st.title("Análise Financeira")

st.write("Visualizando os dados:")
st.dataframe(df.head())

country_product_counts = df.groupby("Country")["Product"].count()

fig, ax = plt.subplots()
country_product_counts.plot(kind="bar", ax=ax)
ax.set_title("Quantidade de Produtos por País")
ax.set_xlabel("Country")
ax.set_ylabel("Quantidade de Produtos")

st.pyplot(fig)
