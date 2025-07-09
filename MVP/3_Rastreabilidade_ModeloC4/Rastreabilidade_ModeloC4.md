# Rastreabilidade com os Diagramas (Modelo C4)
<br>

<p align="justify">O MVP foi desenvolvido de forma alinhada ao Diagrama de Classes, utilizando as classes que estão diretamente relacionadas às funcionalidades implementadas. Também se considerou o Modelo C4, com referência aos diagramas de Contexto, Container e Componente, identificando onde cada parte do sistema atua. As interações entre os componentes foram pensadas para garantir uma comunicação fluida entre as camadas da aplicação, mantendo a estrutura organizada e coerente com os modelos projetados.
<br>
<br>
  
# Tabelas de Rastreabilidade
<br> 

<p align="justify">A seguir, serão apresentadas as principais funcionalidades do sistema, detalhadas com suas respectivas relações nos diagramas de classes e nas diferentes camadas da arquitetura C4. Para cada funcionalidade, é descrito o contexto geral, os containers envolvidos e os componentes que fazem parte do seu funcionamento, proporcionando uma visão clara e organizada da estrutura do sistema.
<br>
<br> 

## 1. Funcionalidade: Cadastro de Usuário
<br>

| Diagrama | Contexto |
|-|-|
|**Diagrama de Classes**| Utiliza as classes Usuário e Autenticação. |
|**Diagrama C4 (Contexto)**| A funcionalidade envolve o Aplicativo Móvel (Flutter Flow), o Serviço Back-end (Firebase) e o Banco de Dados (Firestore). |
| **Diagrama C4 (Container)** | A funcionalidade faz parte do container "Aplicativo Móvel", que se comunica com o "Serviço Back-end" e o "Firestore". |
|**Diagrama C4 (Componente)** | Conecta a Tela de Cadastro, o Controlador de Usuário, o Serviço de Autenticação e o Firestore para criar o registro do usuário. |
<br>

## 2. Funcionalidade: Login de Usuário
<br>

| Diagrama | Contexto |
| - | - |
| Diagrama de Classes | Utiliza as classes Usuário e Autenticação. |
| Diagrama C4 (Contexto) | A funcionalidade envolve o Aplicativo Móvel (Flutter Flow), o Serviço Back-end (Firebase) e Autenticação (Firebase Authentication) para validação de credenciais. |
| Diagrama C4 (Container) | A funcionalidade faz parte do container "Aplicativo Móvel", que se comunica com o "Serviço Back-end" e o "Firestore". |
| Diagrama C4 (Componente) | Conecta a Tela de Login, o Controlador de Autenticação, o Serviço de Autenticação e o Firestore/Firebase Authentication para validar e recuperar os dados do usuário. |
<br>

## 3. Funcionalidade: Consulta da Carteira de Vacinação
<br>

| Diagrama | Contexto |
| - | - |
| Diagrama de Classes | Utiliza as classes Paciente, Carteira Vacinação, Vacina e Dose. |
| Diagrama C4 (Contexto) | A funcionalidade envolve o Aplicativo Móvel (Flutter Flow), o Serviço Back-end (Firebase) e o Banco de Dados (Firestore). |
| Diagrama C4 (Container) | A funcionalidade faz parte do container "Aplicativo Móvel", que se comunica com o "Serviço Back-end" e o "Firestore". |
| Diagrama C4 (Componente) | Conecta a Tela Carteira de Vacina, o Controlador de Vacinas, o Serviço de Histórico de Vacinas e o Firestore para exibir as doses aplicadas. |
<br>

## 4. Funcionalidade: Mapa de Vacinação
<br>

| Diagrama | Contexto |
| - | - |
| Diagrama de Classes | Utiliza as classes Unidade Saúde, Endereço e Paciente. |
| Diagrama C4 (Contexto) | A funcionalidade envolve o Aplicativo Móvel (Flutter Flow), o Serviço Back-end (Firebase), o Banco de Dados (Firestore) e o Google Maps SDK para exibir os locais de vacinação. |
| Diagrama C4 (Container) | A funcionalidade faz parte do container "Aplicativo Móvel", que se comunica com o "Serviço Back-end", o "Firestore" e o "Google Maps SDK". |
| Diagrama C4 (Componente) | Conecta a Tela de Mapa de Vacinação, o Controlador de Mapas, o Serviço de Geolocalização, o Google Maps SDK e o Firestore para buscar e mostrar os locais no mapa. |
<br>

## 5. Funcionalidade: Mapa de Campanhas de Vacinação
<br>

| Diagrama | Contexto |
| - | - |
| Diagrama de Classes | Utiliza as classes Campanha, Unidade Saúde, Endereço e Paciente. |
| Diagrama C4 (Contexto) | A funcionalidade envolve o Aplicativo Móvel (Flutter Flow), o Serviço Back-end (Firebase), o Banco de Dados (Firestore) e o Google Maps SDK para exibir locais. |
| Diagrama C4 (Container) | A funcionalidade faz parte do container "Aplicativo Móvel", que se comunica com o "Serviço Back-end", o "Firestore" e o "Google Maps SDK". |
| Diagrama C4 (Componente) | Conecta a Tela de Mapa de Campanhas, o Controlador de Campanhas, o Controlador de Mapas, o Serviço de Geolocalização, o Google Maps SDK e o Firestore para exibir as campanhas no mapa. |
<br>
