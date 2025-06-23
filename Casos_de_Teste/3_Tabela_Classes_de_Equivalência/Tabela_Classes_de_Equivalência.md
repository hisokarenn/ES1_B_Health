# Classes de Equivalência
<br>
<p align="justify">Tabelas de classe de equivalência, em contexto de testes de software, são ferramentas usadas para particionar um conjunto de entradas possíveis em grupos menores, onde cada grupo contém entradas que são consideradas equivalentes em termos de comportamento esperado do sistema. 
<br>
<br>

## Tabelas elaboras
<p align="justify">Cada tabela de classe de equivalência foi criada levando em cosideração todas as 20 histórias de usuário que foram especificadas no BackLog do Produto. Elas serão apresentadas a seguir:
<br>
<br>
  
### PACIENTE
H1 - Como paciente, gostaria de me cadastrar no aplicativo para que eu possa ter acesso ao aplicativo B Health.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Nome completo preenchido|Nome preenchido (1)|Nome em branco ou com caracteres especiais (2)|
|Endereço preenchido|Endereço preenchido (3)|Endereço em branco (4)|
|CNS possui 15 dígitos|CNS com exatamente 15 dígitos numéricos (5)|CNS com menos ou mais de 15 dígitos (6)|
|E-mail possui formato válido|E-mail com “@” e domínio, por exemplo:  usuario@email.com (7)|E-mail sem “@” ou sem domínio (8)|
|CPF possui 11 dígitos|CPF com 11 dígitos numéricos (9)|CPF com menos ou mais de 11 dígitos (10)|
|CPF e CNS possuem apenas números|CPF e CNS compostos apenas por dígitos (11)|CPF ou CNS contendo letras ou caracteres especiais (12)|
|E-mail não utilizado anteriormente|E-mail ainda não cadastrado (13)|E-mail já cadastrado (14)|
|Todos os campos obrigatórios preenchidos|Formulário completo (15)|Um ou mais campos obrigatórios não preenchidos (16)|
|Notificação de confirmação enviada com sucesso|Notificação enviada por e-mail (17)|Notificação não enviada por  erro no endereço de e-mail (18)|
<br>

H2 - Como paciente, gostaria de realizar o login no aplicativo para que eu tenha acesso aos serviços do aplicativo.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H3 - Como paciente cadastrado no aplicativo B Health, gostaria de ver o histórico de vacinas para que eu possa verificar quais vacinas já tomei.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H4 - Como paciente, gostaria de acessar o mapa de vacinação para saber em quais unidades de saúde estão fornecendo as vacinas que preciso.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H5 - Como paciente, gostaria de receber lembretes do aplicativo de doses pendentes para que eu possa manter o controle das vacinas que eu devo tomar.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||

<br>

---

### ASSISTENTE SOCIAL
H12 - Como assistente social, gostaria de me cadastrar no aplicativo para que eu possa ter acesso ao aplicativo B Health.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H13 - Como assistente social, gostaria de realizar o login no aplicativo para que eu tenha acesso aos serviços do aplicativo.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H14 - Como assistente social, quero agendar visitas no aplicativo, para que os pacientes sejam notificados.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H17 - Como assistente social, eu gostaria de visualizar uma lista de pacientes prioritários (idosos, gestantes, crianças), para planejar visitas de acordo com a prioridade.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H19 - Como assistente social, eu gostaria de acessar o perfil completo de um paciente, para visualizar seus dados pessoais antes de uma visita.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||

<br>

---

### Enfermeira
H33 - Como enfermeiro, eu quero me cadastrar no aplicativo, para que eu possa acessar as funcionalidades.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H20 - Como enfermeiro, quero registrar a aplicação de vacinas diretamente no aplicativo, para que eu possa atualizar o histórico do paciente.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H21 - Como enfermeiro, quero acessar um mapa com unidades de saúde, para que eu possa orientar pacientes sobre locais disponíveis para vacinação.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H22 - Como enfermeiro, eu quero cadastrar os detalhes de campanhas de vacinação no aplicativo, para informar a todos os pacientes.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H23 - Como enfermeiro, eu gostaria de registrar as vacinas que foram aplicadas no paciente para que atualize a carteira de vacina do paciente.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


<br>

---

### MÉDICO
H26 - Como médico, eu gostaria de me cadastrar no aplicativo para que eu possa ter acesso ao aplicativo B Health.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H27 - Como médico, eu gostaria de realizar o login no aplicativo para que eu tenha acesso aos serviços do aplicativo.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H28 - Como médico, eu gostaria de acessar uma lista de pacientes, para que eu possa acessar o seu perfil e carteira de vacina.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H31 - Como usuário (médico) do aplicativo B Health, eu gostaria de visualizar avisos sobre campanhas de vacinação, para informar sobre elas ao paciente durante uma consulta.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


H32 - Como médico, eu gostaria de saber os locais onde as campanhas de vacinação estão ocorrendo, através de um mapa de vacinação interativo, para que eu possa orientar o paciente a ir até esse lugar se vacinar.
<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
||||


<br>
