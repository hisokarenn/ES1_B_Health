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
|Identificação via CNS ou e-mail|CNS com 15 dígitos numéricos ou e-mail válido (1)|CNS com menos de 15 dígitos e e-mail inválido (2)|
|Senha inserida corretamente|Senha corresponde à cadastrada (3)|Senha incorreta (4)|
|Senha não está em branco|Campo de senha preenchido (5)|Campo de senha em branco (6)|
|Clique em "Esqueci minha senha"|Redireciona para etapa de recuperação (7)|Nenhuma ação ocorre, pode ser erro ou botão que não está funcionando (8)|
|E-mail informado na recuperação é válido e cadastrado|E-mail contém "@" e domínio e está registrado no sistema (9)|E-mail inválido ou não registrado (10)|
|Código de verificação enviado|Código enviado com sucesso ao e-mail informado (11)|Código não enviado o que pode ocorrer por falha no sistema ou e-mail inválido (12)|
|Código de verificação inserido corretamente|Código correto permite redefinir senha (13)|Código incorreto ou em branco (14)|
<br>

H3 - Como paciente cadastrado no aplicativo B Health, gostaria de ver o histórico de vacinas para que eu possa verificar quais vacinas já tomei.

<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Paciente autenticado|Paciente está logado no sistema (1)|Acesso sem login/autenticação (2)|
|Paciente visualiza apenas seu próprio histórico|Histórico exibido pertence ao usuário autenticado (3)|Visualização de histórico de outro paciente (4)|
|Histórico possui registros|Lista de vacinas exibida com nome e data em ordem crescente (5)|Histórico em branco sem registros (6)|
|Clique sobre vacina exibida|Exibe local de aplicação e nome do profissional (7)|Não exibir informações adicionais ao clicar (8)|
|Nome da vacina presente|Cada item do histórico possui o nome da vacina (9)|Campo "nome da vacina" está vazio ou ausente (10)|
|Data de aplicação válida|Data no formato correto e cronologicamente organizada (11)|Data ausente ou fora de ordem cronológica (12)|
|Histórico atualizado|Cada vacina aplicada será registrada no histórico (13)|Histórico desatualizado mesmo após aplicação de vacina (14)|
<br>

H4 - Como paciente, gostaria de acessar o mapa de vacinação para saber em quais unidades de saúde estão fornecendo as vacinas que preciso.

<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Paciente está com acesso à internet|Conexão ativa para exibição do mapa (1)|Sem internet ou conexão instável (2)|
|Localização do usuário permitida no app|Permissão de localização concedida (3)|Permissão de localização negada (4)|
|Mapa interativo é carregado corretamente|Mapa exibido com pontos geográficos (5)|Mapa não aparece ou carrega em branco (6)|
|Paciente aplica filtro por vacina|Unidades exibidas com a vacina filtrada (7)|Nenhuma unidade corresponde ao filtro (mensagem exibida) (8)|
|Clique sobre unidade de saúde no mapa|Exibe nome, endereço, vacinas disponíveis e horário de funcionamento (9)|Informações incompletas ou não exibidas ao clicar (10)|
|Mapa mostra apenas unidades com vacina disponível e abertas|Unidades exibidas estão abertas e com a vacina procurada (11)|Mapa mostra unidades fechadas ou sem a vacina (12)|
|Aplicativo mantém localização segura|Localização não compartilhada com terceiros (13)|Aplicativo vaza ou compartilha dados de localização (14)|
<br>

H5 - Como paciente, gostaria de receber lembretes do aplicativo de doses pendentes para que eu possa manter o controle das vacinas que eu devo tomar.

<br>
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Vacina com próxima dose registrada no sistema|Vacina possui nome e data de próxima dose (1)|Nenhuma dose futura registrada (2)|
|Sistema envia lembrete com antecedência mínima de 2 dias|Notificação enviada pelo menos 2 dias antes da aplicação (3)|Notificação enviada com menos de 2 dias ou não enviada (4)|
|Formato da notificação é push|Notificação push recebida no celular (5)|Notificação não enviada ao paciente (6)|
|Paciente clica na notificação|Redirecionamento correto para tela de detalhes da vacina (7)|Clique não direciona ou gera erro (8)|
|Vacina é aplicada e registrada pelo enfermeiro|Lembretes futuros cancelados automaticamente (9)|Lembretes continuam mesmo após confirmação da dose (10)|
|Paciente desativa notificações do app nas configurações do celular|Lembretes desativados  corretamente (11)|Lembretes continuam sendo enviados mesmo com notificações desativadas (12)|
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
