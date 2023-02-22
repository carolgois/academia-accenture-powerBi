# academia-accenture-powerBi
Projeto desenvolvido na Academia Mulheres em Tech Data Engineer - Azure

## 1. Importar a biblioteca pandas e criar o dataframe a partir do arquivo cadastro_clientes.csv
~~~python
import pandas as pd
df = pd.read_csv(r"C:\Users\carol\cadastro_clientes.csv")
~~~

## Imagem do dataframe no Power Query
![dataframe](https://github.com/carolgois/academia-accenture-powerBi/blob/main/dataframe1.png)

## 2. Transformação dos dados
### 2.1. Converter os valores da coluna 'id' para números
~~~python
df['id'] = pd.to_numeric(df['id'])
~~~

### 2.2. Separar o Estado e a Cidade da coluna 'local' em duas colunas e deletar a coluna 'local'
~~~python
df[['estado','cidade']] = df['local'].apply(lambda x: pd.Series(str(x).split(" - ")))
df = df.drop(columns=['local']) 
~~~

## Imagem do dataframe no Power Query
![dataframe](https://github.com/carolgois/academia-accenture-powerBi/blob/main/dataframe2.png)

### 2.3. Criar as colunas 'idade' e 'faixa etaria' no Power Query
![dataframe](https://github.com/carolgois/academia-accenture-powerBi/blob/main/dataframe3.png)

## Visualização dos dados
### 3.1 Criar dashboard no Power BI contendo:
- Distribuição dos clientes por estado (ao passar o cursor sobre o estado no mapa é possível visualizar o número de clientes cadastrados daquele estado)
- Distribuição dos clientes cadastrados por faixa etária
- Proporção de clientes do sexo masculino e sexo feminino

## Imagem do dashboard no Power BI
![dataframe](https://github.com/carolgois/academia-accenture-powerBi/blob/main/dashboard.png)
