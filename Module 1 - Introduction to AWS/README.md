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
  - AWS Command Line Interface: com scripts, consegue-se buscar uma lista de Buckets 
  - AWS Software Develompent Kits (SDK's)
 ***

# Segurança e o modelo de responsabilidade compartilhada da AWS
- Ambos clientes e a AWS tem responsabilidade sobre a segurança da aplicação
![AWS_Security](/Module%201%20-%20Introduction%20to%20AWS/Assets/AWS_Shared_Responsibility_Model.png)

###### Responsabilidade da AWS
- Segurança da nuvem: protege e assegura a infraestrutura que executa serviços oferecidos na Nuvem AWS

###### Responsabilidade do cliente
- Responsável por configurar adequadamente o serviço e seus aplicativos, além de garantir que seus daods estejam seguros
- Nível de responsabilidade: depende do serviço da AWS
- Clientes: mantêm controle total de seus dados e são responsáveis por gerenciar a segurança relacionada ao seu conteúdo:
  - escolha de região
  - implementar mecanismos de proteção de dados (criptografia e backups agendados)
  - controle de acesso para limitar quem pode acessar seus dados e recursos da AWS
***

# Protegendo o usuário raiz da AWS
- Usuário raiz tem 2 conjunto de credenciais:
  - E-mail e senha
  - Chaves de acesso (ID da chave de acesso e Chave de acesso secreta): permite fazer solicitações programáticas da AWS CLI ou API
***

# Gerenciamento de identidade e acesso da AWS
## O que é IAM?
- AWS Identity and Acess Management (IAM): serviço da AWS que ajuda a gerenciar o acesso à sua conta e recursos da AWS

## Recursos do IAM
- 6 categorias para controlar acesso e gerenciar identidades na sua conta da AWS:
  - Global
  - Integrado com serviços AWS
  - Acesso compartilhado
  - Autenticação multifatorial
  - Federação de identidade
  - Livre para usar

## Usuário IAM
- Representa pessoa ou serviço que interage com a AWS
- Definindo um usuário na conta AWS, qualquer atividade é cobrada na conta e este usuário pode fazer login para obter acesso aos recursos da AWS dentro da conta
- Cada pessoa deve ter as próprias credenciais de login para evitar o compartilhamento de credenciais
- Consiste em nome e conjunto de credenciais
- Pode fornecer a ele os acessos:
  - AWS Management Console
  - Acesso programático à AWS CLI e à AWS API

## Grupos IAM
- Coleção de usuários
- Todos usuários do grupo herdam permissões atribuídas ao grupo

## Políticas de IAM
- É uma maneira de conceder permissões no IAM
- Gerenciar o acesso e fornecer permissões aos serviços e recursos da AWS -> criar políticas do IAM e anexá-las em uma identidade do IAM
- Identidade do IAM faz solicitação -> AWS avalia políticas associadas a ela
  - **Ex 1:** fornecer acesso de administrador 
    ``` 
    {
      "Version": "2012-10-17",
      "Statement": [{
        "Effect": "Allow",
        "Action": "*",
        "Resource": "*"
      }]
    }
    ```
      - **Effect:** especifica se a política permite ou nega o acesso
      - **Action:** descreve o tipo de ação que permite ou nega
      - **Resource:** especifica objeto(s) que a declaração de política abrange. o "*" representa permissão em todos os recursos
  
  - **Ex 2:** bloqueia acesso às ações do Amazon S3, ao menos que esteja sendo acessado pela conta 222222222222 
    ``` 
    {
      "Version": "2012-10-17",
      "Statement": [
        {
          "Sid": "DenyS3AccessOutsideMyBoundary",
          "Effect": "Deny",
          "Action": [
            "s3:*"
          ],
          "Resource": "*",
          "Condition": {
            "StringNotEquals": {
              "aws:ResourceAccount": [
                "222222222222"
              ]
            }
          }
        }
      ]
    }
    ```

## Funções do IAM
- Permissões que users podem ter

## Melhores práticas de IAM
###### Bloqueie o usuário root da AWS:
- Não compartilhar credenciais associadas ao user root
- Considerar excluir chaves de acesso 
- Ativar MFA na conta raiz

###### Princípio do menor privilégio
- Princípio de segurança padrão
- Aconselha a conceder apenas permissões necessárias para fazer um trabalho especifico e nada mais
- Comecar com um conjunto mínimo de permissões em uma política IAM e conceder adicionais conforme necessário para um user, grupo ou função

###### Use o IAM adequadamente
- Não é usado para autenticação e autorização de sites nem oferece suporte a controles de segurança para proteger sistemas operacionais e redes

###### Use funções do IAM quando possível
- Manter funções é mais eficiente que manter usuários
- Assumir função -> IAM fornece credenciais temporárias

###### Considere usar provedor de identidade
- Se o app começar a ter mais gente trabalhando nele, considerar gerenciar informações de identidade de funcionários por meio de um provedor de identidade (IdP)
- Usar IdP fornece uma única fonte de verdade para todas as identidades na organização
- Não é mais preciso criar usuários IAM separados na AWS  -> pode usar funções IAM para fornecer permissões a identidades que são federadas do seu IdP (processo que permite transferência de informações de identidade e autenticação em um conjnto de sistemas em rede)
  - Ex: Felipe tem acesso a várias contas da AWS -> pode gerenciar uma conta Felipe no IdP da empresa em vez de ter vários usuários do IAM chamando Felipe em cada uma das contas

###### Revise e remova regularmente usuários, funções e outras credenciais não utilizadas
- IAM fornece informações de último acesso para ajudar a identificar credenciais irrelevantes para poder removê-las -> ajuda a reduzir usuários, funções, permissões, políticas e credenciais que precisa monitorar
