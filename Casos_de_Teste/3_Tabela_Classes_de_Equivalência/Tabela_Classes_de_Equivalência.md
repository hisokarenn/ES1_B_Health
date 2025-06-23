# Tabela de Classes de Equivalência
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
|Formulário de cadastro identifica ocupação como “Assistente Social”|Campo “ocupação” fixo e visível como “Assistente Social” (1)|Campo de ocupação ausente, editável ou com outro valor (2)|
|Número do CRESS validado quando ocupação é “Assistente Social”|Número CRESS válido e obrigatório (3)|CRESS ausente, inválido ou com caracteres incorretos (4)|
|E-mail digitado segue padrão RFC 5322|E-mail com @, domínio e extensão correta, sem espaços ou caracteres inválidos (5)|E-mail com erro de formatação ou símbolos proibidos (6)|
|E-mail não está cadastrado anteriormente|E-mail novo e único no sistema (7)|E-mail já utilizado por outro usuário (8)|
|Senha tem no mínimo 8 caracteres|Senha com 8 ou mais caracteres (9)|Senha com menos de 8 caracteres (10)|
|Senha contém letras maiúsculas, minúsculas e números|Composição aceita, por exemplo, Sabrina123 (11)|Senha composta apenas por letras ou números (12)|
|Confirmação de senha igual à senha digitada|Ambas senhas coincidem (13)|Senhas diferentes (14)|
|Cadastro finalizado com sucesso|Mensagem de “Cadastro realizado com sucesso” exibida (15)|Mensagem não exibida ou erro no cadastro (16)|
<br>
<br>

H13 - Como assistente social, gostaria de realizar o login no aplicativo para que eu tenha acesso aos serviços do aplicativo.
<br>

|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Campos de e-mail e senha preenchidos no login|Ambos os campos preenchidos corretamente (1)|Campo de e-mail ou senha em branco (2)|
|E-mail e senha são válidos e cadastrados|Credenciais correspondem ao cadastro (3)|E-mail ou senha incorretos (4)|
|Clique em “Esqueci minha senha” disponível|Link presente e funcional para recuperação por e-mail (5)|Link ausente ou não funcional (6)|
|Após login, usuário é direcionado à interface de assistente social|Interface específica com funções de assistente exibida (7)|Redirecionamento errado ou para outra interface (8)|
<br>
<br>

H14 - Como assistente social, quero agendar visitas no aplicativo, para que os pacientes sejam notificados.
<br>

|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Paciente existe e está ativo no banco PostgreSQL|Paciente cadastrado e ativo (1)|Paciente inexistente ou inativo (2)|
|Data e hora da visita selecionadas|Data e hora escolhidas (3)|Campo de data/hora não selecionado ou em branco (4)|
|Data e hora armazenadas corretamente no sistema|Registro salvo com sucesso no banco (5)|Falha ao armazenar no banco (6)|
|Assistente social deseja editar ou cancelar visita agendada|Edita ou cancela agendamento com sucesso (7)|Sistema impede ou não realiza alteração (8)|
|Nova visita não colide com outro agendamento|Data e hora disponíveis e não sobrepostas (9)|Data e hora já estão ocupadas por outro agendamento (10)|
|Agendamento não está em data e hora passada|Data futura validada (11)|Data anterior ao momento atual (12)|
|Validação feita tanto no cliente (Flutter) quanto no servidor (Node)|Ambas as camadas rejeitam datas inválidas (13)|Sistema aceita datas passadas por falha na interface ou backend (14)|
|Paciente recebe lembrete com 12h de antecedência|Notificação push enviada com sucesso via Firebase (15)|Notificação não enviada ou enviada em horário incorreto (16)|
<br>
<br>

H17 - Como assistente social, eu gostaria de visualizar uma lista de pacientes prioritários (idosos, gestantes, crianças), para planejar visitas de acordo com a prioridade.
<br>

|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Lista exibe apenas pacientes prioritários|Lista com idosos, gestantes, crianças com vacinação incompleta (1)|Lista contém pacientes fora dos grupos prioritários (2)|
|Sistema identifica prioridade automaticamente|Identificação correta via data de nascimento, sexo ou campo "prioridade" (3)|Sistema não identifica corretamente o grupo de prioridade (4)|
|Ordenação por tipo de prioridade disponível|Lista pode ser ordenada por idoso, gestante ou criança (5)|Sistema não permite ordenação (6)|
|Lista atualizada automaticamente|Novo paciente com prioridade aparece na lista após cadastro (7)|Novo paciente com prioridade não aparece na lista (8)|
|Sistema separa visualmente os tipos de prioridade|Uso correto de cores ou ícones (verde, amarelo, vermelho) conforme nível (9)|Ausência de distinção visual ou incorreta (10)|
|Paciente com esquema vacinal incompleto exibido mesmo sem estar em grupo alvo|Inclusão de pacientes com vacinação pendente (11)|Exclusão de pacientes fora dos grupos-alvo mas com esquema vacinal incompleto (12)|
<br>
<br>

H19 - Como assistente social, eu gostaria de acessar o perfil completo de um paciente, para visualizar seus dados pessoais antes de uma visita.
<br>

|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Paciente está cadastrado no sistema|Perfil acessível para paciente existente (1)|Perfil inexistente ou não localizado (2)|
|Dados exibidos incluem nome, contato, endereço e carteira de vacinação|Todos os campos necessários visíveis (3)|Dados incompletos ou campos ausentes (4)|
|Assistente social não pode editar dados pessoais|Campos como nome, endereço, CNS, CPF são apenas leitura (5)|Permissão indevida para editar ou excluir dados (6)|
|Carteira de vacinação é exibida no mesmo scroll da página do perfil|Exibição contínua com rolagem vertical (7)|Exibição separada em abas, telas ou com navegação adicional (8)|
|Assistente social não pode alterar a carteira de vacinação|Apenas visualização permitida (9)|Sistema permite editar e remover vacinas (10)|
|Acesso ao perfil ocorre pelo botão "visualizar perfil" na lista de pacientes|Botão funcional e leva à página correta (11)|Botão ausente, não funcional ou com redirecionamento incorreto (12)|
<br>

---

### Enfermeiro
H33 - Como enfermeiro, eu quero me cadastrar no aplicativo, para que eu possa acessar as funcionalidades.
<br>

|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|COREN válido e ativo|COREN reconhecido pelo sistema e com status ativo (1)|COREN inválido, expirado ou ausente (2)|
|Senha contém ao menos 8 caracteres, com letra maiúscula, número e símbolo (@, # etc.)|Senha no formato exigido (ex: Saude@2025) (3)|Senha com menos de 8 caracteres ou faltando tipos exigidos (4)|
|Campos obrigatórios preenchidos: Nome, COREN, e-mail institucional, unidade de saúde|Todos os dados inseridos corretamente (5)|Campos obrigatórios ausentes, inválidos ou e-mail sem domínio institucional (6)|
|Perfil “Enfermeiro-Chefe” atribuído apenas por gestor da UBS|Gestor atribui corretamente o perfil durante validação (7)|Perfil atribuído automaticamente ou por pessoa sem permissão (8)|
|COREN inativo bloqueia conta após verificação manual em até 24h|Conta bloqueada corretamente com registro do motivo (9)|COREN inativo continua com acesso ou sem justificativa no sistema (10)|
|Três tentativas de login incorretas bloqueiam a conta por 1h|Bloqueio realizado corretamente após terceira tentativa (11)|Tentativas ilimitadas ou sem bloqueio (12)|
|E-mail de bloqueio enviado com motivo e link para redefinir senha|E-mail com mensagem e link enviado após bloqueio (13)|Nenhuma notificação enviada ou link ausente (14)|
|Sessão expirada após inatividade exige novo login|Sessão finalizada automaticamente e acesso bloqueado (15)|Sessão permanece ativa indefinidamente ou exige recarregamento manual (16)|
|Dados não sensíveis mantidos por até 1h após sessão expirar|Informações públicas como nome e cargo mantidas temporariamente (17)|Dados sensíveis como senha ou COREN expostos ou mantidos após expiração (18)|
<br>
<br>

H20 - Como enfermeiro, quero registrar a aplicação de vacinas diretamente no aplicativo, para que eu possa atualizar o histórico do paciente.
<br>

|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Busca de paciente por CPF ou número do SUS|CPF com 11 dígitos ou CNS com 15 dígitos válidos (1)|CPF e CNS inválidos, incorretos ou não cadastrados (2)|
|Vacinas disponíveis na lista estática oficial do SUS/ANVISA|Lista correta com vacinas do calendário atualizado (3)|Lista desatualizada ou com itens ausentes (4)|
|Sistema aceita registrar até 50 vacinas por sessão|Registros aceitos até o limite de 50 por sessão (5)|Excede o limite sem nova autenticação (6)|
|Sistema permite registros tanto online quanto offline|Registro salvo localmente e sincronizado quando online (7)|Falha na sincronização ou bloqueio por falta de conexão (8)|
|Enfermeiro possui COREN ativo e está vinculado a uma UBS|COREN validado e vínculo confirmado (9)|COREN inativo ou enfermeiro sem vínculo com UBS (10)|
|Validação de cadastro por e-mail institucional e conferência manual|Cadastro aprovado pelo administrador (11)|Cadastro não validado ou pendente de conferência (12)|
|Registro de lote de vacina completo com os dados obrigatórios|Lote registrado com nº do lote, validade, fabricante, CPF, COREN, data/hora (13)|Registro incompleto ou campos obrigatórios ausentes (14)|
|Backups criptografados garantem rastreabilidade|Registros armazenados com criptografia e retenção por 10 anos (15)|Falha no backup, dados não rastreáveis ou sem proteção adequada (16)|
<br>
<br>

H21 - Como enfermeiro, quero acessar um mapa com unidades de saúde, para que eu possa orientar pacientes sobre locais disponíveis para vacinação.
<br>

|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Indicador de lotação exibido corretamente por cor|Verde (≤50%), Amarelo (51–80%), Vermelho (>80%), atualizado a cada 15 min (1)|Cores erradas, atualização incorreta ou ausência de indicador de lotação (2)|
|Mapa mostra unidades num raio inicial de 500m e expande automaticamente|Raio de busca aumenta para 1km, 3km e 5km caso não haja unidades (3)|Raio não expande ou não encontra unidades mesmo que existam (4)|
|Raio ajustável manualmente pelo usuário|Interface permite alterar manualmente a distância de busca (5)|Usuário não consegue ajustar o raio ou recurso ausente (6)|
|Endereços das unidades validados automaticamente|Endereço com CEP, número e cidade validados e marcados como verificados (7)|Endereços inválidos ou marcados como “não verificados” por erro de validação (8)|
|Sistema marca como “não verificado” em caso de falha de validação de endereço|Sistema identifica corretamente falhas e marca visualmente (9)|Endereços incorretos são exibidos como válidos (10)|
<br>
<br>

H22 - Como enfermeiro, eu quero cadastrar os detalhes de campanhas de vacinação no aplicativo, para informar a todos os pacientes.
<br>

|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Campanha submetida por enfermeiro com COREN|Enfermeiro-chefe com COREN ativo aprova a campanha (1)|Campanha enviada por usuário sem COREN ou sem validação (2)|
|Aprovação da campanha ocorre em até 2 horas|Campanha validada dentro do prazo e publicada (3)
Aprovação não ocorre em 2 horas (4)|
|Campanha reprovada pode ser reenviada após revisão|Sistema permite correção e reenvio para nova tentativa de aprovação (5)|Sistema bloqueia reenvio ou não informa reprovação automática (6)|
|Notificações são enviadas a todos os perfis com formato padrão|Push enviado com mensagem no formato: ‘Campanha [x] em [Posto] até [Data]’ (7)|Notificação não enviada ou enviada com formato errado ou incompleto (8)|
<br>
<br>

H23 - Como enfermeiro, eu gostaria de registrar as vacinas que foram aplicadas no paciente para que atualize a carteira de vacina do paciente.
<br>

|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Registro segue intervalo mínimo do PNI ou é reforço autorizado|Sistema aceita vacina dentro do prazo ou com dose de reforço válida (1)|Sistema bloqueia registro duplicado fora do prazo sem justificativa (2)|
|Vacinas/doses pendentes geram alertas automáticos|Notificações visuais e push informam vacina, dose e prazo conforme PNI (3)|Nenhum alerta é exibido ou exibe informações incompletas ou incorretas (4)|
|Paciente visualiza histórico atualizado em até 1 minuto após o registro|Atualização imediata ou dentro do tempo limite (5)|Histórico não atualizado ou demora excessiva (6)|
|Histórico pode ser exportado em PDF conforme modelo do Ministério da Saúde|PDF gerado com QR Code e dados oficiais disponíveis ao paciente e profissionais (7)|PDF ausente, sem QR Code ou fora do padrão do MS (8)|
|Vacina reaplicada fora do prazo com justificativa médica|Cadastro autorizado com CRM, token, justificativa e prontuário (9)|Reaplicação fora do intervalo sem justificativa e documentação médica (10)|
|Registro feito offline é sincronizado e verificado na reconexão|Sincronização verifica duplicidade (CPF + lote + data + tipo) e permite resolução (11)|Sincronização falha ou conflitos não resolvidos corretamente (12)|
|Conflito em duplicatas resolvido pelo enfermeiro com justificativa|Enfermeiro pode justificar o registro e resolver manualmente (13)|Sistema não permite justificar ou não escalona casos complexos ao enfermeiro-chefe (14)|
<br>

---

### MÉDICO
H26 - Como médico, eu gostaria de me cadastrar no aplicativo para que eu possa ter acesso ao aplicativo B Health.
<br>

|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Campo de ocupação é fixo como “Médico”|Campo “Médico” pré-definido e não editável (1)|Campo permite editar ocupação (2)|
|CRM é obrigatório e validado|CRM inserido corretamente e validado (3)|CRM inválido ou duplicado (4)|
|E-mail válido é exigido|E-mail com formato válido é aceito (5)|E-mail em formato inválido ou duplicado (6)|
|Senha com no mínimo 8 caracteres|Senha com 8 ou mais caracteres (7)|Senha com menos de 8 caracteres e sem validação (8)|
|Senha contém letras e números|Senha com letras maiúsculas, minúsculas e números (9)|Senha com apenas números ou apenas letras (10)|
|Validação de senha duplicada|Senhas iguai e válidas (11)|Senhas diferentes (12)|
|Acesso ao perfil do médico|Acesso liberado com funcionalidades médicas (13)|Acesso liberado com funcionalidades erradas (14)|
<br>
<br>

H27 - Como médico, eu gostaria de realizar o login no aplicativo para que eu tenha acesso aos serviços do aplicativo.
<br>

|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|CRM ou e-mail cadastrado|CRM ou E-mail previamente cadastrado (1)|Login aceito com dados não cadastrados e inexistentes (2)|
|Senha incorreta|Senha corresponde ao cadastro (3)|Senha incorreta ou campo de senha em branco (4)|
|Cadastro validado oficialmente|Cadastro válido via integração ou manual (5)|Validação pendente e login permitido (6)|
|Link de recuperação de senha disponível|Link “Esqueci minha senha” funcional (7)|Link ausente na interface (8)|
|Acesso ao painel exclusivo do médico|Direcionado para painel correto após o login (9)|Acesso negado após login correto (10)|
<br>
<br>

H28 - Como médico, eu gostaria de acessar uma lista de pacientes, para que eu possa acessar o seu perfil e carteira de vacina.
<br>

|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Lista de pacientes apresentada em scroll contínuo e ordenada alfabeticamente|Lista carrega automaticamente e está organizada por nome (1)|Lista incompleta, não ordenada ou sem carregamento automático (2)|
|Pesquisa por nome completo, CPF ou CNS funciona com filtragem em tempo real|Resultados são filtrados corretamente conforme entrada do médico (3)|Pesquisa lenta, falha ou sem retorno esperado (4)|
|Acesso limitado a um paciente por vez|Médico acessa apenas um perfil de cada vez (5)|Acesso simultâneo a múltiplos perfis ou dados de pacientes incorretos (6)|
|Perfil exibe nome completo, CNS e carteira de vacinação|Informações corretas e completas são exibidas (7)|Dados faltando, incompletos ou inconsistentes com o cadastro (8)|
|Médico não pode alterar dados pessoais do paciente (nome, endereço, CNS, e-mail)|Campos protegidos contra edição (9)|Sistema permite alterações indevidas em dados sensíveis (10)|
|Dados e carteira de vacinação são exibidos na mesma tela (scroll vertical contínuo)|Exibição única e fluida em tela única com rolagem (11)|Interface dividida em abas ou múltiplas telas (12)|
|Médico pode editar a carteira de vacinação|Alterações autorizadas e salvas corretamente (13)|Edição não permitida ou funcionalidade ausente mesmo com permissão (14)|
<br>
<br>

H31 - Como usuário (médico) do aplicativo B Health, eu gostaria de visualizar avisos sobre campanhas de vacinação, para informar sobre elas ao paciente durante uma consulta.
<br>

|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Visualizar apenas campanhas ativas|Campanhas ativas são exibidas no mapa (1)|Campanhas inativas são exibidas (2)|
|Médico não pode publicar campanhas|Médico apenas visualiza campanhas (3)|Médico consegue publicar campanhas (4)|
|Campanhas contém datas visíveis|Sistema exibe data de início e fim (5)|Datas não são exibidas (6)|
|Campanha emergencial notifica médicos|Notificação push é enviada via Firebase (7)|Notificação não é enviada (8)|
<br>
<br>

H32 - Como médico, eu gostaria de saber os locais onde as campanhas de vacinação estão ocorrendo, através de um mapa de vacinação interativo, para que eu possa orientar o paciente a ir até esse lugar se vacinar.
<br>

|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS|CLASSES INVÁLIDAS|
|-|-|-|
|Notificação exibe locais das campanhas|Locais exibidos na notificação push (1)|Locais ausentes na notificação (2)|
|Endereço completo visível|Endereço completo exibido no mapa (3)|Endereço incompleto ou ausente (4)|
|Período da campanha visível|Médico vê o intervalo da campanha (5)|Período não é informado (6)|
|Dados são atualizados pela enfermagem|Alterações feitas pela enfermagem aparecem no sistema (7)|Sistema não reflete alterações (8)|
|Médico vê apenas sua jurisdição|Apenas locais do município do médico são exibidos (9)|Locais de outros municípios são exibidos (10)|












<br>
