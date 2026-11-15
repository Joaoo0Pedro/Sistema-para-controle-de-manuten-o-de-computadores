# 02. Requisitos (A4, A5)

## Histórias de usuário

| ID | História | Origem |
|---|---|---|
| HU01 | Como funcionário da assistência, quero acessar o sistema por meio de login, para utilizar as funcionalidades de acordo com minha autorização. | B01 |
| HU02 | Como funcionário, quero cadastrar e consultar clientes, para manter organizadas as informações de quem solicita os serviços. | B02 |
| HU03 | Como funcionário, quero cadastrar e consultar computadores, para manter o histórico dos equipamentos atendidos pela assistência. | B03 |
| HU04 | Como técnico, quero registrar e acompanhar ordens de serviço, para organizar os consertos e consultar o andamento das manutenções. | B04 e B05 |
| HU05 | Como responsável administrativo, quero elaborar e registrar orçamentos, para informar os valores ao cliente e obter sua aprovação antes do início do conserto. | B06 |
| HU06 | Como responsável administrativo, quero registrar a confirmação do pagamento da entrada e do saldo restante, para garantir que as condições de pagamento sejam atendidas antes do conserto e da retirada do equipamento. | SM-01 |

## Requisitos funcionais

| ID | Requisito | História relacionada |
|---|---|---|
| B01 | O sistema deve permitir o acesso dos funcionários por meio de login e autenticação. | HU01 |
| B02 | O sistema deve permitir cadastrar, consultar e gerenciar clientes. | HU02 |
| B03 | O sistema deve permitir cadastrar, consultar e gerenciar computadores, relacionando-os aos respectivos clientes. | HU03 |
| B04 | O sistema deve permitir criar e gerenciar ordens de serviço para os equipamentos cadastrados. | HU04 |
| B05 | O sistema deve permitir acompanhar o status das ordens de serviço durante o processo de manutenção. | HU04 |
| B06 | O sistema deve permitir registrar orçamentos e a aprovação ou recusa do cliente antes do início do serviço. | HU05 |
| B06 – atualização SM-01 | O sistema deverá permitir registrar o pagamento de uma entrada de 30% ou o pagamento integral antecipado, além do saldo restante de 70%, exigindo a confirmação da entrada antes do início do conserto e a quitação do saldo antes da retirada do equipamento. | HU06 |

## Requisitos não funcionais

| ID | Requisito | Característica de qualidade |
|---|---|---|
| RNF01 | O sistema deverá suportar pelo menos oito usuários simultâneos. | Eficiência de desempenho |
| RNF02 | O sistema deverá minimizar interrupções durante sua utilização. | Confiabilidade |

## Regras de negócio

| ID | Regra | Origem |
|---|---|---|
| RN01 | A manutenção somente poderá prosseguir após a aprovação do orçamento pelo cliente. | Requisito inicial do projeto |
| RN02 | O início do conserto dependerá da confirmação do pagamento de pelo menos 30% do orçamento, ou do pagamento integral antecipado. | SM-01 |
| RN03 | Os 70% restantes deverão ser pagos antes da retirada do equipamento, quando o cliente optar pelo pagamento da entrada. | SM-01 |
| RN04 | A confirmação dos pagamentos será realizada manualmente nesta primeira etapa. | Decisão do PO – SM-01 |
| RN05 | A integração com API de pagamento não faz parte do escopo atual do projeto. | Decisão da equipe |

## Critérios de aceitação

### CA01 – B01: Login

- Dado que o funcionário possui credenciais válidas, quando informar seu login e senha, então o sistema deverá permitir o acesso.
- Dado que o funcionário informe credenciais inválidas, quando tentar acessar o sistema, então o acesso deverá ser bloqueado.

### CA02 – B02: Cadastro de clientes

- Dado que o funcionário preencha os campos obrigatórios, quando confirmar o cadastro, então o sistema deverá salvar as informações do cliente.
- Dado que existam informações obrigatórias não preenchidas, quando o funcionário tentar salvar, então o sistema deverá informar que os dados precisam ser completados.

### CA03 – B03: Cadastro de computadores

- Dado que exista um cliente cadastrado, quando o funcionário registrar um computador e associá-lo a esse cliente, então o sistema deverá salvar o equipamento relacionado ao cliente correto.

### CA04 – B04 e B05: Ordens de serviço

- Dado que exista um computador cadastrado, quando o funcionário criar uma ordem de serviço, então o sistema deverá registrar as informações do atendimento.
- Dado que uma ordem de serviço esteja em andamento, quando seu status for atualizado, então o sistema deverá apresentar a situação atualizada.

### CA05 – B06: Orçamento e aprovação

- Dado que uma ordem de serviço possua um orçamento registrado, quando o cliente aprovar o orçamento, então o sistema deverá registrar a aprovação.
- Dado que o cliente recuse o orçamento, quando a decisão for registrada, então o sistema não deverá permitir que o conserto prossiga.

### CA06 – SM-01: Entrada e pagamento integral

- Dado que o cliente aprove o orçamento e realize o pagamento de 30%, quando a confirmação do pagamento for registrada, então o sistema deverá permitir o início do conserto.
- Dado que o cliente opte pelo pagamento integral antecipado, quando a confirmação do pagamento for registrada, então o sistema deverá permitir o início do conserto.
- Dado que o cliente aprove o orçamento, mas não tenha realizado o pagamento da entrada, quando o funcionário tentar iniciar o conserto, então o sistema deverá impedir o início do serviço.

### CA07 – SM-01: Saldo restante

- Dado que o cliente tenha pago somente a entrada, quando tentar retirar o equipamento com saldo pendente, então a retirada não deverá ser autorizada.
- Dado que o cliente quite o saldo restante, quando o pagamento for confirmado, então a retirada poderá ser autorizada.

## Priorização (MoSCoW)

A priorização abaixo organiza os requisitos conforme sua importância para o funcionamento do sistema e considera as decisões tomadas pela equipe.

| Prioridade | Itens | Justificativa |
|---|---|---|
| Must (Obrigatório) | B01, B02, B03, B04, B05 e B06 | São as funcionalidades principais para permitir o acesso, o cadastro de informações, o gerenciamento das ordens de serviço e o controle dos orçamentos. |
| Must (Obrigatório) | RN01 e regras aprovadas da SM-01 | São necessárias para garantir que o conserto respeite as condições de aprovação e pagamento definidas para o negócio. |
| Should (Importante) | RNF01 e RNF02 | São importantes para garantir o atendimento simultâneo dos funcionários e reduzir interrupções durante a utilização. |
| Could (Desejável) | Lembretes automáticos de pagamento e notificações à assistência. | Foram solicitados na SM-01, mas adiados para uma atualização futura. |
| Won't (Neste momento) | Integração com API de pagamento. | Foi considerada uma possibilidade futura, mas não faz parte das prioridades atuais do projeto. |

## Observações e pendências

- A SM-01 foi aprovada parcialmente pelo Product Owner. As regras de pagamento aprovadas devem ser consideradas na atualização dos requisitos e dos demais artefatos.
- Os lembretes automáticos após dois dias úteis e as notificações à assistência após três dias úteis não fazem parte do escopo atual.
- A confirmação dos pagamentos será manual nesta primeira etapa.
- A integração com API de pagamento permanece como possibilidade futura.
- A RNF02 ainda precisa de um critério mensurável para permitir a verificação de que as interrupções foram minimizadas.
- Os critérios de aceitação apresentados deverão ser validados pela equipe e ajustados conforme as funcionalidades efetivamente implementadas.
