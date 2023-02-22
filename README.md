# academia-accenture-powerBi
Projeto desenvolvido na Academia Mulheres em Tech Data Engineer - Azure

## Importar a biblioteca pandas e criar o dataframe a partir do arquivo cadastro_clientes.csv
~~~python
import pandas as pd
df = pd.read_csv(r"C:\Users\carol\OneDrive\Área de trabalho\Gama\Desafio\academia-accenture-powerBi\cadastro_clientes.csv")
~~~
## Imagem do dataframe no PowerQuery
![dataframe][dataframe1.png]

## Transformação dos dados
### Converter os valores da coluna 'id' para números
~~~python
df['id'] = pd.to_numeric(df['id'])
~~~
### Separar o Estado e a Cidade da coluna 'local' em duas colunas e deletar a coluna 'local'
~~~python
df[['estado','cidade']] = df['local'].apply(lambda x: pd.Series(str(x).split(" - ")))
df = df.drop(columns=['local']) 
~~~
## Imagem do dataframe no PowerQuery
![dataframe][dataframe2.png]
