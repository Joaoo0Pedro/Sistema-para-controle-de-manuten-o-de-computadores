# 04. Modelagem, arquitetura e rastreabilidade (A9, A10)

Este documento apresenta os modelos utilizados para representar o funcionamento e a estrutura do Sistema para Controle de Manutenção de Computadores. A modelagem foi realizada por meio de um fluxograma e de um wireframe, complementados pela descrição da arquitetura conceitual e pela matriz de rastreabilidade.

## Fluxograma: processo de manutenção de computadores (A9)

O fluxograma representa as principais etapas do processo de manutenção realizado pela assistência técnica, desde o recebimento do equipamento até a conclusão do serviço.

O processo considera o cadastro ou identificação do cliente e do computador, a abertura da ordem de serviço, o diagnóstico do problema, a elaboração do orçamento e a aprovação pelo cliente.

Uma das principais regras consideradas é a RN01: o serviço de manutenção somente pode ser iniciado após a aprovação do orçamento pelo cliente.

**Imagem do fluxograma:**

> [<img width="2512" height="1320" alt="Diagrama em branco (4)" src="https://github.com/user-attachments/assets/fa46e39a-acb7-453e-83d0-37a54f8597a7" />]

## Wireframe: interface do sistema (A9)

O wireframe representa a organização visual das telas e dos elementos da interface do Sistema para Controle de Manutenção de Computadores.

O modelo foi utilizado para visualizar como os usuários poderão interagir com o sistema e acessar as funcionalidades previstas, como o gerenciamento de clientes, computadores e ordens de serviço.

A elaboração do wireframe permitiu organizar as informações e visualizar a disposição dos elementos antes da implementação da interface.

**Imagem do wireframe:**

> [<img width="1574" height="908" alt="Diagrama em branco (3)" src="https://github.com/user-attachments/assets/8dec84e5-540e-4bfe-b8f1-ae27293c9c94" />]

## Arquitetura conceitual (A10)

A arquitetura conceitual do sistema foi organizada em três componentes principais: interface, lógica de negócio e dados. Essa divisão permite separar as responsabilidades e compreender como as partes do sistema se relacionam.

| Componente | Responsabilidade | Requisitos relacionados |
|---|---|---|
| Interface | Permitir a interação dos usuários com o sistema, incluindo cadastros, abertura de ordens de serviço e consulta de informações. | B01, B02, B03, B04 e B05 |
| Lógica de negócio | Processar as informações, validar os dados e aplicar as regras de negócio, como a aprovação de orçamentos antes do início dos serviços. | B04, B05, B06 e RN01 |
| Dados | Armazenar e disponibilizar as informações de clientes, computadores, ordens de serviço e orçamentos. | B02, B03, B04, B05 e B06 |

Também foi considerada a possibilidade de integração futura com uma API de pagamento. Essa integração não faz parte da primeira versão planejada e permanece como possibilidade de evolução do sistema.

A arquitetura foi definida conceitualmente, sem a elaboração de um diagrama visual nesta atividade.

## Matriz de rastreabilidade

A matriz de rastreabilidade relaciona as necessidades identificadas no projeto aos itens do backlog, às regras de negócio, aos modelos e aos componentes do sistema. Seu objetivo é facilitar o acompanhamento dos requisitos e verificar como as necessidades influenciam o desenvolvimento.

| Origem / necessidade | Item do backlog | Regra de negócio | Modelo relacionado | Componente |
|---|---|---|---|---|
| Organizar os dados dos clientes. | B02 – Clientes | — | Wireframe | Interface e dados |
| Registrar os equipamentos recebidos para manutenção. | B03 – Computadores | — | Wireframe | Interface e dados |
| Organizar os atendimentos e serviços de manutenção. | B04 – Ordens de serviço | — | Fluxograma | Interface, lógica de negócio e dados |
| Acompanhar o andamento dos serviços. | B05 – Status da OS | — | Fluxograma e wireframe | Interface, lógica de negócio e dados |
| Registrar orçamentos e a aprovação do cliente. | B06 – Orçamento e confirmação do serviço | RN01 – O serviço depende da aprovação do orçamento. | Fluxograma | Lógica de negócio e dados |
| Exigir o pagamento de uma entrada antes do início do conserto. | B06 – Alteração relacionada à SM-01 | SM-01 – Entrada de 30% antes do início do serviço, com possibilidade de pagamento integral antecipado. | Fluxograma a atualizar | Lógica de negócio e dados |
| Garantir o pagamento do valor restante antes da retirada do equipamento. | B06 – Alteração relacionada à SM-01 | SM-01 – Pagamento dos 70% restantes antes da retirada. | Fluxograma a atualizar | Lógica de negócio e dados |

### Requisitos não funcionais

Os requisitos não funcionais também devem ser considerados na organização e na avaliação da arquitetura.

| Requisito | Descrição | Componente relacionado |
|---|---|---|
| RNF01 | O sistema deverá suportar até 8 usuários simultâneos. | Lógica de negócio e dados |
| RNF02 | O sistema deverá minimizar interrupções durante o uso. | Arquitetura do sistema e infraestrutura |

### Observações sobre a rastreabilidade

- Os identificadores B01 a B06 correspondem aos itens do backlog utilizados no planejamento do projeto.
- A SM-01 representa uma solicitação de mudança aprovada parcialmente pelo Product Owner.
- A alteração relacionada ao pagamento deverá ser incorporada ao fluxograma quando for implementada.
- Os testes correspondentes às necessidades identificadas deverão ser relacionados à matriz conforme forem definidos e executados pela equipe.

## Considerações finais

A modelagem contribuiu para representar o funcionamento e a organização do Sistema para Controle de Manutenção de Computadores. O fluxograma permitiu visualizar o processo de manutenção, enquanto o wireframe auxiliou na organização da interface. A arquitetura conceitual apresentou a divisão das responsabilidades do sistema, e a matriz de rastreabilidade relacionou as necessidades identificadas aos itens do backlog e aos componentes envolvidos.

Esses elementos servem como referência para orientar o desenvolvimento, facilitar a compreensão do sistema e apoiar futuras alterações.
