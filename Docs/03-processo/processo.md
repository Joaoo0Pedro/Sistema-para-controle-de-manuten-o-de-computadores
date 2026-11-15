# 03. Processo e planejamento (A2, A7, A8)

## 1. Ciclo de vida e processo

### Ciclo de vida

O projeto adotou uma abordagem **Ágil**, com desenvolvimento organizado em incrementos e possibilidade de ajustes ao longo do trabalho.

A escolha foi feita considerando o tamanho da equipe, a disponibilidade da stakeholder Marina e a possibilidade de surgirem novas necessidades durante o desenvolvimento.

A equipe entendeu que seria importante manter contato com a stakeholder para receber retornos, revisar os requisitos e adaptar o planejamento conforme necessário.

A decisão foi revisada após o feedback recebido na AP1, buscando um processo que permitisse maior acompanhamento e adaptação durante o projeto.

### Processo de trabalho

O processo escolhido foi o **Kanban**, utilizado para organizar as atividades e acompanhar visualmente o andamento do desenvolvimento.

A equipe optou por esse processo porque possui três integrantes, e a disponibilidade da stakeholder pode variar. Dessa forma, o Kanban permite reorganizar as prioridades sem depender de ciclos fixos de desenvolvimento.

### Fluxo de trabalho

| Etapa | Regra |
|---|---|
| Backlog | Reúne as atividades e necessidades identificadas para o projeto. |
| A Fazer | Recebe as tarefas priorizadas pelo Product Owner. |
| Em Desenvolvimento | Reúne as tarefas que estão sendo implementadas. |
| Em Teste | As funcionalidades são verificadas conforme os critérios de aceitação e os testes previstos. |
| Concluído | Recebe as tarefas que atenderam aos critérios de aceitação, passaram pelos testes e tiveram o código registrado no repositório. |

**Limite de trabalho em andamento (WIP):** a equipe definiu um limite de três tarefas em andamento, buscando evitar o acúmulo de atividades e manter o foco no desenvolvimento.

**Tratamento de problemas:** caso uma tarefa não passe nos testes ou não atenda aos critérios de aceitação, ela retorna para Em Desenvolvimento para correção e nova verificação.

### Papéis e responsabilidades

| Integrante | Papel | Responsabilidades |
|---|---|---|
| Yudi Michel Noronha Hartmann | Product Owner (PO) | Contato com a stakeholder, levantamento de requisitos, priorização do backlog e decisões sobre as solicitações de mudança. |
| João Pedro Chimello Goulart | Desenvolvedor | Implementação das funcionalidades, desenvolvimento do sistema e registro dos commits no repositório. |
| Arthur Matos dos Reis | Testador | Revisão dos artefatos, elaboração e execução dos testes e verificação dos critérios de aceitação. |

**Stakeholder:** Marina, responsável administrativa, que apresenta as necessidades do negócio e fornece retornos para orientar a evolução do sistema.

### Definição de pronto (Definition of Done)

Uma tarefa é considerada concluída quando:

- Os critérios de aceitação foram atendidos.
- Os testes previstos foram executados com sucesso.
- Não existem defeitos críticos pendentes relacionados à tarefa.
- O código está registrado no repositório do projeto.

As verificações acontecem principalmente na etapa Em Teste, com responsabilidade de Arthur e colaboração dos demais integrantes quando necessário.

## 2. Backlog, estimativas e incrementos

O backlog reúne os requisitos e as atividades necessárias para desenvolver o Sistema para Controle de Manutenção de Computadores.

A priorização considera a importância das funcionalidades para o funcionamento do sistema e as necessidades identificadas junto à stakeholder.

### Backlog inicial

| ID | Item | Prioridade | Tamanho | Incremento |
|---|---|---|---|---|
| B01 | Login e autenticação de usuários. | Alta | P | 1 |
| B02 | Cadastro e gerenciamento de clientes. | Alta | M | 1 |
| B03 | Cadastro e gerenciamento de computadores. | Alta | M | 1 |
| B04 | Criação e gerenciamento de ordens de serviço. | Alta | G | 1 |
| B05 | Acompanhamento do status das ordens de serviço. | Alta | M | 2 |
| B06 | Orçamento e confirmação do serviço, conforme RN01. | Alta | A confirmar | A confirmar |

**Referência de estimativa:** os tamanhos P, M e G representam, respectivamente, tarefas pequenas, médias e grandes. O tamanho considera o esforço e a complexidade envolvidos no desenvolvimento.

### Organização dos incrementos

**Incremento 1:** concentra as funcionalidades iniciais necessárias para estruturar o sistema, incluindo autenticação, cadastro de clientes, cadastro de computadores e gerenciamento das ordens de serviço.

**Incremento 2:** contempla o acompanhamento do status das ordens de serviço, permitindo que os funcionários acompanhem o andamento das manutenções.

**Orçamento e confirmação do serviço:** o requisito B06 está relacionado à regra de negócio RN01 e precisa ter sua distribuição confirmada conforme o planejamento original da equipe.

### Atualização do backlog – Solicitação SM-01

Após a solicitação da stakeholder Marina, a equipe decidiu aprovar parcialmente a mudança SM-01.

As funcionalidades aprovadas foram:

- Exigir o pagamento de uma entrada de 30% antes do início do conserto.
- Permitir o pagamento integral antecipado.
- Exigir a quitação dos 70% restantes antes da retirada do equipamento.
- Realizar a confirmação manual dos pagamentos nesta primeira implementação.

Os lembretes automáticos ao cliente e as notificações à assistência foram adiados para uma atualização futura.

Essa mudança deverá ser incorporada ao backlog e ao planejamento dos incrementos após a atualização dos artefatos afetados.

## 3. Riscos (registro do planejamento)

A equipe identificou riscos que podem afetar o desenvolvimento e o cumprimento do planejamento.

| ID | Risco | Probabilidade | Impacto | Mitigação |
|---|---|---|---|---|
| R01 | A stakeholder apresentar novas necessidades ou alterações nos requisitos durante o desenvolvimento. | A confirmar | A confirmar | Manter contato com Marina, registrar as solicitações e analisar seus impactos antes de realizar alterações. |
| R02 | Atrasos no desenvolvimento devido ao volume de tarefas e ao prazo disponível. | A confirmar | A confirmar | Utilizar o limite WIP de três tarefas, priorizar as atividades e acompanhar o andamento pelo Kanban. |

### Acompanhamento dos riscos

Os riscos devem ser acompanhados durante o desenvolvimento, considerando as mudanças nos requisitos, a disponibilidade da stakeholder e o andamento das tarefas.

A solicitação SM-01 demonstra a importância desse acompanhamento, pois trouxe uma nova necessidade que exigiu análise de impacto e revisão do planejamento.

## 4. Decisões e pendências

### Decisões tomadas

- Adotar a abordagem Ágil para o ciclo de vida do projeto.
- Utilizar Kanban para organizar e acompanhar as atividades.
- Estabelecer um limite WIP de três tarefas em andamento.
- Definir Yudi como Product Owner, João Pedro como desenvolvedor e Arthur como testador.
- Estabelecer critérios para considerar uma tarefa concluída.
- Organizar o backlog em incrementos, priorizando as funcionalidades principais do sistema.
- Analisar solicitações de mudança antes de incorporá-las ao planejamento.

### Pendências e próximos passos

- Confirmar o tamanho e o incremento do requisito B06.
- Conferir as estimativas e a distribuição completa dos requisitos no planejamento original da A8.
- Confirmar a classificação de probabilidade e impacto dos riscos R01 e R02.
- Atualizar o backlog conforme as decisões aprovadas na SM-01.
- Acompanhar o andamento das tarefas e revisar as prioridades conforme necessário.
