# Computação em nuvem (CN)

- Entrega sob demanda de recursos de TI com preços conforme o uso

- Fornece a capacidade de se concentrar no que mais importa, evitando trabalhos como aquisição, manutenção e planejamento de capacidade

- CN cresce: + estratégias de implantação -> + níveis de controle, flexibilidade e gerenciamento

***

#### Local VS Nuvem VS Híbrido

- **Local:**
  - empresas hospedavam e mantinham hardware como equipamentos de computação, armazenamento e rede nos próprios data centers
  - departamentos inteiros de infraestrutira para cuidar dos data centers: gerava operações custosas -> surge a CN

- **Nuvem:**
  - entrega sob demanda com preços pay-as-you-go
  - empresas não precisam gerenciar e manter hardwares ou data centers
  - empresas de CN: possuem e mantêm data centers, fornecendo tecnologias e serviços de data centers virtuais para empresas

- **Híbrido:**
  - maneira de conectar infraestrutura e apps entre recursos baseados em nuvens e recursos existentes que não se localizam na nuvem

***

# Computação em nuvem (CN) - CONT

- Economiza tempo durante configuração e remove tarefas desnecessárias (remoção de trabalho pesado indiferenciado)
- **Serviços da AWS:** arquitetar uma infraestrutura escalável, altamente disponível e econômica

## Seis vantagens da CN

##### Pague conforme o uso

- Pagar apenas pelos recursos que você usa

##### Enormes economias de escala

- Atingir um custo menor do que se fosse sozinho
- Maior economia de escala -> preços mais baixos conforme o uso

##### Pare de adivinhar a capacidade

- Ao tomar uma decisão de capacidade antes de implementar, muitas vezes fica caro ou limitado
- CN -> acessa a capacidade conforme o necessário em pouco tempo

##### Velocidade e Agilidade

- Poucos cliques -> redução do tempo para disponibilizar recursos aos devs
- Aumento drástico na agilidade da organização pois custo e tempo são muito menores

##### Economias de custo

- CN remove o "trabalho pesado indiferenciado" -> pode-se concentrar nos clientes em vez de empilhar e alimentar uma infraestrutura física

##### Torne-se global em minutos

- Apps implantados em várias regiões do mundo com alguns cliques
- Pode fornecer menor latência e melhor experiência aos clientes a um custo mínimo
***

# Infraestrutura global da AWS
- Vários data centers pelo mundo compartilhando dados -> caso um falhe, outro continua funcionando (Availability Zone)
- Nomeados como Regiões
- Como escolher regiões?
  - Compliance (conformidade): aonde está sua região? Na mesma área em que vive?
  - Latency: serviço sensível à latência -> escolher região próxima da base de usuários
  - Price
  - Service Availability: alguns serviços podem não estar disponíveis em algumas regiões

## Escopo dos Serviços da AWS
- Dependendo do serviço que usa -> recursos são implantados no nível de Zona de Disponibilidade, Região ou Global
- Cada serviço é diferente: entender como o escopo de um serviço pode afetar a arquitetura de aplicativo
- Serviço: se não solicitar a região, significa que o serviço opera em nível de Região -> escopo Região: executa automaticamente ações para aumentar a durabilidade e a disponibilidade dos dados. Se pedem uma Zona de Disponibilidade específica -> você é resposável por aumentar a durabilidade dos dados e a alta disponibilidade desses recursos.


## Manter a resiliência
- Manter o app disponível: manter a alta disponibilidade e resiliência
- Prática recomendada: usar servilos gerenciados com escopo de região -> estes vêm com disponibilidade e resiliência incorporadas. Se não for possível, certificar que a carga de trabalho seja replicada em várias Zonas de Disponibilidade (mínimo de 2 Zonas) -> se uma falhar, o app terá a infraestrutura instalada e funcionando em uma segunda Zona para assumir o tráfico

## Edge Locations (Locais de Ponta)
- Locais globais onde o conteúdo é armazenado em cache
- Exemplo: vídeo na Cidade A e quer compartilhar na Cidade B -> vídeo em cache em uma Edge location mais próximo da Cidade B, que irá acessar mais rápido
***

# Interagindo com a AWS
- 3 principais meios de interagir com a AWS API:
  - AWS Management Console
  - AWS Command Line Interface
  - AWS Software Develompent Kits (SDK's)