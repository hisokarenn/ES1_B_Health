# Diagrama de Containers

<br>
<p align="justify">Um diagrama de containers, no contexto do modelo C4, é uma representação visual que detalha como um sistema de software é dividido em contêineres, que são unidades de implantação como aplicativos web, bancos de dados ou microserviços. Ele mostra a relação entre esses containers e como eles interagem entre si, fornecendo uma visão de alto nível da arquitetura do sistema focada em tecnologia.
<br>
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/06017e5db1a0395f34628e82d2979f100f17de60/Arquitetura_do_Software/Imagens/Modelo_C4/2_Diagrama_de_Containers/DiagramaDeContainers2.drawio.png" alt="" width="900"
<br>
<p align="center"> Diagrama de Containers produzido no Draw.io
<br>
<br>

## Explicação sobre os itens pertencentes ao Diagrama de Containers

<br>
<p align="justify">Esta parte do diagrama mostra os diferentes tipos de usuários que utilizam o sistema, chamados de personas, cada um com papéis e necessidades distintas. Entre eles estão pacientes, profissionais da saúde e assistentes sociais. As interações de cada perfil com o sistema são representadas de acordo com suas funções e níveis de acesso. Isso contribui para entender como cada usuário utiliza o sistema em seu contexto.

<br>
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/06017e5db1a0395f34628e82d2979f100f17de60/Arquitetura_do_Software/Imagens/Modelo_C4/2_Diagrama_de_Containers/personasContainer.png" alt="" width="1000"
<br>

---

<br>
<p align="justify">Esta parte do diagrama representa a conexão entre o aplicativo móvel e o serviço de back-end. É por meio dessa ligação que as requisições do aplicativo móvel são processadas e encaminhadas para as tecnologias envolvidas. O back-end executa as lógicas de negócio e garante o funcionamento dos serviços. Essa comunicação é essencial para o pleno funcionamento do sistema.
<br>
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/eae790ebcaaa969003e8192d1acbb5143df58b88/Arquitetura_do_Software/Imagens/Modelo_C4/2_Diagrama_de_Containers/backEndeApp.png" alt="" width="500"
<br>

---

<br>
<p align="justify">Esta seção do diagrama ilustra a relação entre o serviço de back-end e o banco de dados. É por meio dessa conexão que o sistema realiza o armazenamento e a recuperação das informações. O back-end atua como intermediário, gerenciando o acesso e a integridade dos dados.
<br>
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/eae790ebcaaa969003e8192d1acbb5143df58b88/Arquitetura_do_Software/Imagens/Modelo_C4/2_Diagrama_de_Containers/backEndEbanco.png" alt="" width="900"
<br>

---

<br>
<p align="justify">Esta parte do diagrama destaca dois serviços diretamente integrados ao aplicativo, devido ao uso da tecnologia Flutter. São eles:
1. Firebase Authentication: responsável pelo controle de acesso; <br>
2. Firebase Cloud Messaging (FCM): gerencia o envio de notificações. <br>
Ambos se conectam de forma nativa ao aplicativo. Essa integração facilita a comunicação e a segurança dentro da plataforma.
<br>
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/eae790ebcaaa969003e8192d1acbb5143df58b88/Arquitetura_do_Software/Imagens/Modelo_C4/2_Diagrama_de_Containers/sist1.png" alt="" width="800"
<br>

---

<br>
<p align="justify">Esta seção do diagrama apresenta as APIs gerenciadas pelo back-end, que são utilizadas pelo aplicativo. Essas APIs permitem a comunicação entre o app e os serviços internos, garantindo respostas eficientes às solicitações dos usuários. As conexões e dependências entre esses elementos também são representadas. Isso evidencia o papel central das APIs na integração da aplicação.
<br>
<br>

<p align="center"> <img src="https://github.com/hisokarenn/ES1-TP1/blob/eae790ebcaaa969003e8192d1acbb5143df58b88/Arquitetura_do_Software/Imagens/Modelo_C4/2_Diagrama_de_Containers/sist2.png" alt="" width="600"
<br>
