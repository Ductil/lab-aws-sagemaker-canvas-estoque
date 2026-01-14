## 📊 Previsão de Estoque Inteligente na AWS com SageMaker Canvas

Este projeto faz parte do Bootcamp Nexa - Machine Learning e GenAI na Prática da DIO. O desafio consiste em utilizar o Amazon SageMaker Canvas para criar previsões de estoque baseadas em Machine Learning (ML), sem necessidade de codificação.

Autor: Gustavo de Oliveira Lima


## 🎯 Objetivos Deste Desafio de Projeto (Lab)

![image](https://github.com/digitalinnovationone/lab-aws-sagemaker-canvas-estoque/assets/730492/72f5c21f-5562-491e-aa42-2885a3184650)

O SageMaker Canvas é uma ferramenta poderosa que permite realizar todo o processamento de dados e construção de modelos de ML sem escrever código. Apesar de ser uma solução no‑code, é fundamental compreender os conceitos de datasets, métricas de avaliação e análise de variáveis para interpretar corretamente os resultados.

Neste projeto, o objetivo foi:

- Criar um modelo de previsão de estoque para uma empresa fictícia de fardamentos.
- Analisar as métricas de desempenho do modelo.
- Identificar as variáveis que mais influenciam a previsão.
- Gerar previsões de demanda para apoiar decisões de reposição de estoque.


## 🚀 Passo a Passo

1. Selecionar Dataset
   
O dataset utilizado foi construído de forma fictícia, simulando vendas de fardamentos em diferentes localidades da Bahia.

Colunas do dataset:
- Data (sequencial a partir de 2025-01-01)
- Produto (Uniforme Escolar, Jaleco Hospitalar, Camisa Corporativa, Macacão Industrial)
- Categoria (Escolar, Hospitalar, Corporativo, Industrial)
- Cliente (colégios, hospitais, empresas e indústrias fictícias)
- Quantidade Vendida (5–50 peças/dia)
- Estoque Atual (saldo após movimentação)
- Preço Unitário (R$ 89,90  R$ 99,90  R$ 129,90  R$ 149,90)
- Localização (Salvador, Feira de Santana, Camaçari, Lauro de Freitas, Vitória da Conquista, Ilhéus, Itabuna, Jequié)
  
📎 Arquivo utilizado no Canvas:
datasets/fardamentos_1000_registros.csv (1000 linhas de dados + header).

2. Construir/Treinar
   
No SageMaker Canvas, o dataset foi importado e configurado para prever a coluna alvo Quantidade Vendida.
O Canvas sugeriu um modelo de regressão numérica, adequado para prever valores contínuos.

3. Analisar
   
Após o treinamento, foram obtidas as seguintes métricas:
- RMSE: 13.547
- MSE: 183.520
Impacto das variáveis no modelo:
- Data – 46.2%
- Estoque Atual – 18.6%
- Localização – 13.2%
- Produto – 10.9%
  
📌 Insight: A sazonalidade (datas) e o nível de estoque são os maiores influenciadores da demanda. Localização e tipo de produto também têm relevância significativa.

4. Prever
   
Com o modelo ajustado, foi possível gerar previsões de vendas futuras para cada produto e região.
Essas previsões podem ser usadas para:
- Planejar reposição de estoque.
- Antecipar compras de matéria‑prima.
- Ajustar estratégias comerciais em períodos de maior demanda (ex.: início do ano escolar).
📎 Evidências geradas:
- Dataset usado: datasets/fardamentos_1000_registros.csv
- Resultado exportado de previsão: reports/previsoes.csv
- Print do resultado: reports/model_results.png

## 📈 Conclusão

O modelo de previsão de estoque inteligente mostrou boa capacidade de identificar padrões de demanda. A análise revelou que datas e estoque atual são os principais fatores que influenciam as vendas de fardamentos, seguidos por localização e tipo de produto.

Esse projeto demonstra como o SageMaker Canvas pode ser aplicado em cenários reais de gestão de estoque, mesmo sem conhecimento avançado em programação.
