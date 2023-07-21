# [Portal de Dados Abertos da CVM](https://dados.cvm.gov.br/)
## Downloads de todos os dados dos Fundos de Investimento Brasileiros da base de dados da CVM.

Este repositório contém um código em Python para criar um banco de dados de cotações de fundos de investimento brasileiros utilizando dados disponíveis no site da Comissão de Valores Mobiliários (CVM).

## Objetivo

O objetivo deste projeto é coletar e unificar dados de cotações de fundos de investimento brasileiros de diferentes anos em um único banco de dados. O código foi desenvolvido utilizando a biblioteca pandas para manipulação dos dados e requests para a extração dos dados da CVM.

## Passo a Passo

1. Coleta dos Dados:
   - Os dados de cotações dos fundos de investimento brasileiros foram extraídos do site da CVM, usando a biblioteca `requests` e `zipfile`.
   - Os arquivos estão disponíveis nos links:
      - Para os anos de 2000 a 2004 é necessario apenas adicionar o ano ao link.
           https://dados.cvm.gov.br/dados/FI/DOC/INF_DIARIO/DADOS/HIST/inf_diario_fi_ano.zip 
      - Para os anos de 2005 a 2020 é necessario adicionar o ano e o mês ao link.       
           https://dados.cvm.gov.br/dados/FI/DOC/INF_DIARIO/DADOS/HIST/inf_diario_fi_ano-mes.zip
      - A partir de 2021 é necessario adicionar o ano e o mês ao link.
           https://dados.cvm.gov.br/dados/FI/DOC/INF_DIARIO/DADOS/inf_diario_fi_ano-mes.zip

2. Concatenação dos Dados:
   - Os dados de cada ano/mês são lidos e concatenados em um único DataFrame utilizando a função `pd.concat()`.

3. Tratamento dos Dados Cadastrais:
   - Os dados cadastrais dos fundos de investimento também foram obtidos do site da CVM e carregados em um DataFrame.
   - Foram removidos os CNPJs duplicados para obter apenas as informações mais atualizadas de cada fundo.

4. Criação do Banco de Dados:
   - Os dataframes com os dados de cotações e informações cadastrais foram combinados em um único dataframe utilizando a função `merge()` do pandas. Obtidas do seguinte ink:
        https://dados.cvm.gov.br/dataset/fi-cad

**AVISO: O banco de dados gerado é muito grande e a execução do código pode levar várias horas. Recomendamos que, para análises mais rápidas e eficientes, você utilize um banco de dados em SQL para manipular os dados dos fundos de investimento.**
