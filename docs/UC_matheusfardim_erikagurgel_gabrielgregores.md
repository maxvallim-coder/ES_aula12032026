## UC01 — Realizar Login

### Atores
Usuário

### Pré-condições
- Usuário cadastrado no sistema.

### Pós-condições
- Sessão iniciada no sistema.

### Fluxo Principal
1. O usuário acessa a tela de login.
2. O usuário informa e-mail/CPF e senha.
3. O sistema valida as credenciais.
4. O sistema identifica o perfil do usuário.
5. O sistema redireciona para o painel principal.

### Fluxos Alternativos
**A1 — Credenciais inválidas**
1. O sistema identifica que os dados são inválidos.
2. O sistema exibe mensagem de erro.

### Requisitos Funcionais Relacionados
- RF001 - Autenticação de usuário

### Requisitos Não Funcionais Relacionados
- RNF001 - Tempo máximo de resposta de login: 2 segundos  
- RNF002 - Senhas devem ser armazenadas com criptografia

### Regras de Negócio Relacionadas
- RN001 - O sistema permite no máximo 5 tentativas de login consecutivas.

---

## UC02 — Cadastrar Aluno

### Atores
Recepcionista

### Pré-condições
- Recepcionista autenticada.

### Pós-condições
- Aluno registrado no sistema.

### Fluxo Principal
1. A recepcionista acessa o menu "Cadastrar Aluno".
2. O sistema apresenta formulário de cadastro.
3. A recepcionista preenche os dados.
4. O sistema valida as informações.
5. O sistema salva o cadastro.

### Fluxos Alternativos
**A1 — CPF já cadastrado**
1. O sistema identifica CPF duplicado.
2. O sistema exibe mensagem informando o erro.

### Requisitos Funcionais Relacionados
- RF002 - Cadastro de alunos

### Requisitos Não Funcionais Relacionados
- RNF003 - Dados devem ser armazenados em banco de dados seguro.

### Regras de Negócio Relacionadas
- RN002 - Cada CPF pode estar associado a apenas um aluno.

---

## UC03 — Consultar Perfil do Aluno

### Atores
Recepcionista, Instrutor

### Pré-condições
- Usuário autenticado.

### Pós-condições
- Informações do aluno exibidas.

### Fluxo Principal
1. O usuário acessa a busca de alunos.
2. O usuário informa nome ou CPF.
3. O sistema lista os resultados encontrados.
4. O usuário seleciona o aluno.
5. O sistema exibe os dados completos.

### Fluxos Alternativos
**A1 — Aluno não encontrado**
1. O sistema informa que não encontrou registros.

### Requisitos Funcionais Relacionados
- RF003 - Consulta de aluno

### Requisitos Não Funcionais Relacionados
- RNF004 - Consulta deve ocorrer em até 2 segundos.

### Regras de Negócio Relacionadas
- RN003 - Apenas funcionários podem visualizar dados completos.

---

## UC04 — Cadastrar Plano de Academia

### Atores
Gerente

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Plano disponível para matrícula.

### Fluxo Principal
1. O gerente acessa gestão de planos.
2. O gerente seleciona novo plano.
3. O gerente informa nome, preço e duração.
4. O sistema salva o plano.

### Fluxos Alternativos
**A1 — Dados inválidos**
1. O sistema solicita correção.

### Requisitos Funcionais Relacionados
- RF004 - Gestão de planos

### Requisitos Não Funcionais Relacionados
- RNF005 - Disponibilidade do sistema de 99%.

### Regras de Negócio Relacionadas
- RN004 - Todo plano deve possuir valor e duração definidos.

---

## UC05 — Realizar Matrícula em Plano

### Atores
Recepcionista

### Pré-condições
- Aluno cadastrado  
- Plano cadastrado

### Pós-condições
- Matrícula ativa.

### Fluxo Principal
1. A recepcionista busca o aluno.
2. Seleciona vincular plano.
3. Escolhe plano e data de início.
4. O sistema registra a matrícula.

### Fluxos Alternativos
**A1 — Plano indisponível**
- Sistema informa erro.

### Requisitos Funcionais Relacionados
- RF005 - Matrícula em planos

### Requisitos Não Funcionais Relacionados
- RNF006 - Operação registrada em log.

### Regras de Negócio Relacionadas
- RN005 - Um aluno só pode ter uma matrícula ativa.

---

## UC06 — Registrar Pagamento

### Atores
Recepcionista

### Pré-condições
- Aluno com mensalidade pendente.

### Pós-condições
- Pagamento registrado.

### Fluxo Principal
1. Recepcionista acessa financeiro.
2. Seleciona parcela.
3. Informa forma de pagamento.
4. Sistema confirma pagamento.

### Fluxos Alternativos
**A1 — Pagamento recusado**
- Sistema informa falha.

### Requisitos Funcionais Relacionados
- RF006 - Controle financeiro

### Requisitos Não Funcionais Relacionados
- RNF007 - Registro financeiro seguro.

### Regras de Negócio Relacionadas
- RN006 - Pagamentos devem gerar comprovante.

---

## UC07 — Vincular TAG RFID

### Atores
Recepcionista

### Pré-condições
- Aluno cadastrado.

### Pós-condições
- TAG vinculada ao aluno.

### Fluxo Principal
1. Recepcionista acessa perfil do aluno.
2. Seleciona vincular TAG.
3. Aproxima TAG do leitor.
4. Sistema registra código.

### Fluxos Alternativos
**A1 — TAG já vinculada**
- Sistema impede duplicação.

### Requisitos Funcionais Relacionados
- RF007 - Integração RFID

### Requisitos Não Funcionais Relacionados
- RNF008 - Comunicação com hardware em tempo real.

### Regras de Negócio Relacionadas
- RN007 - Cada TAG pertence a apenas um aluno.

---

## UC08 — Validar Acesso na Catraca

### Atores
Sistema de Catraca

### Pré-condições
- TAG aproximada do leitor.

### Pós-condições
- Entrada registrada.

### Fluxo Principal
1. Sistema lê TAG.
2. Busca aluno.
3. Verifica status.
4. Libera catraca.

### Fluxos Alternativos
**A1 — Matrícula inativa**
- Acesso negado.

### Requisitos Funcionais Relacionados
- RF008 - Controle de acesso

### Requisitos Não Funcionais Relacionados
- RNF009 - Tempo de resposta inferior a 1 segundo.

### Regras de Negócio Relacionadas
- RN008 - Apenas alunos ativos podem entrar.

---

## UC09 — Bloquear Acesso por Inadimplência

### Atores
Sistema

### Pré-condições
- Aluno com pagamento atrasado.

### Pós-condições
- Acesso negado.

### Fluxo Principal
1. Sistema detecta atraso.
2. Sistema bloqueia acesso.

### Fluxos Alternativos
**A1 — Pagamento regularizado**
- Sistema libera acesso.

### Requisitos Funcionais Relacionados
- RF009 - Controle de inadimplência

### Requisitos Não Funcionais Relacionados
- RNF010 - Atualização automática do status.

### Regras de Negócio Relacionadas
- RN009 - Tolerância de atraso de 5 dias.

---

## UC10 — Agendar Aula Coletiva

### Atores
Aluno

### Pré-condições
- Aluno autenticado.

### Pós-condições
- Vaga reservada.

### Fluxo Principal
1. Aluno acessa agenda.
2. Escolhe aula.
3. Confirma agendamento.

### Fluxos Alternativos
**A1 — Turma lotada**
- Sistema oferece lista de espera.

### Requisitos Funcionais Relacionados
- RF010 - Agendamento de aulas

### Requisitos Não Funcionais Relacionados
- RNF011 - Sistema disponível via app.

### Regras de Negócio Relacionadas
- RN010 - Cada aula possui limite de vagas.

---

## UC11 — Cancelar Agendamento

### Atores
Aluno

### Pré-condições
- Agendamento existente.

### Pós-condições
- Vaga liberada.

### Fluxo Principal
1. Aluno acessa agendamentos.
2. Seleciona cancelar.
3. Sistema confirma operação.

### Fluxos Alternativos
**A1 — Prazo expirado**
- Cancelamento bloqueado.

### Requisitos Funcionais Relacionados
- RF011 - Cancelamento de aula

### Requisitos Não Funcionais Relacionados
- RNF012 - Atualização em tempo real.

### Regras de Negócio Relacionadas
- RN011 - Cancelamento permitido até X horas antes.

---

## UC12 — Registrar Presença

### Atores
Instrutor

### Pré-condições
- Aula em andamento.

### Pós-condições
- Presença registrada.

### Fluxo Principal
1. Instrutor acessa lista.
2. Marca presença.
3. Salva dados.

### Fluxos Alternativos
**A1 — Aluno extra**
- Instrutor adiciona manualmente.

### Requisitos Funcionais Relacionados
- RF012 - Controle de presença

### Requisitos Não Funcionais Relacionados
- RNF013 - Interface simples para uso rápido.

### Regras de Negócio Relacionadas
- RN012 - Apenas instrutores podem registrar presença.

---

## UC13 — Criar Ficha de Treino

### Atores
Instrutor

### Pré-condições
- Aluno ativo.

### Pós-condições
- Treino registrado.

### Fluxo Principal
1. Instrutor seleciona aluno.
2. Cria treino.
3. Define exercícios.
4. Salva ficha.

### Fluxos Alternativos
**A1 — Reutilizar treino**
- Instrutor copia ficha anterior.

### Requisitos Funcionais Relacionados
- RF013 - Prescrição de treino

### Requisitos Não Funcionais Relacionados
- RNF014 - Suporte a biblioteca de exercícios.

### Regras de Negócio Relacionadas
- RN013 - Treinos devem possuir ao menos um exercício.

---

## UC14 — Visualizar Ficha de Treino

### Atores
Aluno

### Pré-condições
- Treino cadastrado.

### Pós-condições
- Treino exibido.

### Fluxo Principal
1. Aluno acessa "Meu Treino".
2. Sistema mostra exercícios.

### Fluxos Alternativos
**A1 — Treino inexistente**
- Sistema informa ausência.

### Requisitos Funcionais Relacionados
- RF014 - Consulta de treino

### Requisitos Não Funcionais Relacionados
- RNF015 - Interface adaptada para celular.

### Regras de Negócio Relacionadas
- RN014 - Apenas o próprio aluno pode visualizar.

---

## UC15 — Registrar Avaliação Física

### Atores
Instrutor

### Pré-condições
- Aluno presente.

### Pós-condições
- Avaliação registrada.

### Fluxo Principal
1. Instrutor inicia avaliação.
2. Insere medidas.
3. Sistema calcula resultados.

### Fluxos Alternativos
**A1 — Dados incompletos**
- Sistema solicita correção.

### Requisitos Funcionais Relacionados
- RF015 - Avaliação física

### Requisitos Não Funcionais Relacionados
- RNF016 - Cálculos automáticos confiáveis.

### Regras de Negócio Relacionadas
- RN015 - Avaliações devem possuir data registrada.

---

## UC16 — Visualizar Histórico de Avaliações

### Atores
Aluno

### Pré-condições
- Avaliações existentes.

### Pós-condições
- Histórico exibido.

### Fluxo Principal
1. Aluno acessa evolução.
2. Sistema gera gráficos.

### Fluxos Alternativos
**A1 — Sem avaliações**
- Sistema informa ausência.

### Requisitos Funcionais Relacionados
- RF016 - Dashboard de evolução

### Requisitos Não Funcionais Relacionados
- RNF017 - Geração gráfica rápida.

### Regras de Negócio Relacionadas
- RN016 - Dados históricos não podem ser alterados.

---

## UC17 — Gerar Relatório de Faturamento

### Atores
Gerente

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Relatório exibido ou exportado.

### Fluxo Principal
1. Gerente acessa relatórios.
2. Define período.
3. Sistema gera relatório.

### Fluxos Alternativos
**A1 — Período inválido**
- Sistema solicita correção.

### Requisitos Funcionais Relacionados
- RF017 - Relatórios financeiros

### Requisitos Não Funcionais Relacionados
- RNF018 - Exportação em PDF.

### Regras de Negócio Relacionadas
- RN017 - Apenas gerente pode acessar relatórios financeiros.

---

## UC18 — Consultar Relatório de Evasão

### Atores
Gerente

### Pré-condições
- Dados disponíveis.

### Pós-condições
- Estatísticas exibidas.

### Fluxo Principal
1. Gerente acessa relatório.
2. Sistema calcula evasão.

### Fluxos Alternativos
**A1 — Dados insuficientes**
- Sistema informa erro.

### Requisitos Funcionais Relacionados
- RF018 - Análise de churn

### Requisitos Não Funcionais Relacionados
- RNF019 - Processamento analítico otimizado.

### Regras de Negócio Relacionadas
- RN018 - Cálculo baseado em alunos que não renovaram.

---

## UC19 — Alterar Senha

### Atores
Usuário

### Pré-condições
- Usuário autenticado.

### Pós-condições
- Nova senha salva.

### Fluxo Principal
1. Usuário acessa segurança.
2. Informa senha atual.
3. Informa nova senha.
4. Sistema valida e salva.

### Fluxos Alternativos
**A1 — Senha atual incorreta**
- Sistema bloqueia alteração.

### Requisitos Funcionais Relacionados
- RF019 - Segurança da conta

### Requisitos Não Funcionais Relacionados
- RNF020 - Senhas criptografadas.

### Regras de Negócio Relacionadas
- RN019 - Senha mínima de 8 caracteres.

---

## UC20 — Cancelar Matrícula

### Atores
Gerente, Recepcionista

### Pré-condições
- Matrícula ativa.

### Pós-condições
- Matrícula encerrada.

### Fluxo Principal
1. Funcionário busca aluno.
2. Seleciona cancelar matrícula.
3. Sistema verifica débitos.
4. Sistema encerra vínculo.

### Fluxos Alternativos
**A1 — Débito pendente**
- Sistema solicita pagamento.

### Requisitos Funcionais Relacionados
- RF020 - Encerramento de matrícula

### Requisitos Não Funcionais Relacionados
- RNF021 - Registro de auditoria.

### Regras de Negócio Relacionadas
- RN020 - Cancelamentos devem registrar motivo.

### DUC_1_matheusfardim_erikagurgel_gabrielgregores
<img width="701" height="1655" alt="image" src="https://github.com/user-attachments/assets/91e3dbac-0820-4bf0-94a9-615e032a4e18" />
