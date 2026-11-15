# 01. Descoberta (A1, A3)

## Problema

Muitas assistências técnicas de informática ainda controlam os serviços de manutenção por meio de anotações em papel, planilhas ou aplicativos simples, como bloco de notas.

Esse processo dificulta o acompanhamento do andamento dos reparos, o controle de peças utilizadas, o registro do histórico de manutenção dos equipamentos e a comunicação com os clientes.

A falta de um sistema de controle pode causar perda de informações, atrasos na entrega dos equipamentos e dificuldades para localizar ordens de serviço. Também podem ocorrer problemas na devolução dos equipamentos, como a falta de acessórios que foram entregues junto com o computador, por exemplo, carregadores.

## Contexto

O problema ocorre em pequenas e médias empresas de assistência técnica, oficinas de manutenção de computadores e profissionais autônomos que realizam reparos em notebooks, desktops e outros equipamentos de informática.

Em muitos casos, o controle é feito manualmente, desde o recebimento do equipamento até sua entrega ao cliente.

Durante o processo de manutenção, são registradas informações como defeitos relatados, diagnóstico técnico, troca de peças, testes realizados, orçamento aprovado e status do serviço. Sem um sistema adequado, essas informações ficam dispersas e dependem da organização individual dos técnicos.

## Público (quem utiliza ou é atendido pelo sistema)

- **Técnicos de informática:** utilizam o sistema para registrar, acompanhar e atualizar as ordens de serviço e as informações dos reparos.
- **Atendentes de assistências técnicas:** utilizam o sistema para cadastrar clientes, registrar equipamentos, consultar orçamentos e acompanhar os serviços.
- **Clientes:** precisam receber informações claras sobre o andamento da manutenção, o status do equipamento e os prazos de entrega.

## Stakeholders (quem é afetado ou participa das decisões)

- **Marina – responsável administrativa:** representa a stakeholder do projeto, contribuindo com as necessidades do negócio, esclarecendo regras e apresentando sugestões de melhoria.
- **Proprietários e gestores da assistência técnica:** acompanham os serviços e participam das decisões relacionadas ao funcionamento do negócio.
- **Técnicos responsáveis pelos reparos:** são afetados pelas mudanças na organização das ordens de serviço e no controle das manutenções.
- **Fornecedores de peças e componentes:** podem ser afetados pela organização das informações sobre peças utilizadas e necessidades de reposição.
- **Parceiros de manutenção:** podem participar de serviços e atividades relacionadas à assistência técnica.
- **Clientes pessoa física e empresas:** são afetados pela qualidade do atendimento, pelo acompanhamento dos serviços e pelos prazos de entrega.

## Elicitação (A3)

### Técnica utilizada

A equipe utilizou **entrevistas com apoio de inteligência artificial** para levantar informações sobre a rotina das assistências técnicas, identificar dificuldades no controle das manutenções e compreender as necessidades dos envolvidos.

Foram preparados materiais de entrevista direcionados a dois perfis:

- Gestores de assistência técnica.
- Proprietário de assistência técnica.

As entrevistas foram anexadas ao repositório do projeto como materiais de apoio ao levantamento de necessidades.

**Materiais utilizados:**

- Entrevista com gestores da assistência técnica.
- Entrevista com proprietário.

### Por que essa técnica?

As entrevistas permitem compreender melhor a rotina de uma assistência técnica, identificar dificuldades enfrentadas pelos responsáveis e levantar necessidades que podem não aparecer apenas na descrição inicial do problema.

A utilização de diferentes perfis também ajuda a observar o funcionamento do negócio por perspectivas distintas, considerando tanto a gestão quanto a administração da assistência.

O apoio de inteligência artificial possibilitou simular as entrevistas e obter respostas para orientar o levantamento inicial de requisitos do projeto.

### Respostas das entrevistas

As entrevistas realizadas com apoio de IA serviram como fonte para compreender as dificuldades e necessidades do negócio.

**Observação:** as falas literais dos entrevistados deverão ser inseridas nesta seção após a conferência dos PDFs originais. Não foram reproduzidas falas aqui para evitar atribuir frases que não foram verificadas nos documentos.

| ID | Entrevistado | Material de referência | Falas |
|---|---|---|---|
| R01 | Gestores da assistência técnica | Entrevista com gestores da assistência técnica | A inserir após conferência do PDF. |
| R02 | Proprietário da assistência técnica | Entrevista com proprietário | A inserir após conferência do PDF. |

## Interpretações da equipe

A partir do problema identificado, do contexto do projeto e dos materiais de entrevista, a equipe identificou as seguintes necessidades:

| ID | Interpretação | Base |
|---|---|---|
| I01 | Centralizar as informações dos clientes e dos equipamentos para facilitar a consulta e evitar perda de dados. | A1 |
| I02 | Organizar as ordens de serviço para acompanhar cada manutenção desde o recebimento até a entrega do equipamento. | A1 |
| I03 | Registrar os acessórios entregues junto com os equipamentos para evitar problemas na devolução. | A1 |
| I04 | Manter o histórico das manutenções para facilitar a consulta de serviços anteriores. | A1 |
| I05 | Melhorar a comunicação com os clientes, permitindo que recebam informações claras sobre o andamento dos serviços. | A1 |
| I06 | Organizar os orçamentos e suas aprovações para evitar que os serviços sejam iniciados sem autorização do cliente. | Levantamento de necessidades e regras de negócio |

## Resultado da descoberta

A etapa de descoberta permitiu identificar os principais problemas enfrentados por assistências técnicas que realizam o controle manual das manutenções.

Com base nessas informações, a equipe definiu como foco do projeto desenvolver um sistema que centralize os dados de clientes, equipamentos, ordens de serviço e orçamentos, facilitando o acompanhamento dos reparos e a organização das atividades da assistência técnica.
