# Casos de Uso — Sistema FitPass
Aluno: Paulo Teixeira

---

# UC01 — Validar entrada

![UC01](diagrams/1.png)

## Atores
Aluno  
Sistema da Catraca (API)

## Descrição
Permite validar a entrada de um aluno na academia através da catraca.

## Pré-condições
- O aluno deve estar cadastrado no sistema
- O aluno deve possuir matrícula ativa

## Fluxo Principal
1. O aluno aproxima o cartão ou identificador da catraca
2. A catraca envia a identificação do aluno ao sistema
3. O sistema verifica a situação da matrícula
4. O sistema retorna autorização de acesso
5. A catraca libera a entrada

## Fluxos Alternativos

### A1 — Matrícula inválida
3a. O sistema identifica matrícula inválida ou vencida  
4a. O sistema nega autorização  
5a. A catraca mantém bloqueio  

## Pós-condições
- A entrada do aluno é registrada no sistema

---

# UC02 — Cadastrar aluno

![UC02](diagrams/2.png)

## Atores
Recepcionista

## Descrição
Permite registrar um novo aluno no sistema da academia.

## Pré-condições
- Recepcionista autenticado no sistema

## Fluxo Principal
1. Recepcionista seleciona a opção cadastrar aluno
2. Sistema solicita dados do aluno
3. Recepcionista informa os dados
4. Sistema valida as informações
5. Sistema registra o aluno no banco de dados

## Pós-condições
- Aluno cadastrado no sistema

---

# UC03 — Atualizar dados do aluno

![UC03](diagrams/3.png)

## Atores
Recepcionista

## Descrição
Permite atualizar informações cadastrais de um aluno.

## Pré-condições
- Aluno previamente cadastrado

## Fluxo Principal
1. Recepcionista pesquisa o aluno
2. Sistema exibe os dados
3. Recepcionista altera as informações necessárias
4. Sistema valida os dados
5. Sistema salva as alterações

---

# UC04 — Consultar cadastro de aluno

![UC04](diagrams/4.png)

## Atores
Recepcionista

## Descrição
Permite visualizar informações cadastrais de um aluno.

## Fluxo Principal
1. Recepcionista pesquisa o aluno
2. Sistema recupera os dados
3. Sistema exibe as informações do aluno

---

# UC05 — Registrar pagamento

![UC05](diagrams/5.png)

## Atores
Recepcionista

## Descrição
Permite registrar o pagamento de uma mensalidade.

## Fluxo Principal
1. Recepcionista seleciona aluno
2. Sistema exibe mensalidades pendentes
3. Recepcionista registra pagamento
4. Sistema confirma pagamento
5. Sistema atualiza status financeiro do aluno

---

# UC06 — Consultar histórico de pagamentos

![UC06](diagrams/6.png)

## Atores
Recepcionista

## Descrição
Permite visualizar o histórico de pagamentos de um aluno.

## Fluxo Principal
1. Recepcionista seleciona aluno
2. Sistema consulta histórico
3. Sistema exibe lista de pagamentos

---

# UC07 — Verificar inadimplência

![UC07](diagrams/7.png)

## Atores
Recepcionista

## Descrição
Permite verificar se um aluno possui pagamentos em atraso.

## Fluxo Principal
1. Recepcionista seleciona aluno
2. Sistema verifica pagamentos pendentes
3. Sistema informa situação financeira

---

# UC08 — Emitir comprovante de pagamento

![UC08](diagrams/8.png)

## Atores
Recepcionista

## Descrição
Permite emitir comprovante de pagamento de mensalidade.

## Fluxo Principal
1. Recepcionista seleciona pagamento
2. Sistema gera comprovante
3. Sistema disponibiliza impressão ou download

---

# UC09 — Visualizar horários de aulas

![UC09](diagrams/9.png)

## Atores
Aluno

## Descrição
Permite ao aluno consultar horários disponíveis de aulas.

## Fluxo Principal
1. Aluno acessa lista de aulas
2. Sistema consulta agenda
3. Sistema exibe horários disponíveis

---

# UC10 — Agendar aula

![UC10](diagrams/10.png)

## Atores
Aluno

## Descrição
Permite ao aluno reservar vaga em uma aula.

## Fluxo Principal
1. Aluno escolhe aula
2. Sistema verifica vagas
3. Sistema registra reserva
4. Sistema confirma agendamento

---

# UC11 — Cancelar reserva de aula

![UC11](diagrams/11.png)

## Atores
Aluno

## Descrição
Permite cancelar reserva previamente realizada.

## Fluxo Principal
1. Aluno acessa reservas
2. Seleciona reserva
3. Sistema cancela agendamento

---

# UC12 — Consultar vagas disponíveis

![UC12](diagrams/12.png)

## Atores
Aluno

## Descrição
Permite verificar quantidade de vagas disponíveis em uma aula.

---

# UC13 — Registrar presença em aula

![UC13](diagrams/13.png)

## Atores
Instrutor

## Descrição
Permite registrar presença dos alunos na aula.

---

# UC14 — Consultar lista de alunos da aula

![UC14](diagrams/14.png)

## Atores
Instrutor

## Descrição
Permite visualizar alunos inscritos em uma aula.

---

# UC15 — Registrar avaliação física

![UC15](diagrams/15.png)

## Atores
Instrutor

## Descrição
Permite registrar avaliação física de um aluno.

---

# UC16 — Consultar histórico de avaliações

![UC16](diagrams/16.png)

## Atores
Instrutor  
Aluno

## Descrição
Permite consultar avaliações físicas anteriores.

---

# UC17 — Gerar relatório de alunos ativos

![UC17](diagrams/17.png)

## Atores
Gerente

## Descrição
Permite gerar relatório de alunos ativos na academia.

---

# UC18 — Gerar relatório de inadimplência

![UC18](diagrams/18.png)

## Atores
Gerente

## Descrição
Permite gerar relatório de alunos inadimplentes.

---

# UC19 — Consultar histórico de acessos

![UC19](diagrams/19.png)

## Atores
Gerente

## Descrição
Permite consultar histórico de entradas na academia.

---

# UC20 — Enviar notificação de vencimento

![UC20](diagrams/20.png)

## Atores
Sistema

## Descrição
Permite enviar notificação automática de vencimento de mensalidade.

## Fluxo Principal
1. Sistema verifica mensalidades próximas do vencimento
2. Sistema identifica alunos afetados
3. Sistema envia notificação
