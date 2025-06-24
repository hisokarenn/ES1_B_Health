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
|E-mail possui formato válido|E-mail com “@” e domínio, por exemplo:  usuario@email.com (7)|E-mail sem “@” e sem domínio (8)|
|CPF possui 11 dígitos|CPF com 11 dígitos nuéricos (9)|CPF com mais de 11 dígitos (10)|
|E-mail não utilizado anteriormente|E-mail ainda não cadastrado (11)|E-mail já cadastrado (12)|
|Todos os campos obrigatórios preenchidos|Formulário completo (13)|Campos obrigatórios não preenchidos (14)|
|Notificação de confirmação enviada com sucesso|Notificação enviada por e-mail (15)|Notificação não enviada por  erro no endereço de e-mail (16)|
<br>
<br>

### <p align="center">Tabela de Casos de Teste

|Casos de Teste|Classes de Equivalência|Entradas|Resultados Esperadas|
|-|-|-|-|
| Caso 1             | 1, 3, 5, 7, 9, 11, 13, 15         | Nome preenchido, endereço preenchido, CNS com 15 dígitos, e-mail válido, CPF com 11 dígitos, e-mail novo, todos os campos preenchidos, notificação enviada | Cadastro realizado com sucesso                                 |
| Caso 2             | 2, 3, 5, 7, 9, 11, 13, 15         | Nome em branco, endereço preenchido, CNS com 15 dígitos, e-mail válido, CPF com 11 dígitos, e-mail novo, todos os campos preenchidos, notificação enviada | Cadastro rejeitado (nome não preenchido)                       |
| Caso 3             | 1, 4, 5, 7, 9, 11, 13, 15         | Nome preenchido, endereço em branco, CNS com 15 dígitos, e-mail válido, CPF com 11 dígitos, e-mail novo, todos os campos preenchidos, notificação enviada | Cadastro rejeitado (endereço não preenchido)                  |
| Caso 4             | 1, 3, 6, 7, 9, 11, 13, 15         | Nome preenchido, endereço preenchido, CNS com mais de 15 dígitos, e-mail válido, CPF com 11 dígitos, e-mail novo, todos os campos preenchidos, notificação enviada | Cadastro rejeitado (CNS inválido)                             |
| Caso 5             | 1, 3, 5, 8, 9, 11, 13, 15         | Nome preenchido, endereço preenchido, CNS com 15 dígitos, e-mail sem “@”, CPF com 11 dígitos, e-mail novo, todos os campos preenchidos, notificação enviada | Cadastro rejeitado (e-mail mal formatado)                     |
| Caso 6             | 1, 3, 5, 7, 10, 11, 13, 15        | Nome preenchido, endereço preenchido, CNS com 15 dígitos, e-mail válido, CPF com mais de 11 dígitos, e-mail novo, todos os campos preenchidos, notificação enviada | Cadastro rejeitado (CPF inválido)                             |
| Caso 7             | 1, 3, 5, 7, 9, 12, 13, 15         | Nome preenchido, endereço preenchido, CNS com 15 dígitos, e-mail válido, CPF com 11 dígitos, e-mail já cadastrado, todos os campos preenchidos, notificação enviada | Cadastro rejeitado (e-mail já existente)                      |
| Caso 8             | 1, 3, 5, 7, 9, 11, 14, 15         | Nome preenchido, endereço preenchido, CNS com 15 dígitos, e-mail válido, CPF com 11 dígitos, e-mail novo, campos obrigatórios não preenchidos, notificação enviada | Cadastro incompleto (faltam campos obrigatórios)             |
| Caso 9             | 1, 3, 5, 7, 9, 11, 13, 16         | Nome preenchido, endereço preenchido, CNS com 15 dígitos, e-mail válido, CPF com 11 dígitos, e-mail novo, todos os campos preenchidos, erro ao enviar notificação | Falha na comunicação (e-mail de confirmação não enviado)      |
<br>
<br>

---

### H2 - Como paciente, gostaria de realizar o login no aplicativo para que eu tenha acesso aos serviços do aplicativo.
<br>

### <p align="center">Tabela de Equivalência
| **Condição de Entrada**                  | **Classes Válidas**                                | **Classes Inválidas**                                      |
| ---------------------------------------- | -------------------------------------------------- | ---------------------------------------------------------- |
| Identificação via CNS ou e-mail          | CNS com 15 dígitos numéricos e e-mail válido (1)   | CNS com menos de 15 dígitos e e-mail inválido (2)          |
| Senha inserida corretamente              | Senha corresponde à cadastrada (3)                 | Senha incorreta (4)                                        |
| Clique em "Esqueci minha senha"          | Redireciona para etapa de recuperação (5)          | Nenhuma ação ocorre, pode ser erro ou botão sem função (6) |
| E-mail informado na recuperação é válido | E-mail contém "@" e domínio, e está registrado (7) | E-mail inválido (8)                                        |
| Código de verificação enviado            | Código enviado com sucesso ao e-mail informado (9) | Código não enviado, falha no sistema (10)                  |
<br>
<br>

### <p align="center">Tabela de Casos de Teste

| **Casos de Teste** | **Classes de Equivalência** | **Entradas**                                                                 | **Resultados Esperados**                     |
| ------------------ | --------------------------- | ---------------------------------------------------------------------------- | -------------------------------------------- |
| Caso 1             | 1, 3                        | CNS com 15 dígitos e e-mail válido, senha correta                            | Login realizado com sucesso                  |
| Caso 2             | 2, 3                        | CNS com menos de 15 dígitos, e-mail inválido, senha correta                  | Login rejeitado (identificação inválida)     |
| Caso 3             | 1, 4                        | CNS com 15 dígitos e e-mail válido, senha incorreta                          | Login rejeitado (senha incorreta)            |
| Caso 4             | 1, 3, 5, 7, 9               | Clique em “Esqueci minha senha” funciona, e-mail válido e código enviado     | Recuperação de senha iniciada com sucesso    |
| Caso 5             | 1, 3, 6                     | Clique em “Esqueci minha senha” não gera resposta, usuário com dados válidos | Erro na interface (botão não funcional)      |
| Caso 6             | 1, 3, 5, 8                  | Redirecionamento correto, mas e-mail inválido                                | Recuperação rejeitada (e-mail inválido)      |
| Caso 7             | 1, 3, 5, 7, 10              | Redirecionamento correto, e-mail válido, falha no envio do código            | Recuperação falhou (erro no envio do código) |
<br>
<br>

---

### H3 - Como paciente cadastrado no aplicativo B Health, gostaria de ver o histórico de vacinas para que eu possa verificar quais vacinas já tomei.
<br>
<br>

### <p align="center">Tabela de Equivalência

H4 - Como paciente, gostaria de acessar o mapa de vacinação para saber em quais unidades de saúde estão fornecendo as vacinas que preciso.
<br>
<br>

### <p align="center">Tabela de Equivalência

H5 - Como paciente, gostaria de receber lembretes do aplicativo de doses pendentes para que eu possa manter o controle das vacinas que eu devo tomar.
<br>
<br>

### <p align="center">Tabela de Equivalência










