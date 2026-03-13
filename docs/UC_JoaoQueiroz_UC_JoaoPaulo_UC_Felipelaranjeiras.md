## UC01 — Realizar Login (UC EXEMPLO - FAZER DESSA FORMA PARA TODOS OS CASOS DE USO, NESSE MESMO DOCUMENTO)

### Ator Principal
Usuário

### Objetivo
Permitir que o usuário acesse o sistema.

### Pré-condições
- Usuário deve possuir cadastro ativo.

### Pós-condições
- Sessão iniciada com sucesso.

### Fluxo Principal
1. O usuário informa e-mail e senha.
2. O sistema valida as credenciais.
3. O sistema autentica o usuário e redireciona para a tela inicial.

### Fluxos Alternativos
- **A1 — Senha incorreta:**  
  O sistema exibe mensagem de erro.

- **A2 — Conta bloqueada:**  
  O sistema impede o login e instrui o usuário a recuperar o acesso.

### RF Relacionados
- (inserir RF aqui)

### RNF Relacionados
- (inserir RNF aqui)

### RN Relacionadas
- (inserir RN aqui)

## UC02 — Realizar Matricula

### Ator Principal
Recepcionista

### Objetivo
Permitir que o aluno se cadastre no sistema

### Pré-condições
- Aluno cadastrado no sistema

### Pós-condições
- Matricula registrada no sistema

### Fluxo Principal
1. Recepcionista acessa a aréa para a matricula
2. Seleciona o nome do novo aluno
3. Escolher plano desejado
4. Sistema registra a nova matricula 

### Fluxos Alternativos
- **A1 — Plano indisponivel:**  
  O sistema exibe mensagem de indisponibilidade.

### RF Relacionados
- RF01 - Cadastro de Aluno novo 

### RNF Relacionados
- RNF01 - Segurança de dados do aluno

### RN Relacionadas
- Só será realizada a matricula com todos os dados completos do aluno

- ## UC03 — Atualizar dados do aluno

### Ator Principal
Recepcionista

### Objetivo
Permitir que o aluno se atualize seus dados no sistema

### Pré-condições
- Aluno cadastrado no sistema

### Pós-condições
- Dados atualizados

### Fluxo Principal
1. Recepcionista busca o aluno no sistema
2. altera dados necessarios do aluno
3. Sistema salva alterações

### Fluxos Alternativos
- **A1 — Aluno não encontrado:**  
  O sistema exibe mensagem de que o Aluno não foi encontrado no sistema

### RF Relacionados
- RF01 - Atualização de dados de aluno

### RNF Relacionados
- RNF01 - Segurança dos novos dados do aluno

### RN Relacionadas
- Só será realizada a alteração de dados se o aluno for encontrado no sistema

- ## UC04 — Cancelar matricula 

### Ator Principal
Recepcionista

### Objetivo
Permitir que o aluno cancele sua matricula 

### Pré-condições
- Aluno seja matriculado

### Pós-condições
- Matricula do aluno seja cancelada

### Fluxo Principal
1. Recepcionista busca matricula 
2. Seleciona cancelar a matricula 
3. O sistema registra o cancelamento da matricula 

### Fluxos Alternativos
- **A1 — Matricula inexistence:**  
  O sistema exibe mensagem de que a matricula não existe

### RF Relacionados
- RF01 - Cancelamento da matricula 

### RNF Relacionados
- RNF01 - Remover do sistema a matricula do aluno

### RN Relacionadas 
- RN 01 - Cancelamento deve ser registrado no sistema

- ## UC05 —  Registrar Pagamento

### Ator Principal
Recepcionista

### Objetivo
Registrar o pagamento 

### Pré-condições
- Aluno matriculado 

### Pós-condições
- Pagamento registrado

### Fluxo Principal
1. Recepcionista acessa módulo financeiro.
2. Seleciona aluno.
3. Informa valor e forma de pagamento.
4. Sistema registra pagamento.

### Fluxos Alternativos
- **A1 — Pagamento recusado:**  
  O sistema exibe mensagem de erro ao realizar o pagamento.

### RF Relacionados
- RF01 - registro de pagamento

### RNF Relacionados
- RNF01 - confiabilidade em dados do pagamento

### RN Relacionadas 
- RN 01 - Pagamento deve estar vinculado a uma matrícula.

- ## UC06 —   Consultar Histórico de Pagamentos

### Ator Principal
Recepcionista

### Objetivo
Exibir o historico de pagamento do aluno

### Pré-condições
- Aluno Cadastrado 

### Pós-condições
- Historico de pagamento exibido

### Fluxo Principal
1. Usuário acessa histórico.
2. Sistema busca registros.
3. Sistema exibe lista de pagamentos.

### Fluxos Alternativos
- **A1 —Nenhum pagamento encontrado :**  
  O sistema exibe mensagem que nenhum pagamento foi encontrado no sistema 

### RF Relacionados
- RF01 - Consultar pagamento 

### RNF Relacionados
- RNF01 - confiabilidade em dados do pagamento

### RN Relacionadas 
- RN 01 - Pagamento deve estar vinculado a uma matrícula.
- 
- ## UC07 —    Validar Acesso na Catraca

### Ator Principal
Aluno
Sistema de catracas 

### Objetivo
Validar se o aluno sera liberado ou negado no sistema de catracas

### Pré-condições
- Aluno com cartão RFID.

### Pós-condições
- Acesso liberado ou negado

### Fluxo Principal
1. Aluno aproxima cartão RFID.
2. Catraca envia dados ao sistema.
3. Sistema verifica matrícula e pagamento.
4. Sistema libera ou bloqueia acesso.

### Fluxos Alternativos
- **A1 — ALuno não encontrado no sistema  :**  
  O sistema exibe mensagem que nehnum aluno com esse RFID foi encontrado no sistema 

### RF Relacionados
- RF01 - Controle de acesso
  
### RNF Relacionados
- RNF01 -  Integração com sistema externo

### RN Relacionadas 
- RN 01 -  Apenas alunos com matricula ativa podem entrar.
- 
- ## UC08 —    Bloquear Acesso por Falta de pagamento 

### Ator Principal
Sistema 

### Objetivo
Bloquear acesso de alunos que não realizaram o pagamento

### Pré-condições
- Pagamento vencido 

### Pós-condições
- Acesso bloqueado

### Fluxo Principal
1. ASistema verifica pagamentos vencidos.
2. Sistema marca aluno como não pagante
3. Sistema bloqueia acesso 


### Fluxos Alternativos
- **A1 — Pagamento regularizado   :**  
  O sistema exibe mensagem que o pegamento está em estado regularizado 

### RF Relacionados
- RF01 - Controle de pagamento 
  
### RNF Relacionados
- RNF01 -  Integração com sistema externo

### RN Relacionadas 
- RN 01 - Apenas alunos com pagamento ativo podem acessar.

- ## UC09 —    Agendar Aula

### Ator Principal
Aluno  

### Objetivo
Agendar aula 

### Pré-condições
- Aluno ativo

### Pós-condições
- Aula agendada 

### Fluxo Principal
1. Aluno acessa agenda.
2. Seleciona a aula
3. Confirma participação
4. Sistema registra agendamento de aula


### Fluxos Alternativos
- **A1 — Turma cheia    :**  
  O sistema exibe mensagem que não há mais vagas disponiveis para agendamento 

### RF Relacionados
- RF01 - Agendamento de aulas
  
### RNF Relacionados
- RNF01 - Deve possuir horarios disponiveis para agendamento 

### RN Relacionadas 
- RN 01 - Numero maximo de alunos por aula

- ## UC10 —  Cancelar agendamento de aula

### Ator Principal
Aluno  

### Objetivo
Cancelar agendamento de aula 

### Pré-condições
- Aula agendada 

### Pós-condições
- Cancelamento de aula 

### Fluxo Principal
1. Aluno acessa agenda.
2. Seleciona a aula.
3. Cancela participação.


### Fluxos Alternativos
- **A1 — Prazo expirado  :**  
  O sistema exibe mensagem que não há mais como cancelar o agendamento, pois o prazo de cancelamento ja está expirado

### RF Relacionados
- RF01 - Cancelamento de aula agendada 
  
### RNF Relacionados
- RNF01 - Deve possuir horarios disponiveis para agendamento 

### RN Relacionadas 
- RN 01 - Cancelamento permitido até certo horario

- ## UC11 —  Consultar agenda de aulas 

### Ator Principal
Aluno  

### Objetivo
Consultar horarios disponiveis para agendamento de aulas

### Pré-condições
- Aluno autenticado 

### Pós-condições
- Agenda exibida 

### Fluxo Principal
1. Aluno acessa agenda.
2. Sistema exibi agenda de aulas


### Fluxos Alternativos
- **A1 — Nenhuma aula disponivel:**  
  O sistema exibe mensagem que não há mais aulas disponiveis para agendamento 

### RF Relacionados
- RF01 - Cancelamento de aula agendada 
  
### RNF Relacionados
- RNF01 - Deve possuir horarios disponiveis para agendamento 

### RN Relacionadas 
- RN 01 - Cancelamento permitido até certo horario

- ## UC12 —  Registrar Presença em Aula
  
### Ator Principal
Instrutor   

### Objetivo
Registar presença em aula

### Pré-condições
- Aula iniciada 

### Pós-condições
- Precença registrada no sistema 

### Fluxo Principal
1. Instrutor acessa lista de alunos.
2. Instrutor marca presença.
3. Sistema salva presença.


### Fluxos Alternativos
- **A1 — Aluno não agendado :**  
  O sistema exibe mensagem que não há nenhum aluno registrado na agenda 

### RF Relacionados
- RF01 - Aluno confirma presença na aula
  
### RNF Relacionados
- RNF01 - DO aluno deve estar presente na agenda

### RN Relacionadas 
- RN 01 - Apenas alunos agendados podem confirmar presença

- ## UC13 —   Cadastrar Instrutor
  
### Ator Principal
Gerente    

### Objetivo
Cadastrar novo instrutor no sistema 

### Pré-condições
- Gerente autenticado 

### Pós-condições
- Instrutor cadastrado 

### Fluxo Principal
1. Gerente acessa cadastro.
2. Informa dados do instrutor 
3. Sistema salva cadastro 


### Fluxos Alternativos
- **A1 — Dados invalidos :**  
  O sistema exibe mensagem que os dados pra registros são invalidos 

### RF Relacionados
- RF01 - instrutor é cadastrado no sistema 
  
### RNF Relacionados
- RNF01 - Instrutor não pode possuir cadastro 

### RN Relacionadas 
- RN 01 - Instrutor deve possuir registro profissional.

- ## UC14 — Atualizar Instrutor
  
### Ator Principal
Gerente    

### Objetivo
Atualizar dados de instrutor que já tem cadastro

### Pré-condições
- Instrutor deve possuir cadastro

### Pós-condições
- Dados de instrutor atualizados 

### Fluxo Principal
1. Gerente busca instrutor 
2. Gerente atualiza dados
3. Sistema salva alterações feitas


### Fluxos Alternativos
- **A1 — Instrutor inativo :**  
  O sistema exibe mensagem que o instrutor está inativo no sistema

### RF Relacionados
- RF01 - Atualização de dados
  
### RNF Relacionados
- RNF01 - Instrutor tem que estar ativo 

### RN Relacionadas 
- RN 01 - Instrutor deve possuir registro profissional.
 
- ## UC15 — Criar Plano de Academia
  
### Ator Principal
Gerente    

### Objetivo
Criar um novo plano de academia

### Pré-condições
- Não pode pussir um plano 

### Pós-condições
- Plano criado 

### Fluxo Principal
1. Gerente abre planos
2. Gerente seleciona o plano escolhido
3. Sistema cria novo plano na academia


### Fluxos Alternativos
- **A1 — Plano indisponivel :**  
  O sistema exibe mensagem que o plano escolhido não está mais disponivel

### RF Relacionados
- RF01 - Atualização de dados
  
### RNF Relacionados
- RNF01 - Instrutor tem que estar ativo 

### RN Relacionadas 
- RN 01 - Instrutor deve possuir registro profissional.
 
- ## UC16 — Atualizar Plano
  
### Ator Principal
Gerente    

### Objetivo
Atualizar plano já ecistente no sistema

### Pré-condições
- Gerente autenticado no sistema.

### Pós-condições
- Informações do plano atualizadas.

### Fluxo Principal
1.Gerente acessa o módulo de planos.
2.Sistema exibe lista de planos cadastrados.
3.Gerente seleciona um plano.
4.Gerente altera informações (valor, duração, benefícios).
5.Gerente confirma atualização.
6.Sistema valida os dados.
7.Sistema salva as alterações.


### Fluxos Alternativos
- **A1 — Plano não encontrado :**  
  O sistema exibe mensagem que o plano escolhido não foi encontrado no sistema

### RF Relacionados
- RF01 -  Atualização de planos
- 
### RNF Relacionados
- RNF01 -Integridade de dados

### RN Relacionadas 
- RN 01 - Todo plano deve possuir valor e duração definidos.

- ## UC17 —  Registrar Avaliação Física
  
### Ator Principal
Instrutor    

### Objetivo
registrar nova avaliação fisica

### Pré-condições
- Instrutor autenticado.

### Pós-condições
- Avaliação fisica registrada no sistema

### Fluxo Principal
1.Instrutor acessa módulo de avaliação física.
2.Instrutor busca o aluno.
3.Sistema exibe dados do aluno.
4.Instrutor registra informações:
5.Instrutor confirma registro.
6.Sistema salva avaliação.

### Fluxos Alternativos
- **A1 — Aluno não encontrado :**  
  O sistema exibe mensagem qde erro ao procurar aluno

### RF Relacionados
- RF01 -  Registro de avaliação física
- 
### RNF Relacionados
- RNF01 - Confiabilidade dos dados

### RN Relacionadas 
- RN 01 - Avaliação deve registrar data e instrutor responsável.

- ## UC18 —  Consultar Histórico de Avaliações
  
### Ator Principal
Instrutor 
Aluno

### Objetivo
Consultar novo historico de avaliação

### Pré-condições
- Aluno cadastrado

### Pós-condições
- Historico exibido

### Fluxo Principal
1.Usuário acessa histórico de avaliações.
2.Sistema consulta o banco de dados.
3.Sistema exibe lista de avaliações.

### Fluxos Alternativos
- **A1 — Nenhuma avaliação encontrada :**  
  O sistema exibe mensagem que nenhuma avaliação foi encontrada
  
### RF Relacionados
- RF01 -  Consulta de avaliações físicas
- 
### RNF Relacionados
- RNF01 - Desempenho na consulta

### RN Relacionadas 
- RN 01 - Avaliações devem ficar armazenadas para histórico.

- ## UC19 —  CGerar Relatório de Alunos
  
### Ator Principal
gerente

### Objetivo
Gerar novo relatório de alunos

### Pré-condições
- Gerente autenticado.

### Pós-condições
- Relatorio autenticado e exibido

### Fluxo Principal
1.Gerente acessa módulo de relatórios.
2.Seleciona relatório de alunos.
3.Define filtros (ativo, inativo, plano).
4.Sistema processa informações.
5.Sistema gera relatório.
6.Sistema exibe relatório na tela.

### Fluxos Alternativos
- **A1 — Nenhum registro encontrado :**  
  O sistema exibe mensagem de falta de dados no registro
  
### RF Relacionados
- RF01 -  Geração de relatórios de alunos
- 
### RNF Relacionados
- RNF01 -  Desempenho na geração de relatórios

### RN Relacionadas 
- RN 01 - Relatórios devem permitir filtragem de dados.

- ## UC20 —  Gerar Relatório Financeiro
  
### Ator Principal
Gerente

### Objetivo
Gerar novo relatório financeiro

### Pré-condições
-Gerente autenticado.

### Pós-condições
- Relatório financeiro gerado.

### Fluxo Principal
1.Gerente acessa módulo financeiro.
2.Seleciona opção Relatório Financeiro.
3.Define período de análise.
4.Sistema consulta pagamentos registrados.
5.Sistema calcula receitas do período.
6.Sistema gera relatório financeiro.
7.Sistema exibe relatório.

### Fluxos Alternativos
- **A1 —  Período inválido :**  
  O sistema exibe mensagem de falta de correção de periodo
### RF Relacionados
- RF01 -  Sistema solicita correção do período.
- 
### RNF Relacionados
- RNF01 -  Desempenho e processamento de dados

### RN Relacionadas 
- RN 01 - Relatórios financeiros devem considerar apenas pagamentos confirmados.
