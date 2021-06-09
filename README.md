# Projeto-Final-ShePY
##ANÁLISE DE DADOS DE REAL TIME PCR (RT-PCR) UTILIZANDO PYTHON
Células são as unidades que formam todos os seres vivos. Existem milhares de tipos de células diferentes e essa diferença se dá principalmente pelas proteínas que a células tem. Essas proteínas são determinadas a partir do genoma da célula, ou seja, do DNA.

A partir do DNA são transcritos os RNAs, que são mensageiros que levam a informação do DNA até os ribossomos, que fazem a tradução desse RNA em proteínas.

O RT-PCR mede o quanto do RNA de um gene específico nós temos na célula. Isso o torna uma ferramenta poderosa em toda a área de ciências da saúde. Utilizando o RT-PCR é possivel verificar nível de infecção de células ou tecidos (COVID-19, HIV) verificar a expressão de genes associados ao câncer ou ainda determinar um tipo celular.

Infelizmente, o processo de análise do RT-PCR é um pouco trabalhoso visto que os dados são gerados em excel e que mais de uma análise é necessária.
#Sobre o Dataset e qPCR
O Dataset análisado foi obtido a partir de uma corrida de RT-PCR realizada em 2017, onde queríamos verificar a expressão de alguns RNAs mensageiros que codificam miosinas.

O Dataset contem 3 sheets de excel, utilizamos apenas a sheet "Results" para análise, pois é ela que contém os resultados da corrida, dados em CT (threshold cycle), que é o ciclo onde a fluorescencia começa a ser observada. Quanto mais cedo essa fluorescencia é detectada pelo aparelho, menor será o CT, e quanto menor o CT mais mRNA específico do gene nós temos.

Além dos CTs do gene de interesse nós também analisamos um gene housekeeping que tem a expressão padrão na célula independente do tratamento que será realizado nela. 

Assim, utilizei o python para as seguintes análises do dataset:

**Duplicatas**: quando fazemos o qPCR, sempre colocamos poços duplicados, os poços duplicados tem que ter o CT parecido, se não é sinal de que algo deu errado durante a execução do experimento e ele precisa ser repetido. Para essa analise, plotei um gráfico de barras (utilizando o seaborn e matplotlib) com uma barra indicando o desvio padrão das duplicatas.

**Expressão gene Housekeeping**: Para analisar se a expressão do housekeeping era constante entre as amostras, codei um boxplot onde conseguiria ver os outliers 

**Expressão gênica**: Para analisar a expressão gênica das miosinas, criei um novo dataframe com as informações do deltaCT (expressão do gene de interesse comparado ao gene housekeeping) e plotei gráficos analisando a expressão gênica de cada gene de interesse.
