+++
date = '2026-03-04T23:18:57-03:00'
draft = false
title = 'Incidente de Camada 1: Decomposição do problema e pensamento sistêmico.'
author = "Enauara"
+++

Recentemente me peguei lembrando de um caso da época que eu trabalhava no provedor de internet. Um problema de quedas de clientes na rede de fibra óptica, mas bem diferente do que eu já havia vivenciado até aquele momento.

**O cenário:**

Na rede de fibra óptica, diversos clientes desconectavam e conectavam aleatoriamente sem um padrão específico de comportamento aparente.

A causa raíz? Uma ONU molhada. O caminho até a conclusão e solução exigiu decomposição do problema, identificação de padrões, pensamento sistêmico e trabalho em equipe.

**Detalhamento do caminho para identificação e solução do problema:**

Primeiramente pensei em estratégias para quebrar o problema em partes menores, ir descartando possibilidades.

1. Verificar os logs do equipamento central (OLT e servidor PPPoE):
Nada de diferente, apenas log de desconexão e conexão.

2. Verificar o sinal óptico dos clientes:
Ao conferir o sinal óptico de alguns clientes foi identificado que estavam com um bom sinal, não sendo a causa das quedas. Descartando também rompimento de fibra, pois eles conectavam novamente.

3. Verificar localização geográfica dos clientes:
Para filtrar se é em uma determinada região e atuar em possíveis atenuações em alguma caixa de distribuição ou quedas/oscilações de energia.
O problema estava ocorrendo em diversas regiões da cidade. Descartado problema em um local específico.

4. Verificar ponto de conexão dos clientes no equipamento central (OLT):
    
    Foi identificado que todos os clientes que apresentavam problema estavam na mesma porta da OLT, nesse momento cheguei a um padrão entre eles e comecei a atuar com mais precisão.

    Trabalhei no splitter daquela porta da OLT, retirando um conector por vez, até que em um momento os clientes pararam de cair. Opa, identificado que algum cliente daquela porta do splitter estava "jogando sujeira" na rede. 

    Identificados quais eram os clientes (em torno de 6), os técnicos foram até os clientes para verificar pessoalmente se encontravam algo que explicasse.    

    Encontramos o cliente causador das quedas, e pasmem, o que causou a queda foi uma ONU molhada. Ou seja, além de prejudicar o próprio, ainda impactou em parte da rede. O temido problema de Camada 1!


**Explicação técnica básica:**

Ao entrar água no conector da ONU, quebrou o índice de refração. A luz "se perde" ao encontrar líquido na fibra, gerando uma reflexão de retorno, em vez da luz ser consumida pela ONU, ela "bate e volta" em direção à OLT, afetando também os outros clientes da mesma porta. Aqui estamos falando de tecnologia EPON.

ONU e OLT fazem a comunicação óptica entre cliente(ONU) e provedor(OLT). 

**Conclusão:**

Aprendi mais e reforcei a importância do pensamento sistêmico e decomposição do problema. Analisar os impactos que um "inocente e pequeno" problema pode causar no ambiente ao redor.

"_Ah, mas você trabalha com desenvolvimento hoje, isso é redes e telecom..._".

Sim, os aprendizados e experiências seguem fazendo sentido, e facilitando o entendimento como um todo, seja ao pegar um problema ou algo novo para aprender. Consigo ter uma visão mais ampla. Essas experiências prévias foram muito importantes para minha migração de carreira Redes/Telecom -> Desenvolvimento. E, claro, seguir aprendendo a cada dia. "Só sei que nada sei".
