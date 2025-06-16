# Padrão Arquitetural

<p align="justify"> A definição das arquiteturas no BHealth foi pensada para garantir escalabilidade, manutenibilidade, funcionamento offline e comunicação eficiente. Abaixo estão as descrições e os motivos pelos quais cada arquitetura foi adotada.

## 1. Arquitetura em Camadas
### O que é?<br>
Um padrão de arquitetura que organiza o sistema em camadas, onde cada uma possui uma responsabilidade específica e se comunica apenas com as camadas adjacentes. As principais são:
- **Apresentação (Front-End):** Interface do usuário (Flutter).
- **Negócio (Back-End):** Regras e lógica (Node.js + Express).
- **Persistência (Banco de Dados):** Armazenamento dos dados (PostgreSQL + PostGIS).
- **Integração (Serviços Externos):** Funcionalidades como autenticação (Firebase), mapas (Google Maps SDK) e notificações (FCM/Socket.IO).

### Por que foi escolhida?
- **Organização:** Facilita a separação do frontend, backend e banco, melhorando a manutenção e o desenvolvimento em equipe.
- **Integração Eficiente:** Permite utilizar tecnologias especializadas como PostGIS para mapas e Firebase para login.
- **Funcionamento Offline:** Suporte a dados locais (SQLite) com sincronização quando houver conexão.
- **Escalabilidade:** Permite que cada camada cresça de forma independente (ex.: backend pode escalar sem afetar o aplicativo móvel).
- **Testabilidade:** Componentes isolados facilitam a execução de testes específicos em cada parte do sistema.

<br>

|Camadas|Tecnologias|Papel no Sistema|
|-|-|-|
|<p align="center">Apresentação|<p align="center">Flutter|Interface do usuário para pacientes, profissionais de saúde e administradores.|
|<p align="center">Negócio|<p align="center">Node.js + Express|APIs REST, regras de vacinação, agendamento, histórico e alertas.|
|<p align="center">Persistência|<p align="center">PostgreSQL + PostGIS|Armazena dados estruturados (vacinas, usuários, locais) e dados geoespaciais.|
|<p align="center">Integração|<p align="center">Firebase Auth, Google Maps SDK, FCM, Socket.IO|Autenticação, geolocalização, notificações push e comunicação em tempo real.|

<br>

## 2. MVC (Model-View-Controller)
### O que é?<br>
Um padrão que separa o sistema em três partes principais:
- **Model:** Dados e regras de negócio (ex.: Paciente, Vacina).
- **View:** Interface com o usuário (Flutter).
- **Controller:** Processamento das ações, orquestra o fluxo entre Model e View (Node.js + Express).
### Por que foi escolhida?
- **Organização:** Cada parte tem uma função bem definida, facilitando manutenções e atualizações.
- **Alinhamento tecnológico:** Flutter como View, Node.js como Controller e PostgreSQL como Model se integram perfeitamente.
- **Eficiência:** Evita sobrecarga no tráfego de dados, retornando apenas o necessário nas requisições.
- **Testabilidade:** Controllers e Models podem ser testados separadamente, garantindo maior estabilidade e segurança.
- **Reutilização:** Models podem ser compartilhados entre o backend e o frontend, otimizando o desenvolvimento.

<br>

|Componente|Responsabilidade|Exemplo no B Health|
|-|-|-|
|<p align="center">Model|<p align="center">Gerencia dados e regras de negócio.|Classe Vacina com atributos como nome, dose, data e lote.|
|<p align="center">View|<p align="center">Interface que exibe informações e recebe ações do usuário|Telas Flutter, como o histórico vacinal e formulário de agendamento.|
|<p align="center">Controller|<p align="center">Processa requisições, conecta Model e View, e executa as regras.|API em Node.js que valida e salva um agendamento no banco de dados.|

<br>

## 3. Publish-Subscribe (Pub/Sub)
### O que é?
Modelo de comunicação assíncrona baseado em eventos:
- **Publisher (Publicador):** Emite eventos (ex.: nova vacina registrada).
- **Subscriber (Assinante):** Recebe e reage aos eventos (ex.: app do paciente exibe notificação).
- **Broker (Intermediário):** Gerencia o envio das mensagens (Socket.IO/FCM).
### Por que foi escolhida?
- **Atualizações em tempo real:** Notificações instantâneas quando, por exemplo, uma nova vacina é registrada.
- **Escalabilidade:** Suporta muitos usuários simultaneamente, permitindo adicionar novos serviços sem alterar o núcleo.
- **Baixo acoplamento:** O backend não precisa saber quantos clientes estão conectados, tornando o sistema mais flexível.
- **Resiliência:** Mensagens são armazenadas e entregues quando o assinante estiver online novamente.
- **Eficiência:** Socket.IO mantém conexão contínua (WebSocket), ideal para dados em tempo real; FCM garante notificações mesmo com o aplicativo fechado.

<br>

|Componente|Tecnologia|Função no B health|
|-|-|-|
|<p align="center">Publisher|<p align="center">Node.js|Publica eventos, como "nova vacina registrada" ou "agendamento criado".|
|<p align="center">Broker|<p align="center">Socket.IO + Firebase Cloud|Gerencia a distribuição das mensagens e garante entrega em tempo real ou push.|
|<p align="center">Subscriber|<p align="center">Flutter|Recebe eventos e exibe notificações no app, como alertas de dose pendente.|

<br>

## 4. Representação visual das arquiteturas selecionadas
A representação visual das arquiteturas foi elaborada a partir da junção das três abordagens, visando um melhor entendimento da organização do aplicativo móvel B Health. Abaixo, segue a imagem correspondente: 
<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/66e00f13902a78a712abfda3cf96905eff3891bd/Arquitetura_do_Software/Imagens/Arquitetura/arqCMP.jpg" alt="" width="500" <br>
<p align="center">Figura das Arquiteturas produzidas no draw.io
<br>


