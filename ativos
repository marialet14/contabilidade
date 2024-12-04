import pandas as pd
import numpy as np
from scipy.stats import gmean

urlpetr = r"C:\Users\maria\Downloads\PETR4 - Página1.csv"
urlvale = r"C:\Users\maria\Downloads\VALE3.SA - Página1.csv"

df1 = pd.read_csv(urlpetr, encoding="latin1")
df2 = pd.read_csv(urlvale, encoding="latin1")


print("Dados de PETR4:")
print(df1.head())
print("\nDados de VALE3:")
print(df2.head())

df1["Fechamento ajustado**"] = df1["Fechamento ajustado**"].replace({",": ".", "R$": "", "%": ""}, regex=True)
df1["Abertura"] = df1["Abertura"].replace({",": "."}, regex=True)
df1["Alto"] = df1["Alto"].replace({",": "."}, regex=True)
df1["Baixo"] = df1["Baixo"].replace({",": "."}, regex=True)
df2["Fechamento ajustado**"] = df2["Fechamento ajustado**"].replace({",": ".", "R$": "", "%": ""}, regex=True)
df2["Abertura"] = df2["Abertura"].replace({",": "."}, regex=True)
df2["Alto"] = df2["Alto"].replace({",": "."}, regex=True)
df2["Baixo"] = df2["Baixo"].replace({",": "."}, regex=True)


df1["Fechamento ajustado**"] = pd.to_numeric(df1["Fechamento ajustado**"], errors="coerce")
df1["Abertura"] = pd.to_numeric(df1["Abertura"], errors="coerce")
df1["Alto"] = pd.to_numeric(df1["Alto"], errors="coerce")
df1["Baixo"] = pd.to_numeric(df1["Baixo"], errors="coerce")
df2["Fechamento ajustado**"] = pd.to_numeric(df2["Fechamento ajustado**"], errors="coerce")
df2["Abertura"] = pd.to_numeric(df2["Abertura"], errors="coerce")
df2["Alto"] = pd.to_numeric(df2["Alto"], errors="coerce")
df2["Baixo"] = pd.to_numeric(df2["Baixo"], errors="coerce")



fech1 = df1["Fechamento ajustado**"].dropna()
fech2 = df2["Fechamento ajustado**"].dropna()


media1 = fech1.mean()
media2 = fech2.mean()


print(f"Média aritmética PETR4: {media1:.2f}")
print(f"Média aritmética VALE3: {media2:.2f}")

media_geom1 = gmean(fech1)
media_geom2 = gmean(fech2)


print(f"Média geométrica PETR4: {media_geom1:.2f}")
print(f"Média geométrica VALE3: {media_geom2:.2f}")


variancia1 = df1["Fechamento ajustado**"].var()
variancia2 = df2["Fechamento ajustado**"].var()

print(f"Variância PETR4: {variancia1:.2f}")
print(f"Variância VALE3: {variancia2:.2f}")


desvio_padrao1 = fech1.std()
desvio_padrao2 = fech2.std()

print(f"Desvio padrão PETR4: {desvio_padrao1:.2f}")
print(f"Desvio padrão VALE3: {desvio_padrao2:.2f}")


covariancia = df1["Fechamento ajustado**"].cov(df2["Fechamento ajustado**"])


print(f"Covariância entre PETR4 e VALE3: {covariancia:.2f}")


cv1 = (desvio_padrao1 / media1) * 100

cv2 = (desvio_padrao2 / media2) * 100

print(f"Coeficiente de variação PETR4: {cv1:.2f}%")

print(f"Coeficiente de variação VALE3: {cv2:.2f}%")



correl1af = df1["Abertura"].corr(df1["Fechamento ajustado**"])
print(f"1 - Correlação entre Abertura e Fechamento da PETR4: {correl1af:.2f}")

correl1alf = df1["Alto"].corr(df1["Fechamento ajustado**"])
print(f"2 - Correlação entre Alto e Fechamento da PETR4: {correl1alf:.2f}")

correl1bf = df1["Baixo"].corr(df1["Fechamento ajustado**"])
print(f"3 - Correlação entre Baixo e Fechamento da PETR4: {correl1bf:.2f}")

correl2af = df2["Abertura"].corr(df2["Fechamento ajustado**"])
print(f"1 - Correlação entre Abertura e Fechamento da VALE3: {correl2af:.2f}")

correl2alf = df2["Alto"].corr(df2["Fechamento ajustado**"])
print(f"2 - Correlação entre Alto e Fechamento da VALE3: {correl2alf:.2f}")

correl2bf = df2["Baixo"].corr(df2["Fechamento ajustado**"])
print(f"3 - Correlação entre Baixo e Fechamento da VALE3: {correl2bf:.2f}")

correlacao_empresas = df1["Fechamento ajustado**"].corr(df2["Fechamento ajustado**"])

print(f"Correlação entre o fechamento de PETR4 e VALE3: {correlacao_empresas:.2f}")
