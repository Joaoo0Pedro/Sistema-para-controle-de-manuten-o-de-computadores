# 06. Mudança e evolução (A14, A15)

## Solicitação de mudança SM-01

| ID | Solicitante | Data | Descrição (nas palavras do solicitante) | Motivo | Urgência |
|---|---|---|---|---|---|
| SM-01 | Marina (stakeholder) | 11/11/2026 | "Eu gostaria que, quando o cliente aprovasse o orçamento, ele também precisasse confirmar o pagamento de uma entrada antes de a gente começar o conserto." | Evitar que clientes aprovem o orçamento e depois demorem para pagar, ocupando espaço na assistência e atrasando outros serviços. | Alta |

### Perguntas de esclarecimento

1. **Qual deve ser o valor da entrada?**  
   Resposta: 30% do valor total do orçamento. O cliente também poderá optar pelo pagamento integral antecipado.

2. **O que acontece se o cliente aprovar o orçamento, mas não realizar o pagamento da entrada?**  
   Resposta: A assistência aguardará até três dias úteis. Após dois dias úteis, o cliente deverá receber um lembrete de pagamento pendente. Após três dias úteis, a assistência deverá ser avisada para entrar em contato com o cliente. Não haverá cancelamento automático.

3. **Quando o conserto poderá começar e quando o restante deverá ser pago?**  
   Resposta: O conserto somente poderá começar após a confirmação do pagamento de pelo menos 30% do orçamento. Os 70% restantes deverão ser pagos antes da retirada do equipamento.

### Linha de base antes da mudança

A versão de referência anterior à solicitação SM-01 deverá ser identificada no histórico de versões do projeto. A equipe ainda precisa confirmar o registro dessa linha de base.

## Análise de impacto (seguindo a matriz)

| Item afetado | Como está | Mudança necessária | Esforço | Risco |
|---|---|---|---|---|
| RN01 | O conserto pode prosseguir após a aprovação do orçamento. | Exigir a confirmação do pagamento de pelo menos 30% antes do início do serviço. | M | Iniciar o conserto sem a confirmação do pagamento. |
| B04 – Ordens de serviço | Permite registrar e acompanhar os serviços de manutenção. | Considerar a confirmação da entrada antes de permitir o início do conserto. | M | A ordem de serviço avançar sem o pagamento confirmado. |
| B05 – Status da ordem de serviço | Permite acompanhar o andamento da manutenção. | Considerar a situação do pagamento no acompanhamento da ordem de serviço. | M | Exibir informações incorretas sobre a situação do serviço. |
| B06 – Orçamento e aprovação | Permite registrar o orçamento e a aprovação do cliente. | Registrar a entrada de 30%, a possibilidade de pagamento integral e o saldo restante. | G | Erros no registro dos valores pagos e pendentes. |

**Itens conferidos e sem mudança de escopo:** integração com API de pagamento. Essa integração permanece como possibilidade futura e não faz parte da implementação atual.

## Alternativas e decisão

| Alternativa | Prós | Contras |
|---|---|---|
| Aprovar toda a solicitação | Atende completamente ao pedido da Marina, incluindo lembretes e notificações automáticas. | Aumenta o esforço de desenvolvimento e a quantidade de funcionalidades e testes. |
| Aprovar parcialmente | Resolve o principal problema com menor esforço, permitindo controlar os pagamentos manualmente. | A assistência ainda precisará acompanhar manualmente os pagamentos pendentes. |
| Adiar a mudança | Mantém o planejamento atual e evita alterações imediatas. | O problema apresentado pela stakeholder continua sem solução nesta etapa. |

**Decisão do PO:** Yudi – Product Owner (PO).

**Decisão:** aprovação parcial da solicitação SM-01.

A equipe decidiu implementar a entrada de 30% antes do início do conserto, a possibilidade de pagamento integral antecipado e a quitação dos 70% restantes antes da retirada do equipamento.

Os lembretes automáticos ao cliente após dois dias úteis e as notificações à assistência após três dias úteis serão adiados para uma atualização futura e registrados no backlog.

A confirmação dos pagamentos será realizada manualmente nesta primeira etapa, pois a integração com uma API de pagamento não faz parte das prioridades atuais.

**Justificativa:** a aprovação parcial permite atender ao principal problema apresentado pela stakeholder sem aumentar excessivamente o esforço e o prazo de desenvolvimento.

### Implementação e testes

A mudança aprovada deverá ser incorporada aos documentos e artefatos afetados, respeitando o processo de controle de versão da equipe.

A implementação no sistema, a revisão do código e a execução dos testes ainda precisam ser confirmadas antes de registrar a mudança como concluída.

| ID | Requisito relacionado | Cenário de teste | Resultado esperado | Status |
|---|---|---|---|---|
| CT-SM01 | RN01 | Cliente aprova o orçamento e paga 30% de entrada. | O pagamento é registrado e o conserto pode ser iniciado. | A definir |
| CT-SM02 | RN01 | Cliente opta pelo pagamento integral antecipado. | O pagamento integral é registrado e o conserto pode ser iniciado. | A definir |
| CT-SM03 | RN01 | Cliente aprova o orçamento, mas não paga a entrada. | O conserto não pode ser iniciado. | A definir |
| CT-SM04 | RN01 | Cliente paga a entrada, mas ainda possui saldo pendente. | O equipamento não pode ser retirado antes da quitação do saldo. | A definir |

## Registro de dívida técnica

A atividade A14 identificou dívidas técnicas no projeto, que devem ser acompanhadas pela equipe.

| ID | Descrição | Onde | Tipo | Quadrante | Juros | Custo | Decisão | Quando |
|---|---|---|---|---|---|---|---|---|
| DT-01 | A preencher conforme registro da A14. | A confirmar | A confirmar | A confirmar | A confirmar | A confirmar | A confirmar | A confirmar |
| DT-02 | A preencher conforme registro atualizado da A14. | A confirmar | A confirmar | A confirmar | A confirmar | A confirmar | A confirmar | A confirmar |
| DT-03 | A preencher conforme registro da A14. | A confirmar | A confirmar | A confirmar | A confirmar | A confirmar | A confirmar | A confirmar |
| DT-04 | A preencher conforme registro da A14. | A confirmar | A confirmar | A confirmar | A confirmar | A confirmar | A confirmar | A confirmar |

## Riscos atualizados

| ID | Risco | Situação e acompanhamento |
|---|---|---|
| R01 | Alterações nos requisitos após novos retornos da stakeholder. | A solicitação SM-01 demonstra a possibilidade de surgirem novas necessidades durante o desenvolvimento. A equipe deve analisar os impactos antes de aprovar mudanças. |
| R02 | Atrasos no desenvolvimento devido ao volume de tarefas. | O limite WIP de três tarefas ajuda a controlar o trabalho em andamento e evitar o acúmulo de atividades. |

## Plano de manutenção

- **Como os pedidos chegam:** as solicitações são registradas, esclarecidas com a stakeholder e analisadas pela equipe antes da decisão do Product Owner.
- **Manutenção corretiva:** correção de erros identificados durante o desenvolvimento e os testes.
- **Manutenção adaptativa:** ajustes necessários para atender a mudanças nas necessidades e regras do negócio.
- **Manutenção perfectiva:** melhorias e novas funcionalidades que ampliem a utilidade do sistema.
- **Manutenção preventiva:** identificação e tratamento de dívidas técnicas para evitar problemas futuros.
- **Controle de versões:** alterações devem ser registradas no histórico do projeto, com revisão e atualização da documentação correspondente.

## Roadmap

| Agora | Próximo | Depois |
|---|---|---|
| Organizar e atualizar a documentação da solicitação SM-01. | Implementar e validar as funcionalidades aprovadas, caso ainda estejam pendentes. | Avaliar a inclusão dos lembretes automáticos e das notificações à assistência. |
| Acompanhar as dívidas técnicas identificadas na A14. | Revisar os testes e a matriz de rastreabilidade após a implementação. | Avaliar uma possível integração com API de pagamento, conforme prioridades futuras. |

## Lições aprendidas

A solicitação SM-01 mostrou a importância de esclarecer os pedidos da stakeholder antes de iniciar uma mudança. As perguntas realizadas ajudaram a definir o percentual da entrada, o momento em que o conserto pode começar e as condições para a retirada do equipamento.

A análise de impacto também demonstrou que uma mudança pode afetar diferentes partes do projeto, como requisitos, regras de negócio, ordens de serviço, orçamento e testes.

A aprovação parcial foi uma forma de atender à principal necessidade da stakeholder sem ampliar excessivamente o escopo da equipe. Isso reforçou a importância de avaliar prioridades, esforço e consequências antes de tomar decisões.
