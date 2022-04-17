# hotel_cancellation
Análise de cancelamento de uma rede de hotéis

Divisão do notebook:
1) Introdução: descrição dos principais objetivos do notebook e de sua divisão, com respectivas análises

2) Setup Notebook: import das bibliotecas e do dataframe de analise

3) Consistency Check: entendimento dos dados e de possíveis inconsistências. Aqui, são análisadas inconsistências como valores dos hoteis nulos/gratuitos e estabelecimento de hipóteses para as variáveis ausentes. São realizadas, portanto, as seguintes análises:
- Entendimento inicial das colunas
- Tipologia das features e criação de novas variáveis de análise
- Valores ausentes e aprofundamento dos valores ausentes
- Valores nulos e negativos e aprofundamento de valores nulos
- Valores duplicados, aprofundamento e remoção de valores duplicados
- Estatística descritiva e correlação
- Distribuição univariada das features

4) Análise Exploratória dos Dados: análise bivariada para todas as variáveis independentes e a resposta, além de analises de consistência mais específicas, como a variação da taxa de cancelamento pelo tempo, utilizando conceitos de séries temporais, valor dos hoteis normais e de luxo e consistência dos dados de diarias durante a semana e o fim de semana. Resumindo as análises, tem-se a divisão:
- Análise bivariada variáveis explicativas vs resposta (densidade de probabilidade e proporção de cancelamentos)
- Demais análises de consistência

5) Modelagem: como forma de modelagem do problema, optou-se por rodar três modelos de árvores (decision tree, random forest e SGBoosting), mediante três iterações com feature engineering diferentes. A métrica de análise escolhida foi a AUC, de forma a balancear as classes positivas e negativas do modelo. As três iterações foram:
- 1ª iteração: geração do modelo com todas as features, sem tratamento previo (baseline)
- 2ª iteração: feature selection a partir do feature importance da própria árvore gerada na primeira iteração
- 3ª iteração: feature engineering e selection manuais
- Além disso, tem-se a consolidação do resultado final por meio do plot da ROC e o cálculo final da AUC da ROC. Teve-se, como resultado final, que a segunda iteração e o modelo do SGBoosting tiveram o melhor desempenho dentre os 9 ajustados.

6) Variação temporal para validação do modelo: é respondido a questão de validação cruzada tanto de forma qualitativa quanto quantitativa. Além disso, são efetuadas as seguintes análises:
- Analise da distribuição das variáveis de 2015 e 2016 vs 2017
- Análise do melhor modelo com a nova base de validação

7) Conclusão e Próximos Passos: resumo geral do que foi realizado e dos resultados obtidos, bem como sugestões de próximos passos das análises (novos algoritmos, testes etc.)