# Tabela de Tecnologiaa e Ferramentas (Tech Stack Map)

<p align="justify"> Em desenvolvimento de software, uma "tech stack" ou "pilha tecnológica" refere-se ao conjunto de ferramentas e tecnologias utilizadas para construir, executar e manter um projeto de software, como um site, aplicativo ou serviço. Isso inclui linguagens de programação, frameworks, bancos de dados, servidores, e outras ferramentas e componentes.

<p align="justify"> Foi elaborado um Mapa de Tecnologias (Tech Stack Map), e uma tabela que demonstram as tecnologias e ferramentas principais que seriam utilizadas para o desenvolvimento do aplicativo móvel.
<br>
<br>
  
## Tech Stack Map
Mapa Geral de Tecnologias listadas, mostrando as camadas e ferramentas respectivas.
<br>
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/00b0cc85bc88eadf9e018a9982a756f590116eb8/Arquitetura_do_Software/Imagens/Tech_Stack_Map/mapaDeTecnologias.drawio.png" alt="" width="1200"
<br>
<p align="center"> Mapa de Tecnologias gerado no Draw.io

---

<br>

Essa parte corresponde as cores e identificação das informações do mapa.
<br>
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/00b0cc85bc88eadf9e018a9982a756f590116eb8/Arquitetura_do_Software/Imagens/Tech_Stack_Map/cores%20e%20identififca%C3%A7%C3%A3o.png" alt="" width="300"
<br>
  
---

<br>
Nessa imagem é mostrado o nome do aplicativo sua descrição juntamente com as camadas que representam as tecnologias.
<br>
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/00b0cc85bc88eadf9e018a9982a756f590116eb8/Arquitetura_do_Software/Imagens/Tech_Stack_Map/camadas%20e%20tecnologias.png" alt="" width="500"
<br>

---

<br>
A seguir todas as tecnologias utilizadas:
<br>
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/00b0cc85bc88eadf9e018a9982a756f590116eb8/Arquitetura_do_Software/Imagens/Tech_Stack_Map/front-end.png" alt="" width="500"
<br>
  
<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/00b0cc85bc88eadf9e018a9982a756f590116eb8/Arquitetura_do_Software/Imagens/Tech_Stack_Map/back-end.png" alt="" width="500"
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/00b0cc85bc88eadf9e018a9982a756f590116eb8/Arquitetura_do_Software/Imagens/Tech_Stack_Map/banco%20de%20dados.png" alt="" width="500"
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/00b0cc85bc88eadf9e018a9982a756f590116eb8/Arquitetura_do_Software/Imagens/Tech_Stack_Map/Autentica%C3%A7%C3%A3o.png" alt="" width="500"
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/00b0cc85bc88eadf9e018a9982a756f590116eb8/Arquitetura_do_Software/Imagens/Tech_Stack_Map/Notifica%C3%A7%C3%B5es.png" alt="" width="500"
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/00b0cc85bc88eadf9e018a9982a756f590116eb8/Arquitetura_do_Software/Imagens/Tech_Stack_Map/geolocaliza%C3%A7%C3%A3o%20.png" alt="" width="500"
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/00b0cc85bc88eadf9e018a9982a756f590116eb8/Arquitetura_do_Software/Imagens/Tech_Stack_Map/deploy.png" alt="" width="500"
<br>

---
## Tabela de Tecnologia

|Camada|Tecnologias|Justificativa|
|-|-|-|
|Front-end|Flutter|O Flutter é um framework (usa a linguagem de programação Dart) que é bem interessante de ser utilizado, pois este possui alto desempenho, fluido e é multiplataforma (IOS, Android, Web, MacOs, Windows e Linux). Além disso, é de fácil integração com Firebase.|
|Back-end|Node.js + Express|Para lidar com várias conexões simultâneas, o Node.js é interessante de ser utilizado. Já o Express fica responsável por organizar as APIs, pelo motivo de possuir uma estrutura flexível e fluída.|
|Banco de Dados|PostgreSQL (PostGIS)|O PostgreSQL é um banco de dados relacional que é bom para armazenar dados mais complexos. O PostGIS é relevante porque ele gerencia dados geoespaciais de forma eficiente. Assim, o controle das funcionalidades de localização dos pacientes e de campanhas de vacinas se tornam mais eficazes. Este banco de dados também facilita a integração com o Mapbox.|
|Autenticação|Firebase Authentication|O Firebase Authentication fornece a autenticação segura com suporte a múltiplos provedores (email/senha, OAuth, etc). Ademais, a gestão e controle de acesso dos usuários se tornam simplificadas.|
|Notificações|Socket.IO + Firebase Cloud Messaging (FMC)|O Socket.IO possibilita comunicação bidirecional persistente, o qual permite atualizações instantâneas que são relevantes para os agendamentos no B Health. Já o FCM ajuda no envio confiável de notificações push, isso ocorre até quando o aplicativo está em segundo plano.|
|Geolocalização|Google Maps SDK|O Google Map SDK possui uma grande cobertura mais completa e atualizações frequentes de localização.|
|Deploy|Railway|Plataforma de deploy e infraestrutura moderna, usada para hospedar o backend Node.js e o banco de dados PostgreSQL. Para mais, ele fornece suporte integrado para múltiplas linguagens e bancos, com escalabilidade automática e monitoramento.|
