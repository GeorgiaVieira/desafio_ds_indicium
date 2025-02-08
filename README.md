# Desafio Cientista de Dados Indicium!

## 1 - EDA ( EDA.ipynb)
A EDA está no arquivo EDA.ipynb. Nela explorei algumas visões e distribuíções, principalmente focadas nas visões relacionadas ao bairro. Uma coisa interessante, é que notei que lugares perto das torres gêmeas e do central park possuem os valores mais altos

## 3 - Modelagem (model.ipynb)
Optei por usar uma regressão linear do sktlearn uma RandomForestRegression para gerar os modelos. Gerei os modelos considerando primeiro o bairro_group, depois utilizei o bairro para comparar ambos. Utilizar o bairro resultou em um modelo melhor, mas parece que entre o random forest e a regressão linear a diferença não foi tão grande. Salvei o modelo por bairro tanto da regressão linear quanto do random forest nos arquivos modelo_linear_regression.pkl, modelo_random_forest.pkl respectivamente

Passos:

1. Carreguei os dados;
2. Retirei os valores nulos, pois eles impactam na regressão linear
3. Suavizei os outliers aplicando uma função log, assim os valores ficam mais suaves para construção de uma reta
4. Selecionei as features bairro e room type, precisei transformar elas em variáveis numéricas e utilizei para isso a função get_dummies do pandas
5. Separei os dados entre treino e teste, reservando 80% para o treino e 20% para teste
6. Treinei os modelos
7. Testei os modelos e calculei métricas. Escolhi MAE, RMSE e R²

## 2a - Sugerindo compras de imóveis (model.ipynb)
Considerando que essa base de anúncios possuí só o valor de preços do anúncios, não consigo garantir quantos dias eles estão alocados por mês. Também não sei se o valor do anúncio é por dia ou se é pelo período total da disponibilidade minima. Ainda assim, apesar de ingênua, vou considerar o seguinte:

## 2b)-  Correlação das variáveis mínimo de noites e a disponibilidade em relação ao preço (model.ipynb)
As variáveis de forma indenpendente não parecem afetar tanto o preço final do anúncio

## 2c - Existe algum padrão no texto do nome do local para lugares de mais alto valor? (model.ipynb)
Por conta do tempo, não fiquei segura das explorações que fiz e dos métodos que escolhi pra tentar ver alguma relação entre o padrão do texto e locais de mais alto valor. Vi algumas formas usando tokenização com uma biblioteca chamada word2vec, mas não consegui entender o suficiente para poder interpretar

- O tamanho médio dos aluguéis sejam próximos em cada bairro group
- Os anúncios são alocados com uma mesma frequência

#### Então, pesquisei o preço do metro quadrado na internet e farei a seguinte recomendação: (model.ipynb)
- Preço metro quadrado Manhattan: https://rocket.com/homes/market-reports/ny/manhattan
- Preço metro quadrado Brooklyn: https://rocket.com/homes/market-reports/ny/brooklyn
- Preço metro quadrado Queens: https://rocket.com/homes/market-reports/ny/queens
- Preço metro quadrado Bronx: https://rocket.com/homes/market-reports/ny/bronx
- Preço metro quadrado Staten Island: https://rocket.com/homes/market-reports/ny/staten-island

## A partir do preço médio de cada bairro group, qual seria o valor se eu dividisse pelo preço médio do metro quadrado? Ou seja, qual é o maior preço de aluguel por metro quadrado entre os bairro groups?
### Eu recomendaria comprar no Bronx!

## 4)-  Prevendo preços (model.ipynb)
Com o modelo gerado, incluí o novo dado aos dados de treino para gerar as mesmas features que as originais. O registro fornecido teve um valor previsto de 255.60 dólares que é bem próximo do valor original de 250. Vi que o registro já estava nos dados originais!


### Para instalar as dependências execute o comando:

pip install -r requirements.txt