# granting-of-credit


## Creating a credit granting model

![concessão-de-crédito](https://user-images.githubusercontent.com/72039442/213340033-fc0f04c2-634b-41c3-a34a-a62efa9ce055.png)

# 1. Problema de negócio

A concessão de crédito é uma etapa que precisa ser muito assertiva, ou seja, o crédito precisa ser concedido para pessoas com maior probabilidade de quitar o empréstimo.

Para isso, é necessário um projeto onde seja realizada a análise combinada com a construção de um modelo de avaliação de crédito treinado e supervisionado de diversos casos de concessão.

# 2. Estratégia de solução

1. Questão de negócios:
    - Construção de um modelo de concessão de crédito

2. Entendendo o negócio:
    - O nosso cliente está a precisar de um modelo de concessão para ser avaliado a possibilidade de concessão de crédito a possíveis clientes novos no seu negócio

3. Coleta de dados
    - Dado pelo cliente

4. Limpeza de dados
    - Descrição dos dados
      - Saber o tamanho do problema que estamos enfrentando
    - Engenharia de recursos
      - Criar novas variáveis a partir dos originais, buscando uma melhor visualização das mesmas
    - Filtragem de variáveis
      - Filtrar variáveis com base no viés do negócio (dados que não podem ser utilizados pela empresa em geral, dados que não estarão disponíveis no momento da previsão,...)
      - Isso influencia como vamos modelar o algoritmo

5. Análise exploratória de dados (EDA)
    - Entender o negócio do ponto de vista dos dados
    - Criar um domínio sobre o problema, através de plots e hipóteses, de quais variáveis seriam importantes para o aprendizado do modelo 
    - Gerar insights, causando até uma possível quebra de crenças em outras pessoas que estão inseridas no problema em questão

6. Modelagem de dados
    - Separamos os dados, mas agora precisamos preparar os dados para os modelos de aprendizado de máquina
        - Codificação de variáveis categóricas e numéricas
    - Seleção de recursos usando algum algoritmo de ML, neste projeto foi SelectFromModel do sklearn
        - Vemos a influência da variável dependente com a resposta

7. Algoritmos de aprendizado de máquina
    - Implementamos inicialmente 1 algoritmo de baseline, 3 não lineares (Naive, Random forest, XGBoost, MLP)
    - Analisamos o erro do ponto de vista do desempenho do modelo
        - Olhando as métricas de acurácia, precisão, recall. f1-score e a matriz de confusão


# 3. Os 3 principais insights dos dados
  1. Mulheres são mais boas pagadoras do que homens?
     - Verdadeiro, o conjunto de dados mostra que, em percentual, as mulheres foram classificadas mais como boas pagadoras

  2. Pessoas mais jovens são mais mal pagadoras?
     - Verdadeiro, o nosso conjunto mostra que geralmente pessoas mais jovens são mais classificadas como mais mal pagadoras

  3. Tem algum estado que as pessoas pagam muito mais mal que nos outros?
     - Sim, o Amapá paga ligeramente mais mal do que os outros estados em nosso problema

# 4. Modelos de aprendizado de máquina aplicados
  Os testes foram feitos usando diferentes algoritmos.

# 5. Desempenho dos modelos de aprendizado de máquina
  O algoritmo XGBoostClassifier foi escolhido como o modelo de classificação binária, onde criou um treinamento mais longo para melhorar sua capacidade de generalização.
  
  Ele conseguiu uma marca 1478 true positives, onde melhorou 3 vezes o que tínhamos vencido no primeiro treinamento do modelo


# 6. Resultados de Negócios
  Conseguimos uma equiparação na performance na política escolhida pelo cliente, com um treinamento mais refinado, facilmente ultrapassaremos a dívida do cliente na concessão de crédito

# 7. Próximos passos para melhorar
 Treinar com mais n_estimators a XGBoost, pois, a partir dos experimentos, ela foi mais generalista quando completava o treinamento com o valor mais alto desse hiperparametro, no entanto, precisa de mais CPU com mais threads/cores para isso
 
 Validar scores no conjunto oot
 
 Testar distribuições diferentes para mitigar o efeito dos falsos positivos

