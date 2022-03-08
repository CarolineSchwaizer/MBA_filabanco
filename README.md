# MBA_filabanco
# **BANCOS**
Este programa simula a chegada de clientes a um banco, que possui alguns postos de atendimento (caixas). A fila é única para todos os caixas.
Os tempos entre chegadas de clientes segue uma distribuição exponencial.
A duração do atendimento a um cliente no caixa segue uma distribuição normal. 

# horario
Variável inteira com o horário atual. O tempo é medido em segundos, contados a partir do instante 0 (instante em que a simulação começou a ser executada).
Por exemplo, se horario = 1000, então já decorreram 1000 segundos desde o início da simulação. A simulação começa com horario = 0. 

# eventos 
É uma lista de eventos programados, sendo que cada evento
pode ser:


*   -1 é o evento da chegada de um cliente ao banco
*   0, 1, 2 ... é o evento do término do atendimento de um cliente
no caixa 0, 1, 2, ...
Exemplo: [-1, 2] 
Há dois eventos programados: um refere-se à chegada
de um novo cliente. O outro refere-se ao término do atendimento no caixa 2. Os horários desses eventos programados estão na lista horario_eventos. 

# horario_eventos
É a lista dos horários em que ocorrerão os eventos programados na lista **eventos**. 
Exemplo: [3001, 2900]
Os correspondentes eventos (no exemplo acima, [-1, 2]) estão programados para ocorrer no instante 3001 e no instante 2900, respectivamente. Esses instantes estão medidos em segundos contados desde o intante zero do começo da simulação.

# caixas
É uma lista dos caixas (postos de atendimentos). Cada caixa pode estar em um dos seguintes estados:
*   "livre"
*   "ocupado"
*   "fechado"
Exemplo: havendo 3 caixas e estando todas livres, a lista caixas fica assim: ["livre", "livre", "livre"].

# fila
É uma lista que contém os horários de chegada nos clientes que comporão a fila de atendimento. Serve para podermos medir o tempo de espera em fila. 
Por exemplo, se na fila há dois clientes que chegaram nos insantes 5000 e 5030, então a fila será: 
[5000, 5030]. Repare que fila[0] é sempre o próximo cliente a ser atendido (é o 1o da fila).

# tempos_espera
Lista que registra o tempo de espera na fila de cada cliente que vem ao banco. Se o cliente não encontrou nenhuma fila, registra zero. Unidade é minutos (e não segundos!). 
Por exemplo, se tempos_espera é [0, 0, 2.5], então o três clientes já foram devidamente atendidos pelo banco, desde o início da simulação. Os dois primeiros não ficam na fila (ficaram 0 minutos na fila). O terceiro teve que aguardar na fila 2,5 minutos. 
