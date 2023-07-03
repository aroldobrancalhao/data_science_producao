Predição de vendas das lojas Rossmann


1.0 Contexto
Rossmann possui mais de 3.000 farmácias em 7 países da Europa. Atualmente, os gerentes das farmácias Rossmann receberam a tarefa de precificar as vendas de cada loja para as próximas seis semanas. As vendas são influenciadas por vários fatores como promoções, competição, feriados, sazonalidade e localização. Como centenas de gerentes realizam suas previsões de maneiras distintas, o resultado ficaria muito variado e dificilmente poderia ser comparado de maneira justa.

2.0 Desafio do Negócio
Durante uma reunião mensal com os gerentes, o CFO da Rossmann solicitou que estes enviassem uma previsão de vendas de cada loja das próximas 6 semanas. Desta forma foi necessária a atuação do cientista de dados para criar um modelo de previsão de vendas das próximas 6 semanas separados por loja.

3.0 Resumo
Após ser contactado por diversos gerentes para realizar a previsão de cada uma das lojas, entendemos que a demanda partiu do CFO, e para verificar se realmente esta precificação seria a melhor entrega conversamos com o CFO para entender sua demanda. Após esta conversa nos foi informado que a precificação das vendas é parte da estratégia de definição de investimento nas lojas, e para isso ele precisaria que a precificação fosse melhor que a média de vendas das lojas que atualmente é utilizado.

Desta forma entendemos que realmente o modelo de precificação supre a necessidade do CFO, e ele será entregue via bot no Telegram, que permitirá que de qualquer local o CFO possa realizar tal consulta de seu celular e definir sua estratégia de investimentos nas lojas.

Fonte de dados
Notebook Link
4.0 Descrição dos Dados
Id - Id único que representa (Loja, Data)
Store - ID das lojas
Sales - Vendas do dia
Customers - Número de clientes no dia
Open - Indicador se a loja está aberta: 0 = Fechada, 1 = Aberta
StateHoliday - Feriados. Normalmente as lojas ficam fechadas nos feriados estaduais, exceto algumas. Todas as escolas ficam fechadas nos feriados públicos e fins de semana. a = public holiday, b = Easter holiday, c = Christmas, 0 = None
SchoolHoliday - indica se a loja foi afetada pelo fechament das escolas públicas
StoreType - 4 tipos de moedlos de loja: a, b, c, d
Assortment - descreve o sortimento de cada loja: a = basic, b = extra, c = extended
CompetitionDistance - distancia em metros para o competidor mais próximo
CompetitionOpenSince[Month/Year] - ano e mês aproximado em que a competição mais próxima foi aberta
Promo - indica se a loja está realizando promoção no dia
Promo2 - Promo2 é uma promoção contínua e consecutiva para algumas lojas: 0 = Loja não participante, 1 = Loja participante
Promo2Since[Year/Week] - Ano e semena em que a loja começou a participar da Promo2
PromoInterval - descreve os intervalos consecutivos em que a Promo2 éiniciada, nomeando os meses em que cada rodada de promoção começa para qualquer ano para esta loja
5.0 Solução
Para a solução foi aplicado o método CRISP-DS, onde começamos com o entendimento do negócio, passamos para coleta dos dados, limpeza dos dados, EDA (Análise Exploratória dos dados), modelagem, Avaliação do modelo e por fim a publicação do modelo em produção.

Para o deploy do modelo utilizamos o render, onde o modelo treinado recebe os dados através de uma requisição por um arquivo JSON e devolve com a coluna de previsão.

6.0 Bot do Telegram
Com o intuito de melhorar a solução para o usuário, criamos um bot no Telegram onde o usuário pode informar o número da loja e receber a previsão das próximas 6 semanas diretamente em seu celular ou computador.

Link
7.0 Próximos passos:
Melhorar as métricas do modelo;
Utilizar métodos complementares ao Bot do Telegram para que o usuário possa realizar tal consulta;
