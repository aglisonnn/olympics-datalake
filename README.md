# 🏅 Olympics Data Lake

Este repositório contém um Data Lake local construído para consolidar e analisar dados históricos das Olimpíadas (desde 1896) e os resultados recentes dos Jogos de Paris 2024. O projeto segue os princípios da **Arquitetura Medalhão** (Raw, Bronze, Gold).

## 🗂️ Estrutura do Data Lake

A organização dos diretórios segue a divisão por camadas de maturidade dos dados:

- **`raw/`**: Contém os arquivos originais (CSVs) extraídos das fontes (Kaggle/Olympedia e COI), além de seus respectivos arquivos de metadados em JSON.
- **`bronze/`**: Dados brutos convertidos para o formato otimizado `Parquet`. Inclui também a base de dados integrada (`medalhas_1986_2024.parquet`) gerada a partir da união do histórico com os dados de 2024.
- **`gold/`**: Camada de consumo. Contém agregações finais, análises e visualizações. Em `analise_medalhas/` temos o quadro geral de todos os tempos, o Jupyter Notebook com o pipeline ETl e os gráficos gerados.

## 📄 Metadados

Todos os datasets do Data Lake estão documentados. Na raiz do projeto, encontra-se o `metadata_schema.json`, que define o padrão (schema) utilizado para descrever os dados em todas as camadas.

## 🛠️ Tecnologias Utilizadas

- **Python**: Linguagem principal para o pipeline de dados.
- **Pandas & PyArrow**: Para leitura, integração (JOINs/Appends) e conversão para formato Parquet.
- **Matplotlib**: Para a geração de visualizações gráficas.
- **Jupyter Notebook**: Para o desenvolvimento interativo do código.

## 🚀 Como executar o Pipeline

1. Clone este repositório.
2. Certifique-se de ter as bibliotecas instaladas: `pip install pandas pyarrow matplotlib`
3. Navegue até `gold/analise_medalhas/` e execute as células do arquivo `notebook.ipynb`.
