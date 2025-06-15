# Rastreabiliade com Histórias de Usuário

<p align="justify">Possui o objetivo de apresentar o mapeamento entre as histórias de usuário desenvolvidas no Trabalho Prático 1 (TP1) e os componentes da arquitetura do sistema. A proposta é evidenciar como cada requisito identificado a partir das necessidades dos usuários foi incorporado à estrutura arquitetural do projeto. Para isso, será utilizada uma tabela/seção que relaciona diretamente as histórias aos elementos responsáveis por sua implementação. Esse mapeamento garante a rastreabilidade e a coerência entre a etapa de levantamento de requisitos e o desenho da solução técnica.
  
Deve conter:
- A história do usuário
- Os componentes envolvidos
- Onde ela aparece nos diagramas

<br>

## Tabela elaborada

<br>

|Histórias de Usuário|Componentes Envolvidos|Diagramas de Referência|
|-|-|-|
|<p align="justify">H1 - Como paciente, gostaria de me cadastrar no aplicativo para que eu possa ter acesso ao aplicativo B Health.|<p align="justify">Tela Cadastro, Controlador de Senha, Firebase Auth, Classe Usuário, Classe Paciente|Contexto,Componentes, Containers, Classes|
|<p align="justify">H2 - Como paciente, gostaria de realizar o login no aplicativo para que eu tenha acesso aos serviços do aplicativo.|<p align="justify">Tela Cadastro, Controlador Login, Componente de Segurança, Firebase Auth, Classe Usuário|Contexto, Componentes, Container, Classes|
|<p align="justify">H3 - Como paciente cadastrado no aplicativo B Health, gostaria de ver o histórico de vacinas para que eu possa verificar quais vacinas já tomei.|<p align="justify">Tela Carteira de Vacina, Controlador de Vacinas e Histórico, Serviço de Vacinas, Banco de Dados, Classes Paciente, Classe CarteiraVacinacao|Contexto, Componentes Containers, Classes|
|<p align="justify">H4 - Como paciente, gostaria de acessar o mapa de vacinação para saber em quais unidades de saúde estão fornecendo as vacinas que preciso.|<p align="justify">Tela Carteira de Vacina, Controlador de Mapas, Componente de Geolocalização, Google Maps SDK, Classe MapaDeVacinacao|Contexto, Componentes, Classes|
|<p align="justify">H5 - Como paciente, gostaria de receber lembretes do aplicativo de doses pendentes para que eu possa manter o controle das vacinas que eu devo tomar.|<p align="justify">Componente de Notificação, Firebase Cloud Messaging, Serviço de Vacinas, Classe Notificacoes|Contexto, Componentes, Classes|
|<p align="justify">H12 - Como assistente social, gostaria de me cadastrar no aplicativo para que eu possa ter acesso ao aplicativo B Health|Tela Cadastro, Controlador de Senha, Firebase Auth, Classe Usuario, Classe Assistente Social|Contexto, Componentes, Container, Classes|
|<p align="justify">H13 - Como assistente social, gostaria de realizar o login no aplicativo para que eu tenha acesso aos serviços do aplicativo.|Tela Cadastro, Controlador Login, Componente de Segurança, Firebase Auth, Classe Usuario|Contexto, Componentes, Containers, Classes|
|<p align="justify">H14 - Como assistente social, quero agendar visitas no aplicativo, para que os pacientes sejam notificados.|Tela Agendamento de Visitas, Controlador de Campanhas e Visitas, Componente de Notificação, Classe AgendamentoVisitas, Classe notificacoes|Contexto, Componentes, Classes|
|<p align="justify">H17 - Como assistente social, eu gostaria de visualizar uma lista de pacientes prioritários (idosos, gestantes, crianças), para planejar visitas de acordo com a prioridade.|<p align="justify">Tela de Lista, Controlador de Vacinas e Histórico, Banco de Dados, Classe Paciente|Contexto, Componentes, Classes|
|<p align="justify">H19 - Como assistente social, eu gostaria de acessar o perfil completo de um paciente, para visualizar seus dados pessoais antes de uma visita.|Controlador de Vacinas e Histórico, Banco de Dados, Classe Paciente|Contexto, Componentes, Classes|
|<p align="justify">H20 - Como enfermeiro, quero registrar a aplicação de vacinas diretamente no aplicativo, para que eu possa atualizar o histórico do paciente.|<p align="justify">Controlador de Vacina e Histórico, Serviço de Vacinas, Banco de Dados, Classe Dose|Contexto, Componentes, Classes|
|<p align="justify">H21 - Como enfermeiro, quero acessar um mapa com unidades de saúde, para que eu possa orientar pacientes sobre locais disponíveis para vacinação.|<p align="justify">Controlador de Mapas, Componente de Geolocalização, Google Maps SDK, Classe UnidadeSaude|Contexto, Componentes, Classes|
|<p align="justify">H22 - Como enfermeiro, eu quero cadastrar os detalhes de campanhas de vacinação no aplicativo, para informar a todos os pacientes.|<p align="justify">Controlador de Campanhas e Visitas, Serviço de Campanha, Banco de Dados, Classe Campanha|Contexto, Componentes, Classes|
|<p align="justify">H23 - Como enfermeiro, eu gostaria de registrar as vacinas que foram aplicadas no paciente para que atualize a carteira de vacina do paciente.|<p align="justify">Tela Carteira de Vacina, Controlador de Vacinas e Histórico, Serviço de Vacinas, Classe CarteiraVacinacao|Componentes, Classes|
|<p align="justify">H26 - Como médico, eu gostaria de me cadastrar no aplicativo para que eu possa ter acesso ao aplicativo B Health.|<p align="justify">Tela Cadastro, Controlador de Senha, Firebase Auth, Classe Usuario, Classe Medico|Contexto, Componentes, Container, Classes|
|<p align="justify">H27 - Como médico, eu gostaria de realizar o login no aplicativo para que eu tenha acesso aos serviços do aplicativo.|<p align="justify">Tela Cadastro, Controlador Login, Componente de Segurança, Firebase Auth, Classe Usuario|Contexto, Componentes, Containers, Classes|
|<p align="justify">H28 - Como médico, eu gostaria de acessar uma lista de pacientes, para que eu possa acessar o seu perfil e carteira de vacina.|<p align="justify">Tela de Lista, Controlador de Vacinas e Histórico, Banco de Dados, Classe Paciente|Contexto, Componentes, Classes|
|<p align="justify">H31 - Como usuário (médico) do aplicativo de Carteira de Vacina Digital, eu gostaria de visualizar avisos sobre campanhas de vacinação, para informar sobre elas ao paciente durante uma consulta.|<p align="justify">Componente de Notificação, Serviço de Campanha, Firebase Cloud Messaging, Classe CarteiraVacinacao, Classe Campanha, Classe Notificacoes|Contexto, Componentes, Classes|
|<p align="justify">H32 - Como médico, eu gostaria de saber os locais onde as campanhas de vacinação estão ocorrendo, para que eu possa orientar o paciente a ir até esse lugar se vacinar.|<p align="justify">Tela de Campanhas, Serviço de Campanhas,  Classe UnidadeSaude|Componentes, Classes|
|<p align="justify">H33 - Como enfermeiro, eu quero me cadastrar no aplicativo, para que eu possa acessar as funcionalidades.|<p align="justify">Tela Cadastro, Controlador de Senha, Firebase Auth, Classe Usuario, Classe Enfermeiro|Contexto, Componentes, Containers, Classes|
