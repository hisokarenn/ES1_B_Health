# Tabela de Classes de Equivalência
<br>
<p align="justify">Uma tabela de classe de equivalência é um instrumento usado para organizar e categorizar elementos de um conjunto em grupos que compartilham uma característica comum, ou seja, são considerados equivalentes em relação a uma propriedade específica. Essa tabela facilita a identificação e análise de conjuntos de dados, especialmente em áreas como programação, testes de software e matemática. 
<br>
<br>

# Tabela de Casos de Teste
<br>
<p align="justify">Uma tabela de casos de teste é uma ferramenta utilizada em testes de software para organizar e documentar os diferentes cenários de teste de um sistema. Ela lista condições de entrada, ações esperadas e resultados obtidos, garantindo uma cobertura abrangente dos testes. 
<br>
<br>

### Organização
<p align="justify">Foram criadas quatro personas representando os principais usuários do sistema, cada uma com cinco histórias de usuário, totalizando 20 histórias. Com base nessas histórias, foram elaboradas cinco tabelas de classes de equivalência para identificar entradas válidas e inválidas. A partir dessas tabelas, foram desenvolvidos cinco conjuntos de casos de teste equivalentes. Essa organização visa garantir a cobertura dos principais fluxos do sistema. O objetivo é validar o comportamento esperado de cada funcionalidade.
<br>
<br>
  
## PACIENTE

### H1 - Como paciente, gostaria de me cadastrar no aplicativo para que eu possa ter acesso ao aplicativo B Health.
<br>

### <p align="center">Tabela de Equivalência
  
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Nome completo preenchido|Nome preenchido (1)|Nome em branco (2)|
|Endereço preenchido|Endereço preenchido (3)|Endereço em branco (4)|
|CNS possui 15 dígitos|CNS com exatamente 15 dígitos numéricos (5)|CNS com mais de 15 dígitos (6)|
|E-mail possui formato válido|E-mail com “@” e domínio(7)|E-mail sem “@” e sem domínio (8)|
|CPF possui 11 dígitos|CPF com 11 dígitos nuéricos (9)|CPF com mais de 11 dígitos (10)|
|E-mail não utilizado anteriormente|E-mail ainda não cadastrado (11)|E-mail já cadastrado (12)|
|Todos os campos obrigatórios preenchidos|Formulário completo (13)|Campos obrigatórios não preenchidos (14)|
|Notificação de confirmação enviada com sucesso|Notificação enviada por e-mail (15)|Notificação não enviada por  erro no endereço de e-mail (16)|
<br>

### <p align="center">Tabela de Casos de Teste

|CASOS DE TESTE|CLASSES DE EQUIVALÊNCIA|ENTRADAS|RESULTADOS ESPERADOS|
|-|-|-|-|
| Caso 1             | 1, 3, 5, 7, 9, 11, 13, 15| Nome preenchido, endereço preenchido, CNS com 15 dígitos, e-mail válido, CPF com 11 dígitos, e-mail novo, todos os campos preenchidos, notificação enviada | Cadastro realizado com sucesso                                 |
| Caso 2             | 2, 3, 5, 7, 9, 11, 13, 15 | Nome em branco, endereço preenchido, CNS com 15 dígitos, e-mail válido, CPF com 11 dígitos, e-mail novo, todos os campos preenchidos, notificação enviada | Cadastro rejeitado (nome não preenchido)                       |
| Caso 3             | 1, 4, 5, 7, 9, 11, 13, 15         | Nome preenchido, endereço em branco, CNS com 15 dígitos, e-mail válido, CPF com 11 dígitos, e-mail novo, todos os campos preenchidos, notificação enviada | Cadastro rejeitado (endereço não preenchido)                  |
| Caso 4             | 1, 3, 6, 7, 9, 11, 13, 15         | Nome preenchido, endereço preenchido, CNS com mais de 15 dígitos, e-mail válido, CPF com 11 dígitos, e-mail novo, todos os campos preenchidos, notificação enviada | Cadastro rejeitado (CNS inválido)                             |
| Caso 5             | 1, 3, 5, 8, 9, 11, 13, 15         | Nome preenchido, endereço preenchido, CNS com 15 dígitos, e-mail sem “@”, CPF com 11 dígitos, e-mail novo, todos os campos preenchidos, notificação enviada | Cadastro rejeitado (e-mail mal formatado)                     |
| Caso 6             | 1, 3, 5, 7, 10, 11, 13, 15        | Nome preenchido, endereço preenchido, CNS com 15 dígitos, e-mail válido, CPF com mais de 11 dígitos, e-mail novo, todos os campos preenchidos, notificação enviada | Cadastro rejeitado (CPF inválido)                             |
| Caso 7             | 1, 3, 5, 7, 9, 12, 13, 15         | Nome preenchido, endereço preenchido, CNS com 15 dígitos, e-mail válido, CPF com 11 dígitos, e-mail já cadastrado, todos os campos preenchidos, notificação enviada | Cadastro rejeitado (e-mail já existente)                      |
| Caso 8             | 1, 3, 5, 7, 9, 11, 14, 15         | Nome preenchido, endereço preenchido, CNS com 15 dígitos, e-mail válido, CPF com 11 dígitos, e-mail novo, campos obrigatórios não preenchidos, notificação enviada | Cadastro incompleto (faltam campos obrigatórios)             |
| Caso 9             | 1, 3, 5, 7, 9, 11, 13, 16         | Nome preenchido, endereço preenchido, CNS com 15 dígitos, e-mail válido, CPF com 11 dígitos, e-mail novo, todos os campos preenchidos, erro ao enviar notificação | Falha na comunicação (e-mail de confirmação não enviado)      |
<br>

---

### H2 - Como paciente, gostaria de realizar o login no aplicativo para que eu tenha acesso aos serviços do aplicativo.
<br>

### <p align="center">Tabela de Equivalência
| CONDIÇÃO DE ENTRADA                  | CLASSES VÁLIDAS                              | CLASSES INVÁLIDAS                                     |
| ---------------------------------------- | -------------------------------------------------- | ---------------------------------------------------------- |
| Identificação via CNS ou e-mail          | CNS com 15 dígitos numéricos e e-mail válido (1)   | CNS com menos de 15 dígitos e e-mail inválido (2)          |
| Senha inserida corretamente              | Senha corresponde à cadastrada (3)                 | Senha incorreta (4)                                        |
| Clique em "Esqueci minha senha"          | Redireciona para etapa de recuperação (5)          | Nenhuma ação ocorre, pode ser erro ou botão sem função (6) |
| E-mail informado na recuperação é válido | E-mail contém "@" e domínio, e está registrado (7) | E-mail inválido (8)                                        |
| Código de verificação enviado            | Código enviado com sucesso ao e-mail informado (9) | Código não enviado, falha no sistema (10)                  |
<br>

### <p align="center">Tabela de Casos de Teste

| CASOS DE TESTE | CLASSES DE EQUIVALÊNCIA | ENTRADAS                                                            | RESULTADOS ESPERADOS                   |
| ------------------ | --------------------------- | ---------------------------------------------------------------------------- | -------------------------------------------- |
| Caso 1             | 1, 3                        | CNS com 15 dígitos e e-mail válido, senha correta                            | Login realizado com sucesso                  |
| Caso 2             | 2, 3                        | CNS com menos de 15 dígitos, e-mail inválido, senha correta                  | Login rejeitado (identificação inválida)     |
| Caso 3             | 1, 4                        | CNS com 15 dígitos e e-mail válido, senha incorreta                          | Login rejeitado (senha incorreta)            |
| Caso 4             | 1, 3, 5, 7, 9               | Clique em “Esqueci minha senha” funciona, e-mail válido e código enviado     | Recuperação de senha iniciada com sucesso    |
| Caso 5             | 1, 3, 6                     | Clique em “Esqueci minha senha” não gera resposta, usuário com dados válidos | Erro na interface (botão não funcional)      |
| Caso 6             | 1, 3, 5, 8                  | Redirecionamento correto, mas e-mail inválido                                | Recuperação rejeitada (e-mail inválido)      |
| Caso 7             | 1, 3, 5, 7, 10              | Redirecionamento correto, e-mail válido, falha no envio do código            | Recuperação falhou (erro no envio do código) |
<br>

---

### H3 - Como paciente cadastrado no aplicativo B Health, gostaria de ver o histórico de vacinas para que eu possa verificar quais vacinas já tomei.
<br>

### <p align="center">Tabela de Equivalência

| CONDIÇÃO DE ENTRADA | CLASSES VÁLIDAS| CLASSES INVÁLIDAS |
| - | - | -|
| Paciente autenticado                            | Paciente está logado no sistema (1)                             | Acesso sem login/autenticação (2)                           |
| Paciente visualiza apenas seu próprio histórico | Histórico exibido pertence ao usuário autenticado (3)           | Visualização de histórico de outro paciente (4)             |
| Histórico possui registros                      | Lista de vacinas exibida com nome e data em ordem crescente (5) | Histórico em branco sem registros (6)                       |
| Clique sobre vacina exibida                     | Exibe local de aplicação e nome do profissional (7)             | Não exibir informações adicionais ao clicar (8)             |
| Nome da vacina presente                         | Cada item do histórico possui o nome da vacina (9)              | Campo "nome da vacina" está vazio (10)                      |
| Data de aplicação válida                        | Data no formato correto e cronologicamente organizada (11)      | Data ausente (12)                                           |
| Histórico atualizado                            | Cada vacina aplicada será registrada no histórico (13)          | Histórico desatualizado mesmo após aplicação de vacina (14) |
<br>

### <p align="center">Tabela de Casos de Teste

| CASOS DE TESTE| CLASSES DE EQUIVALÊNCIA | ENTRADAS | RESULTADOS ESPERADOS|
| - | - | - | -|
| Caso 1             | 1, 3, 5, 7, 9, 11, 13       | Paciente autenticado, visualiza apenas seu histórico, registros com nome e data em ordem crescente, clique exibe local e profissional, datas válidas | Histórico exibido corretamente com todos os dados esperados   |
| Caso 2             | 2, 3, 5, 7, 9, 11, 13       | Acesso sem login, visualização correta, histórico com dados completos, clique funcional, nome da vacina e data válidos                               | Acesso negado (usuário não autenticado)                       |
| Caso 3             | 1, 4, 5, 7, 9, 11, 13       | Paciente autenticado, visualiza histórico de outro paciente, demais dados corretos                                                                   | Violação de privacidade (acesso indevido ao histórico alheio) |
| Caso 4             | 1, 3, 6, 7, 9, 11, 13       | Paciente autenticado, visualiza seu histórico, histórico em branco, clique funcional, nome da vacina e datas válidas                                 | Histórico vazio (sem registros de vacinação)                  |
| Caso 5             | 1, 3, 5, 8, 9, 11, 13       | Paciente autenticado, visualiza seu histórico com dados completos, clique sobre vacina não exibe informações adicionais                              | Informações incompletas (falha na exibição ao clicar)         |
| Caso 6             | 1, 3, 5, 7, 10, 11, 13      | Paciente autenticado, histórico completo, clique exibe dados corretos, mas nome da vacina ausente                                                    | Dados incompletos (nome da vacina ausente)                    |
| Caso 7             | 1, 3, 5, 7, 9, 12, 13       | Paciente autenticado, visualiza seu histórico, clique funcional, nome da vacina presente, mas data de aplicação está ausente                         | Dados incompletos (data não registrada)                       |
| Caso 8             | 1, 3, 5, 7, 9, 11, 14       | Paciente autenticado, histórico exibido com dados válidos, clique funcional, nome e data presentes, mas histórico não é atualizado                   | Histórico desatualizado (nova vacina não aparece)             |
<br>

---

### H4 - Como paciente, gostaria de acessar o mapa de vacinação para saber em quais unidades de saúde estão fornecendo as vacinas que preciso.
<br>

### <p align="center">Tabela de Equivalência

| CONDIÇÃO DE ENTRADA                  | CLASSES VÁLIDAS                           | CLASSES INVÁLIDAS                                     |
| ------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------------ |
| Paciente está com acesso à internet               | Conexão ativa para exibição do mapa (1)                 | Sem internet (2)                                             |
| Localização do usuário permitida no app           | Permissão de localização concedida (3)                  | Permissão de localização negada (4)                          |
| Mapa interativo é carregado corretamente          | Mapa exibido com pontos geográficos (5)                 | Mapa não aparece (6)                                         |
| Paciente aplica filtro por vacina                 | Unidades exibidas com a vacina filtrada (7)             | Nenhuma unidade corresponde ao filtro (mensagem exibida) (8) |
| Clique sobre unidade de saúde no mapa             | Exibe nome, endereço, vacinas disponíveis e horário (9) | Informações incompletas (10)                                 |
| Mapa mostra apenas unidades com vacina disponível | Unidades abertas e com a vacina procurada (11)          | Mapa mostra unidades fechadas (12)                           |
| Aplicativo mantém localização segura              | Localização não compartilhada com terceiros (13)        | Aplicativo vaza dados de localização (14)                    |
<br>

### <p align="center">Tabela de Casos de Teste

| CASOS DE TESTE | CLASSES DE EQUIVALÊNCIA | ENTRADAS                                                                                                                                                                        | RESULTADOS ESPERADOS                                          |
| -------- | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| Caso 1   | 1, 3, 5, 7, 9, 11, 13       | Conexão ativa, permissão de localização concedida, mapa carregado com pontos, filtro aplicado com resultado, clique exibe informações completas, unidades abertas, localização segura | Mapa funcional exibindo corretamente as unidades com dados completos |
| Caso 2   | 2, 3, 5, 7, 9, 11, 13       | Sem internet, localização permitida, mapa normalmente carregaria, filtro aplicado, clique funcional, unidades com vacina e abertas, localização segura                                | Falha na exibição do mapa (sem conexão)                              |
| Caso 3   | 1, 4, 5, 7, 9, 11, 13       | Internet ativa, localização negada, mapa carregado, filtro com resultado, clique funcional, unidades abertas, localização segura                                                      | Mapa não exibe unidades próximas (sem acesso à localização)          |
| Caso 4   | 1, 3, 6, 7, 9, 11, 13       | Internet ativa, localização permitida, erro no carregamento do mapa, filtro funcional, clique funcional, unidades abertas, localização segura                                         | Erro ao exibir o mapa (falha de renderização)                        |
| Caso 5   | 1, 3, 5, 8, 9, 11, 13       | Internet ativa, localização permitida, mapa carregado, filtro sem resultados, clique funcional, unidades abertas, localização segura                                                  | Nenhuma unidade encontrada com a vacina (mensagem exibida)           |
| Caso 6   | 1, 3, 5, 7, 10, 11, 13      | Internet ativa, localização permitida, mapa carregado, filtro com resultados, clique não exibe todas as informações                                                                   | Informações incompletas sobre unidade no clique                      |
| Caso 7   | 1, 3, 5, 7, 9, 12, 13       | Internet ativa, localização permitida, mapa carregado, filtro funcional, clique completo, unidades exibidas estão fechadas                                                            | Erro: unidades exibidas não estão abertas                            |
| Caso 8   | 1, 3, 5, 7, 9, 11, 14       | Internet ativa, localização permitida, mapa carregado, filtro funcional, clique completo, unidades abertas, aplicativo vaza localização                                               | Falha de privacidade (dados de localização expostos)                 |
<br>

---

### H5 - Como paciente, gostaria de receber lembretes do aplicativo de doses pendentes para que eu possa manter o controle das vacinas que eu devo tomar.
<br>

### <p align="center">Tabela de Equivalência

| CONDIÇÃO DE ENTRADA                                | CLASSES VÁLIDAS                                        | CLASSES INVÁLIDAS                                                |
| -------------------------------------------------------- | ------------------------------------------------------------ | -------------------------------------------------------------------------- |
| Vacina com próxima dose registrada no sistema            | Vacina possui nome e data de próxima dose (1)                | Nenhuma dose futura registrada (2)                                         |
| Sistema envia lembrete com antecedência mínima de 2 dias | Notificação enviada pelo menos 2 dias antes da aplicação (3) | Notificação enviada com menos de 2 dias (4)                                |
| Formato da notificação é push                            | Notificação push recebida no celular (5)                     | Notificação não enviada ao paciente (6)                                    |
| Vacina é aplicada e registrada pelo enfermeiro           | Lembretes futuros cancelados automaticamente (7)             | Lembretes continuam mesmo após confirmação da dose (8)                     |
| Paciente desativa notificações do app no celular         | Lembretes desativados corretamente (9)                       | Lembretes continuam sendo enviados mesmo com notificações desativadas (10) |
<br>

### <p align="center">Tabela de Casos de Teste

| CASOS DE TESTE | CLASSES DE EQUIVALÊNCIA | ENTRADAS                                                                                                                       | RESULTADOS ESPERADOS                                         |
| -------- | --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Caso 1   | 1, 3, 5, 7, 9               | Vacina possui próxima dose registrada, lembrete enviado com 2 dias de antecedência, push recebido, dose aplicada, lembretes cancelados | Lembrete funcional e cancelado após vacinação                      |
| Caso 2   | 2, 3, 5, 7, 9               | Nenhuma próxima dose registrada, notificação enviada corretamente, push recebido, dose aplicada, lembretes cancelados                  | Lembrete desnecessário (nenhuma dose futura prevista)              |
| Caso 3   | 1, 4, 5, 7, 9               | Próxima dose registrada, notificação enviada com menos de 2 dias, push recebido, dose aplicada, lembretes cancelados                   | Alerta enviado com atraso (fora do prazo mínimo)                   |
| Caso 4   | 1, 3, 6, 7, 9               | Próxima dose registrada, notificação enviada corretamente, push não recebido, dose aplicada, lembretes cancelados                      | Falha de envio da notificação                                      |
| Caso 5   | 1, 3, 5, 8, 9               | Próxima dose registrada, lembrete enviado corretamente, push recebido, vacina aplicada, lembretes continuam ativos                     | Erro: lembretes não cancelados após aplicação                      |
| Caso 6   | 1, 3, 5, 7, 10              | Próxima dose registrada, lembrete enviado corretamente, push recebido, vacina aplicada, notificações desativadas, lembretes continuam  | Falha: lembretes enviados mesmo com notificações desativadas       |
| Caso 7   | 1, 3, 5, 7, 9               | (Repetido do Caso 1) Vacina com próxima dose, lembrete correto, push recebido, dose aplicada, notificações ativas                      | Comportamento correto: lembrete recebido e removido após vacinação |
<br>
