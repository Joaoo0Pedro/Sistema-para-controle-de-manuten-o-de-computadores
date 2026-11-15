# 05. Qualidade, revisão e testes (A11, A12, A13)

## Plano de qualidade (A11)

### Contexto

O Sistema para Controle de Manutenção de Computadores tem como objetivo centralizar o cadastro de clientes, equipamentos, ordens de serviço, orçamentos e acompanhamento das manutenções.

O sistema será utilizado principalmente pela equipe da assistência técnica, incluindo técnicos e a responsável administrativa.

A stakeholder Marina tem grande participação nas decisões de qualidade, pois conhece a rotina do negócio e relatou problemas com informações espalhadas e interrupções no atendimento. A equipe de desenvolvimento também participa das decisões técnicas, considerando os requisitos e os riscos identificados.

### Características de qualidade priorizadas

**Adequação funcional:** foi selecionada porque o sistema precisa executar corretamente as funções de cadastro e acompanhamento das ordens de serviço. Está relacionada aos requisitos B04 e B06 e às regras de negócio relacionadas à aprovação do orçamento.

**Segurança:** é importante porque o sistema armazenará informações de clientes, computadores e ordens de serviço. Por isso, será necessário controlar o acesso a essas informações. Essa escolha está relacionada à RN02 e ao componente de armazenamento de dados definido na arquitetura. As permissões de acesso ainda precisam ser esclarecidas pela equipe.

**Eficiência de desempenho:** foi selecionada porque o sistema deverá suportar oito usuários simultâneos, conforme estabelecido na RNF01. Essa característica está relacionada à capacidade do sistema funcionar adequadamente quando vários usuários realizam operações ao mesmo tempo.

### Tabela do plano de qualidade

| Característica | Subcaracterística | Por que importa | Métrica | Meta | Como verificar | Responsável | Quando |
|---|---|---|---|---|---|---|---|
| Adequação funcional | Correção funcional | Garante que as informações serão salvas e o sistema poderá cumprir sua função. | Conclusão de cadastros e orçamentos. | Cadastros de clientes, máquinas e funcionários salvos corretamente em 100% das tentativas. | Testagem do sistema pela equipe. | Arthur – Tester e revisão. | Primeiro incremento. |
| Segurança | Confiabilidade (conforme classificação da A11) | Os acessos devem ser realizados somente por pessoal autorizado. | Tentativa de acesso ao menu inicial. | 100% dos acessos devem exigir login e senha. | Tentativas de acesso antes da utilização definitiva. | Arthur – Tester e revisão. | Primeiro incremento. |
| Eficiência de desempenho | Comportamento temporal | O atendimento e os cadastros devem ser rápidos para garantir a satisfação dos clientes. | Tempo para concluir a criação de um cadastro ou ordem de serviço. | 90% dos carregamentos realizados em até 1,5 segundo. | Lighthouse e testes nos dispositivos dos funcionários. | João Pedro – Front-end. | Segundo incremento. |

### Características deixadas para depois

- **Facilidade de uso:** foi deixada para depois porque o sistema já é considerado simples, embora ainda possa receber melhorias.
- **Compatibilidade:** foi deixada para etapas futuras porque a utilização em celulares e tablets não é prioridade nas etapas iniciais. O foco inicial está nos computadores utilizados pelos funcionários.

### Conflitos entre características

Foi identificado um conflito entre Compatibilidade e Eficiência de desempenho. A equipe considerou que adaptar todo o sistema para funcionar em celulares e tablets exigiria esforços adicionais.

Por isso, decidiu priorizar o funcionamento no ambiente principal, que são os computadores utilizados pelos funcionários, deixando a compatibilidade com outros dispositivos para uma etapa posterior.

### Qualidade dentro do processo

A equipe considera uma tarefa concluída quando os critérios de aceitação são atendidos, os testes previstos são executados com sucesso e o código está registrado no repositório do projeto.

Essas verificações serão realizadas principalmente na etapa **Em Teste** do Kanban, sob responsabilidade de Arthur, responsável pelos testes e pela revisão, com a colaboração dos demais integrantes quando necessário.

Se algum critério não for atendido, a tarefa retornará para **Em Desenvolvimento** até que o problema seja corrigido e testado novamente. Somente depois de cumprir os critérios estabelecidos poderá seguir para **Concluído**.

---

## Revisão (A12) — proposta para o projeto

### Objetivo

Realizar uma revisão dos documentos e das funcionalidades do Sistema para Controle de Manutenção de Computadores, verificando se estão de acordo com os requisitos, regras de negócio, critérios de aceitação e decisões tomadas pela equipe.

### Tipo de revisão

Inspeção dos documentos do projeto e revisão funcional do sistema, utilizando uma lista de verificação baseada nos requisitos e nas regras de negócio.

### Responsáveis

- **Arthur:** responsável pela revisão e pelos testes.
- **João Pedro:** apoio na verificação da implementação.
- **Yudi:** validação dos requisitos e das decisões junto à stakeholder.

### Critérios de revisão

- Os requisitos estão documentados e coerentes com as necessidades da stakeholder.
- Os cadastros de clientes e computadores permitem registrar e consultar as informações corretamente.
- As ordens de serviço estão relacionadas aos clientes e equipamentos correspondentes.
- O orçamento precisa ser aprovado antes do início do conserto.
- Após a aprovação da SM-01, o início do conserto também depende da confirmação de pagamento de pelo menos 30%.
- O saldo restante precisa estar quitado antes da retirada do equipamento.
- O acesso ao sistema exige autenticação.
- A documentação corresponde às decisões atuais do projeto.
- Os critérios de aceitação estão claros e podem ser verificados por testes.

### Registro de pontos para revisão

| ID | Artefato | Onde | Descrição | Critério de revisão | Situação |
|---|---|---|---|---|---|
| RV01 | Plano de qualidade | Característica Segurança | A subcaracterística indicada na A11 é Confiabilidade. É necessário confirmar se essa classificação representa corretamente o controle de acesso pretendido. | A característica e a subcaracterística devem estar corretamente relacionadas. | Pendente de validação. |
| RV02 | Plano de qualidade | Eficiência de desempenho | A métrica precisa deixar claro como será medido o tempo de conclusão de um cadastro ou ordem de serviço. | A métrica deve possuir início, fim e condição de medição definidos. | Pendente de detalhamento. |
| RV03 | Requisitos não funcionais | RNF02 | A exigência de minimizar interrupções ainda precisa de um critério mensurável para permitir sua verificação. | Requisitos não funcionais devem possuir critérios de avaliação. | Pendente de definição. |
| RV04 | Documentação | Requisitos e regras de negócio | A documentação precisa refletir a alteração aprovada na SM-01, incluindo entrada de 30% e quitação do saldo antes da retirada. | Os documentos devem estar atualizados conforme as decisões aprovadas. | Pendente de conferência. |

**Observação:** os registros acima são pontos de revisão identificados durante a preparação deste dossiê. Ainda precisam ser conferidos e validados pela equipe. Não representam defeitos encontrados em uma inspeção já executada.

---

## Estratégia de testes (A13) — proposta para o projeto

### Escopo dos testes

Os testes deverão verificar as principais funcionalidades do sistema:

- Autenticação e controle de acesso.
- Cadastro de clientes.
- Cadastro e associação de computadores aos clientes.
- Criação e acompanhamento de ordens de serviço.
- Registro e aprovação de orçamentos.
- Controle de pagamento da entrada e do saldo, conforme a mudança SM-01.
- Desempenho com até oito usuários simultâneos, conforme RNF01.

### Fora do escopo inicial

- Integração com API de pagamento, pois foi considerada uma possibilidade futura.
- Lembretes automáticos de pagamento após dois dias úteis.
- Notificações automáticas à assistência após três dias úteis.
- Compatibilidade com celulares e tablets, deixada para uma etapa futura.

### Nível e tipo de teste

- **Testes funcionais:** verificar se as funcionalidades executam corretamente o que foi definido nos requisitos.
- **Testes de integração:** verificar se clientes, computadores, ordens de serviço e orçamentos estão relacionados corretamente.
- **Testes de segurança:** verificar se usuários sem autenticação conseguem acessar as funcionalidades protegidas.
- **Testes de desempenho:** verificar o comportamento do sistema durante operações e com usuários simultâneos.
- **Testes de regressão:** repetir os testes das funcionalidades afetadas sempre que uma alteração for realizada.

### Técnicas de teste

- **Partição de equivalência:** testar situações válidas e inválidas, como dados preenchidos corretamente ou campos obrigatórios vazios.
- **Análise de valor limite:** verificar valores próximos ao limite de pagamento da entrada de 30% e do saldo de 70%.
- **Teste negativo:** verificar se o sistema impede operações que não atendem às regras de negócio.
- **Teste de desempenho:** observar o tempo de resposta e o comportamento do sistema com vários usuários.

### Critérios de entrada

- Funcionalidade implementada e disponível para teste.
- Requisitos e critérios de aceitação definidos.
- Ambiente de teste preparado.

### Critérios de saída

- Todos os casos de teste previstos para a funcionalidade executados.
- Nenhum defeito crítico aberto.
- Resultados registrados.
- Problemas encontrados encaminhados para correção.
- Funcionalidade aprovada conforme os critérios de aceitação.

---

## Casos de teste e execução

Os casos abaixo foram propostos a partir dos requisitos e das regras de negócio do projeto. Os resultados deverão ser preenchidos após a execução dos testes.

| ID | Requisito relacionado | Técnica | Entrada / Cenário | Resultado esperado | Resultado obtido | Status |
|---|---|---|---|---|---|---|
| CT01 | Login / Segurança | Teste positivo | Informar usuário e senha válidos. | O sistema permite o acesso. | Não executado. | Pendente |
| CT02 | Login / Segurança | Teste negativo | Tentar acessar com senha incorreta ou sem autenticação. | O sistema bloqueia o acesso. | Não executado. | Pendente |
| CT03 | B02 – Clientes | Partição de equivalência | Cadastrar um cliente com os dados obrigatórios preenchidos. | O cliente é cadastrado e suas informações ficam disponíveis para consulta. | Não executado. | Pendente |
| CT04 | B03 – Computadores | Teste de integração | Cadastrar um computador e associá-lo a um cliente existente. | O equipamento fica relacionado ao cliente correto. | Não executado. | Pendente |
| CT05 | B04 – Ordens de serviço | Teste funcional | Criar uma ordem de serviço para um computador cadastrado. | A ordem de serviço é registrada e relacionada ao equipamento e cliente correspondentes. | Não executado. | Pendente |
| CT06 | RN01 / SM-01 | Teste negativo | Cliente aprova o orçamento, mas não realiza o pagamento da entrada. | O sistema não permite iniciar o conserto. | Não executado. | Pendente |
| CT07 | RN01 / SM-01 | Teste positivo | Cliente paga e tem confirmada a entrada de 30% do orçamento. | O pagamento é registrado e o conserto pode ser iniciado. | Não executado. | Pendente |
| CT08 | RN01 / SM-01 | Partição de equivalência | Cliente opta pelo pagamento integral antecipado. | O pagamento integral é registrado e o conserto pode ser iniciado. | Não executado. | Pendente |
| CT09 | RN01 / SM-01 | Teste negativo | Cliente pagou somente a entrada e tenta retirar o equipamento. | O sistema não permite a retirada enquanto houver saldo pendente. | Não executado. | Pendente |
| CT10 | RN01 / SM-01 | Teste positivo | Cliente quita os 70% restantes antes da retirada. | O pagamento é registrado e a retirada pode ser autorizada. | Não executado. | Pendente |
| CT11 | RNF01 | Teste de desempenho | Oito usuários realizam operações simultaneamente. | O sistema continua funcionando corretamente, sem interrupções que impeçam as operações. | Não executado. | Pendente |
| CT12 | Plano de qualidade / desempenho | Medição de tempo | Realizar cadastros e criação de ordens de serviço. | Pelo menos 90% dos carregamentos devem ocorrer em até 1,5 segundo, conforme a meta da A11. | Não executado. | Pendente |

### Observações sobre os testes

- Os testes CT06 a CT10 consideram a decisão de aprovação parcial da SM-01.
- A confirmação de pagamento será manual nesta primeira etapa.
- Os lembretes automáticos e as notificações adiados não fazem parte dos testes atuais.
- O teste CT11 deverá ser complementado com um critério de medição mais específico para a RNF02.
- Os testes ainda não foram executados. Os resultados deverão ser atualizados pela equipe conforme a implementação do sistema.

### Cobertura dos requisitos

A cobertura será acompanhada conforme os casos de teste forem executados.

| Área | Casos relacionados | Situação |
|---|---|---|
| Autenticação e segurança | CT01 e CT02 | Pendente de execução |
| Cadastro de clientes | CT03 | Pendente de execução |
| Cadastro de computadores | CT04 | Pendente de execução |
| Ordens de serviço | CT05 | Pendente de execução |
| Orçamento e pagamento | CT06 a CT10 | Pendente de execução |
| Desempenho | CT11 e CT12 | Pendente de execução |

**Nota:** a cobertura apresentada representa os casos de teste planejados neste documento, não uma cobertura já comprovada por execução.

