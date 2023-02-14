# Análise Exploratória, Limpeza e Transformações de Dados de Telecomunicações

Fonte de Dados: <a href ="https://www.kaggle.com/datasets/blastchar/telco-customer-churn">Telco Customer Churn<a>

Uma empresa de telecomunicações possui um grande volume de dados de clientes.

Neste projeto foi realizado:
* Drop de linhas e colunas por decisões de negócio e/ou por percentual de valores ausentes;
* Conversão de tipos de dados;
* Imputação em valores ausentes de variáveis categóricas;
* Imputação em valores ausentes por preenchimento progressivo e reverso;
* Substituição de outliers por valores de maximum e minimum.

## Relatorio de Entrega

O dataset originalmente possuia 150001 registros (linhas) com 55 variáveis (colunas).

O título das colunas 'Dur. (ms).1', 'Start ms' e 'End ms' foram renomeadas para 'Dur (ms), 'Start Offset (ms)' e 'End Offset (ms)' respectivamente, como o objetivo de manter um padrão de nomenclatura.

Existiam no dataset as colunas 'Dur (ms)' e 'Dur (s)' com o mesmo tipo de informação porém representadas com unidades de medida diferentes. Foi mantida apenas a coluna 'Dur (ms)' por possuir uma maior precisão de casas decimais.


### Tratamento de Valores Ausentes:

As colunas 'Nb of sec with 37500B < Vol UL', 'Nb of sec with 6250B < Vol UL < 37500B', 'Nb of sec with 125000B < Vol DL', 'Nb of sec with 31250B < Vol DL < 125000B', 'Nb of sec with 1250B < Vol UL < 6250B', 'Nb of sec with 6250B < Vol DL < 31250B', 'HTTP UL (Bytes)' e 'HTTP DL (Bytes)' foram removidas por possuirem mais de 30% de valores ausentes.

As variáveis 'TCP UL Retrans. Vol (Bytes)' e 'TCP DL Retrans. Vol (Bytes)' mesmo possuindo alto percentual de valores ausentes, foram mantidas e passaram por tratamento pelo método de preenchimento reverso, por entender que estas variáveis representam informações relevantes para futuras análises.

As variáveis 'Avg RTT DL (ms)' e 'Avg RTT UL (ms)' passaram por tratamento de valores ausentes pelo método de preenchimento progressivo.

As variáveis "Handset Type" e "Handset Manufacturer" são do tipo categóricas e por decisão de negócio foram preenchidas com o valor "unknown" onde possuia valores ausentes.

Após a realização dos procedimentos supracitados restaram 2,08 % de registros (linhas) contendo pelo menos um valor ausente, portanto estes registros foram descartados.


### Conversão de Tipos de Dados:

'Start' e 'End' para Datatime;
Variáveis objeto para String;
'Bearer Id', 'IMSI', 'MSISDN/Number' e 'IMEI' para Int.


### Tratamento de Outliers:

Todas as variáveis do tipo float passaram por tratamento de outliers, substituindo estes valores por valores estatísticos de Maximum ou Minimum.

## Resultado

O dataset final possui 146887 registros (linhas), com 46 variáveis (colunas). 

Um novo arquivo csv foi gerado para que a partir dele o cientista de dados possa realizar previsões em relação aos comportamentos dos usuários e desenvolver juntamente com os tomadores de decisão e toda resposável, ações voltadas para rentenção de clientes.

Você pode reproduzir os resultados do projeto através do link do Google Colab: <a href ="https://colab.research.google.com/drive/1ifMRaYV57KQWHX_p1LPoot2fcexod5uz?usp=sharing">Análise Exploratória, Limpeza e Transformações de Dados de Telecomunicações<a>

## Referências

Este projeto foi desenvolvido com auxilio de técnicas apresentadas no curso: <a href="https://www.datascienceacademy.com.br/course/analise-de-dados-com-linguagem-python-dsa">Análise de Dados com Linguagem Python - Data Science Academy</a>
