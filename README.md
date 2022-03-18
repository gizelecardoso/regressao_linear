## Regressão Linear

![Grafico Regressao](https://s.dicionariofinanceiro.com/imagens/normdist-regression.jpg)


Dentro da área de Aprendizado de Máquina, temos os modelos Supervisionados, que são modelos treinados com informações conhecidas e sabemos exatamente o que queremos de saída, com isso conseguimos prever valores a partir de dados conhecidos, e calcular o quão bom nosso modelos é comparando a saída do modelo com os dados que temos disponíveis.

A ideia sempre será tentar prever uma variável (y) chamada de variável dependente, a partir de uma ou mais variáveis (x's) chamadas de variáveis explicativas.

Importante na Regressão Linear, é que a variável dependente, precisa ser **QUANTITATIVA**, com isso estimaremos o valor de determinado conjunto de dados.

Equação Regressão Linear

$$
   y = \alpha + \beta.x1 + \epsilon
$$

Essa equação é para Regressão Linear Simples, onde tentamos prever **y** em razão de uma variável **x**


$$
   y = \alpha + \beta1.x1 + \beta2.x2 + ... + \beta k.x k + \epsilon
$$

Essa equação é para Regressão Linear Múltipla, onde tentamos prever **y** em razão de **k** variáveis **x**.

Dentro da equação temos algumas informações importantes:

* **Alfa** -> é chamado de **intercepto**, é o ponto que cruza o eixo y na reta, se não tiver nenhuma váriavel preditora o valor de **y** é o intercepto (talvez eu diria que é o valor padrão).

* **Beta** -> é chamado de **coeficiente de inclinação da reta**.

* **x** ->  já mencionado anteriormente são as **variáveis explicativas**.

* **u** -> é o termo de erro da equação. A ideia dele é que nossa reta da equação não conseguirá captar todos os pontos das observações, essa diferença do ponto e a reta é agregada nessa variável.

Com essa definição do erro, temos

$$
    erro = Y - Ŷ
$$

Ou seja, o erro é igual a diferença dos valores reais menos os valores previstos da variável dependente.

Com isso, para nosso modelo ser o mais preciso possível, precisamos minimizar essa diferença (erro)

* Condições Regressão:

    1. Somatória de erros igual a zero
    2. Somatória de erros ao quadrado a menor possível.

Com essas duas condições temos o que chamamos de: **OLS** ou **MQO**

___
- **O** ordinary 
- **L** least
- **S** squares
___
- **M** Mínimos
- **Q** Quadrados
- **O** Ordinarios
___

Tentando responder quais valores de alfa e beta minimizam o erro ao quadrado e garantem o erro igual a zero.

### Análises

Após rodarmos o modelo alguns outputs são usados para validar o quão bom o modelo é.

1. Coeficiente de Determinação (R²)

Esse coeficiente indica quanto do comportamento da variavel y é explicado pelas variáveis x. Com isso quanto maior o R² melhor será o modelo.
Coeficiente varia de 0 - 1.

2. Testes Estatísticos

    * Significância Estatística do Modelo - TESTE F de Snedecor
        <p> Objetivo desse teste é avaliar a significância estatística conjunta dos parâmetros, validando se pelo menos um dos betas é estatísticamente significante para explicar o comportamento de y.</p>
        <p> Nesse teste importante o DF (Degrees of Freedom) - (Graus de Liberdade), calculado pela diferença de quantidade de observaçoes (N) menos quantidade de parâmetros (k -> alfa e betas)</p>

        ![Grafico do Teste f](https://e7.pngegg.com/pngimages/830/362/png-clipart-f-distribution-f-test-percentile-statistics-test-statistic-others.png)

        Conforme o gráfico calcular o valor de modo,
        que F_calculado seja > F_critico ou p-valor < 0,05

        Nesse caso reijeitamos H0 (hipótese nula) de que não f estatísticamente diferente de zero a 95% de confiança.

        Ou seja, existe um beta estatisticamente significante.
        Se p-valor >= 0.05, não haveria modelo, pois nenhuma variável é estatisticamente significante para explicar o valor da variavel y.


    * Significância Estatística do Modelo - TESTE t de Student
        <p> Objetivo desse teste é avaliar a significância estatística de cada um dos parâmetros, validando se o parâmetro em questão é estatísticamente significante para explicar o comportamento de y.</p>
        <p>o gráfico desse teste mostra uma distribuição bicauldal</p>

        ![Grafico do Teste t](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7a/Teste_T_Gr%C3%A1fico_bicaudal_v2.png/300px-Teste_T_Gr%C3%A1fico_bicaudal_v2.png)

        Conforme o gráfico calcular o valor de modo,
        que F_calculado seja > F_critico ou p-valor < 0,025 (positivo e negativo)

        Nesse caso reijeitamos H0 (hipótese nula) de que não f estatísticamente diferente de zero a 95% de confiança.

        Ou seja, existe um beta estatisticamente significante.
        Se p-valor >= 0.05, não haveria modelo, pois nenhuma variável é estatisticamente significante para explicar o valor da variavel y.



