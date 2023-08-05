# Análise de Dados PF e PJ (Número de Beneficiarios, Receita e Despesas)

Este projeto tem como objetivo analisar dados de beneficiários ativos para pessoas físicas (PF) e pessoas jurídicas (PJ) a partir de um conjunto de arquivos Excel mensais. O script Python processa os dados e cria uma planilha consolidada com informações sobre o número de beneficiários ativos, valor da receita e valor das despesas para cada mês e cada categoria (PF e PJ).

## Como usar

1. Certifique-se de ter o Python instalado em seu sistema.

2. Clone este repositório para o seu computador:
git clone https://github.com/seu-usuario/nome-do-repositorio.git

3. Coloque o arquivo `analitixa-pf.xlsx` na pasta do repositório.

4. Abra um terminal ou prompt de comando e navegue até o diretório do repositório.

5. Execute o script com o comando:
python script_analise_dados.py

6. A planilha consolidada será criada no arquivo `planilhas_analise_pf_pj.xlsx`.

## Trecho do Código

```python
import pandas as pd

def analisar_dados(df, pessoa):
 # Filtrar apenas os dados da pessoa (PF ou PJ)
 df_pessoa = df[df['PESSOA'] == pessoa]

 # Número de beneficiários ativos
 num_beneficiarios_ativos = df_pessoa[df_pessoa['SITUACAO'] == 'Ativo']['MATRICULA'].nunique()

 # Valor da receita
 valor_receita = df_pessoa[df_pessoa['SITUACAO'] == 'Ativo']['Mensalidade'].sum()

 # Valor das despesas
 valor_despesas = df_pessoa[df_pessoa['SITUACAO'] == 'Ativo']['Despesas'].sum()

 return num_beneficiarios_ativos, valor_receita, valor_despesas

Este trecho do código é responsável por analisar os dados filtrando apenas as informações relevantes para cada pessoa (PF ou PJ) e calculando o número de beneficiários ativos, valor da receita e valor das despesas.

Requisitos
Python 3.x
Pandas
Licença
Este projeto é licenciado sob a licença MIT - consulte o arquivo LICENSE para obter mais detalhes.

Lembre-se de substituir `seu-usuario` e `nome-do-repositorio` com suas informações corretas. Esse README.md foca na explicação do projeto e inclui um trecho do código para ilustrar a funcionalidade. Espero que isso seja útil para o seu portfólio no seu currículo!


