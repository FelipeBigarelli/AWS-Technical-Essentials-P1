# Computação como um serviço
- Em nível fundamental -> 3 tipos de opções de computação disponíveis:
    - VMs
    - Serviços de contêiner
    - Sem servidor (serverless)

## Servidores 
- **Servidor:** primeiro bloco de construção para hospedar um app
- Podem lidar com solicitações HTTP, enviando respostas aos clientes seguinto o modelo cliente-servidor
- **Cliente:** pessoa ou PC que envia solicitação. Servidor que manipula solicitações: PC ou conjunto de PCs. 

## Escolhendo a opção de computação correta
- Primeiro é necessário saber qual serviço de computação usar para cada caso de uso
- Se tiver conhecimento pŕevio, uma VM será a opção mais fácil de entender -> VM emula servidor físico e permite que instale servidor HTTP para executar apps
***

# Introdução ao Amazon EC2
- Ao Arquitetar qualquer APP para alta disponibilidade, considerar usar pelo menos 2 instâncias do EC2 em duas Zonas de Disponibilidade separadas