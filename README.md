# cognitivo-airbnb
Repositório para entrega do teste técnico - Cognitivo.ai

# Respostas

## a. Como foi a definição da sua estratégia de modelagem?

Segui as seguintes etapas:

1. Análise Exploratória de Dados
    - Valores Ausentes
    - Distribuição/Tipo das Variáveis
    - Análise de outliers
    - Correlações
2. Pré-processamento
    - Remoção de Outliers
    - Seleção de Atributos
    - Transformação de Atributos
3. Divisão Treino/Teste

4. Ajuste de Hiperparâmetros
    - Validação Cruzada
5. Treinamento e Validação do Modelo de Regressão

Comparei a performance de 3 modelos distintos:
- Regressão linear com expansão de base polinomial e regularização _ridge_
- Árvore de Decisão
- Multilayer Perceptron

## __b.__ Como foi definida a função de custo utilizada?


A função de custo da regressão linear é a função de mínimos quadrados lineares (__LLS__).

Para a árvore de decisão, foi utilizado a função do Erro Quadrático Médio (__MSE__).

Para a MLP, foi experimentado a função de custo __MSLE__. A __MSLE__ não penaliza tanto a presença de outliers quanto a __MSE__.

## __c.__ Qual foi o critério utilizado na seleção do modelo final?

Dentre os 3 modelos testados, quis englobar modelos que:
- Fossem capazes de capturar efeitos não-lineares
- Tivessem princípios de funcionamento não-correlacionados
- Fossem robustos a atributos irrelevantes

## __d.__ Qual foi o critério utilizado para validação do modelo? Por que escolheu utilizar este método?

O modelo foi avaliado em termos do __MSE__ e também pelo __MAE__ calculado no conjunto de testes.

Escolhi o __MAE__ por apresentar as mesmas unidades da variável alvo (__Reais__). Desta maneira, o resultado do erro é mais facilmente interpretável.

No caso da MLP, o modelo também foi avaliado com base no histórico de treinamento: Training loss vs Validation loss, para avaliar under/overfitting.

## __e.__ Quais evidências você possui de que seu modelo é suficientemente bom?

O __MAE__ nos dá uma boa indicação da performance do modelo. Os 3 modelos se equipararam, indicando que não há um erro de modelagem muito grande em qualquer um deles. No caso da __MLP__, foi avaliado o histórico de treinamento para verificação de overfitting. O erro apresentado muito provavelmente se dá a efeitos não capturados pelas variáveis de entrada.

Como expansão desta análise, poderíamos voltar à etapa de exploração para tentarmos extrair mais informação dos dados extraídos, e procurar mais fontes de dados para possivelmente enriquecer nossas variáveis de entrada.
