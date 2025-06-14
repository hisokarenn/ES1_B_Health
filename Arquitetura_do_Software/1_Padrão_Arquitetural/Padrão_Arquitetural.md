# Padrão Arquitetural

<p align="justify"> A definição das arquiteturas no BHealth foi pensada para garantir escalabilidade, manutenibilidade, funcionamento offline e comunicação eficiente. Abaixo estão as descrições e os motivos pelos quais cada arquitetura foi adotada.

## 1. Arquitetura em Camadas
### O que é?<br>
Organiza o sistema em camadas, onde cada uma possui uma responsabilidade específica e se comunica apenas com as camadas adjacentes. As principais são:
- Apresentação (Front-End): Interface do usuário (Flutter).
- Negócio (Back-End): Regras e lógica (Node.js + Express).
- Persistência (Banco de Dados): Armazenamento dos dados (PostgreSQL + PostGIS).
- Integração (Serviços Externos): Funcionalidades como autenticação (Firebase), mapas (Google Maps SDK) e notificações (FCM/Socket.IO).

### Por que foi escolhida?
- Organização: Facilita a separação do frontend, backend e banco, melhorando a manutenção e o desenvolvimento em equipe.
- Integração Eficiente: Permite utilizar tecnologias especializadas como PostGIS para mapas e Firebase para login.
- Funcionamento Offline: Suporte a dados locais (SQLite) com sincronização quando houver conexão.
- Escalabilidade: Permite que cada camada cresça de forma independente (ex.: backend pode escalar sem afetar o app).
- Testabilidade: Componentes isolados facilitam a execução de testes específicos em cada parte do sistema.

<br>

|Camadas|Tecnologias|Papel no Sistema|
|-|-|-|
|Apresentação|Flutter|Interface do usuário para pacientes, profissionais de saúde e administradores.|
|Negócio|Node.js + Express|APIs REST, regras de vacinação, agendamento, histórico e alertas.|
|Persistência|PostgreSQL + PostGIS|Armazena dados estruturados (vacinas, usuários, locais) e dados geoespaciais.|
|Integração|Firebase Auth, Google Maps SDK, FCM, Socket.IO|Autenticação, geolocalização, notificações push e comunicação em tempo real.|

<br>

## 2. MVC (Model-View-Controller)
### O que é?<br>
