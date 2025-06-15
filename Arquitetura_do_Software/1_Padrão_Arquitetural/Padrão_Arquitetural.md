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
Um padrão que separa o sistema em três partes principais:
- Model: Dados e regras de negócio (ex.: Paciente, Vacina).
- View: Interface com o usuário (Flutter).
- Controller: Processamento das ações, orquestra o fluxo entre Model e View (Node.js + Express).
### Por que foi escolhida?
- Organização clara: Cada parte tem uma função bem definida, facilitando manutenções e atualizações.
- Alinhamento tecnológico: Flutter como View, Node.js como Controller e PostgreSQL como Model se integram perfeitamente.
- Eficiência: Evita sobrecarga no tráfego de dados, retornando apenas o necessário nas requisições.
- Testabilidade: Controllers e Models podem ser testados separadamente, garantindo maior estabilidade e segurança.
- Reutilização: Models podem ser compartilhados entre o backend e o frontend, otimizando o desenvolvimento.

<br>

|Componente|Responsabilidade|Exemplo no B Health|
|-|-|-|
|Model|Gerencia dados e regras de negócio.|Classe Vacina com atributos como nome, dose, data e lote.|
|View|Interface que exibe informações e recebe ações do usuário|Telas Flutter, como o histórico vacinal e formulário de agendamento.|
|Controller|Processa requisições, conecta Model e View, e executa as regras.|API em Node.js que valida e salva um agendamento no banco de dados.|

<br>

## 3. Publish-Subscribe (Pub/Sub)
### O que é?
Modelo de comunicação assíncrona baseado em eventos:
- Publisher (Publicador): Emite eventos (ex.: nova vacina registrada).
- Subscriber (Assinante): Recebe e reage aos eventos (ex.: app do paciente exibe notificação).
- Broker (Intermediário): Gerencia o envio das mensagens (Socket.IO/FCM).
### Por que foi escolhida?
- Atualizações em tempo real: Notificações instantâneas quando, por exemplo, uma nova vacina é registrada.
- Escalabilidade: Suporta muitos usuários simultaneamente, permitindo adicionar novos serviços sem alterar o núcleo.
- Baixo acoplamento: O backend não precisa saber quantos clientes estão conectados, tornando o sistema mais flexível.
- Resiliência: Mensagens são armazenadas e entregues quando o assinante estiver online novamente.
- Eficiência: Socket.IO mantém conexão contínua (WebSocket), ideal para dados em tempo real; FCM garante notificações mesmo com o app fechado.

<br>

|Componente|Tecnologia|Função no B health|
|-|-|-|
|Publisher|Node.js|Publica eventos, como "nova vacina registrada" ou "agendamento criado".|
|Broker|Socket.IO + Firebase Cloud|Gerencia a distribuição das mensagens e garante entrega em tempo real ou push.|
|Subscriber|Flutter|Recebe eventos e exibe notificações no app, como alertas de dose pendente.|
