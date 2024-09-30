# Resumo-Projeto-Criando-um-Assistente-de-Delivery-com-AWS-Step-Functions-e-Bedrock

1. Explicação da ferramenta Step Functions:
AWS Step Functions é um serviço de orquestração serverless que permite coordenar múltiplos serviços AWS em fluxos de trabalho visuais. Durante o projeto, aprendi que essa ferramenta é crucial para criar aplicações distribuídas, pois permite definir uma sequência de etapas, condições e ramificações de forma clara e visual. No caso do Assistente de Delivery, o Step Functions foi fundamental para gerenciar todo o fluxo do pedido, desde a recepção até a entrega.

2. Pré-requisitos:
Para trabalhar com Step Functions, percebi que é essencial ter:
- Uma conta AWS ativa
- Conhecimentos básicos sobre serviços AWS como Lambda, DynamoDB, e SQS
- Familiaridade com JSON para definição de máquinas de estado
- Compreensão de conceitos de workflows e máquinas de estado
- Permissões IAM adequadas para criar e gerenciar recursos

3. Localização e integração de serviços com Step Functions:
Aprendi que para integrar serviços ao Step Functions, é necessário:
- Acessar o console AWS e buscar o serviço "Step Functions"
- Ao criar uma máquina de estado, utilizar o painel lateral para localizar os serviços disponíveis
- Arrastar e soltar os serviços desejados no canvas do Workflow Studio
- Configurar os parâmetros de integração, como ARNs de funções Lambda ou nomes de filas SQS

4. Iniciando um template no Step Functions:
Para iniciar um template, aprendi a:
- Acessar o console do Step Functions
- Clicar em "Create state machine"
- Escolher entre começar do zero ou usar um template existente
- Se optar por um template, selecionar o mais adequado ao projeto (no caso, seria útil um template relacionado a processamento de pedidos)
- Customizar o template conforme as necessidades específicas do Assistente de Delivery

5. Experiência com Workflow Studio e ASL:
O Workflow Studio se mostrou uma ferramenta visual incrivelmente útil para desenhar o fluxo do Assistente de Delivery. Pude arrastar e soltar estados, definir transições e configurar parâmetros de forma intuitiva. Já o Amazon States Language (ASL) foi essencial para entender a estrutura subjacente da máquina de estados. Alternar entre a visão visual e o código ASL me ajudou a compreender melhor como o workflow está sendo definido e me permitiu fazer ajustes finos quando necessário.

6. Precificação e custos:
Durante o projeto, aprendi sobre o modelo de precificação do Step Functions:
- Cobrança por transição de estado (a cada passo executado no workflow)
- Preços diferentes para fluxos de trabalho padrão e expressos
- Camada gratuita disponível para experimentação
- Custos adicionais dos serviços AWS integrados (como Lambda, DynamoDB)
Percebi a importância de projetar workflows eficientes para otimizar custos, evitando transições desnecessárias.

7. Configuração do projeto - permissão do perfil:
Para configurar as permissões adequadas, aprendi a:
- Criar uma role IAM específica para o Step Functions
- Anexar políticas que permitam acesso aos serviços necessários (Lambda, DynamoDB, SQS, etc.)
- Usar o princípio do menor privilégio, concedendo apenas as permissões essenciais
- Configurar trust relationships para permitir que o Step Functions assuma a role

8. Configuração do projeto - disponibilidade do serviço:
Aprendi sobre a importância de considerar a disponibilidade regional dos serviços AWS. Para o Assistente de Delivery, foi necessário:
- Verificar se todos os serviços necessários estão disponíveis na região escolhida
- Configurar backups e estratégias de recuperação para garantir alta disponibilidade
- Considerar o uso de múltiplas regiões para maior resiliência, especialmente para um serviço crítico como delivery

9. Criando um assistente de delivery com uma máquina de estado:
Para criar o Assistente de Delivery, segui estes passos:
- Desenhei o fluxo completo do pedido, desde a recepção até a entrega
- Criei estados para cada etapa do processo (validação do pedido, processamento de pagamento, atribuição de entregador, etc.)
- Implementei lógica de erro e retentativas para lidar com falhas
- Integrei serviços como Lambda para processamento, DynamoDB para armazenamento de pedidos, e SQS para filas de entrega
- Utilizei o Amazon Bedrock para adicionar inteligência ao assistente, como sugestões personalizadas e previsão de tempo de entrega

Complementando, gostaria de adicionar que a experiência de criar um Assistente de Delivery usando AWS Step Functions e Amazon Bedrock foi extremamente enriquecedora. Aprendi não apenas sobre a orquestração de serviços, mas também sobre como criar sistemas distribuídos robustos e escaláveis. 

A integração com o Amazon Bedrock, em particular, abriu meus olhos para as possibilidades de incorporar IA generativa em fluxos de trabalho automatizados. Isso permitiu criar um assistente mais inteligente e adaptativo, capaz de lidar com situações complexas e fornecer uma experiência personalizada aos clientes.

Além disso, percebi a importância de considerar aspectos como segurança (usando encriptação em trânsito e em repouso), conformidade (especialmente com regulamentações de proteção de dados) e monitoramento (utilizando CloudWatch para rastrear métricas e logs) ao desenvolver um sistema desse porte.

Por fim, essa experiência me mostrou o poder da computação serverless e da orquestração de microserviços para criar soluções escaláveis e de alto desempenho. Acredito que essas habilidades serão extremamente valiosas no desenvolvimento de sistemas complexos no futuro.
