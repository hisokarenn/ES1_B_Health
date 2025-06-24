# Tabela de Classes de Equivalência
<br>
<p align="justify">Uma tabela de classe de equivalência é um instrumento usado para organizar e categorizar elementos de um conjunto em grupos que compartilham uma característica comum, ou seja, são considerados equivalentes em relação a uma propriedade específica. Essa tabela facilita a identificação e análise de conjuntos de dados, especialmente em áreas como programação, testes de software e matemática. 
<br>
<br>

# Tabela de Casos de Teste
<br>
<p align="justify">Uma tabela de casos de teste é uma ferramenta utilizada em testes de software para organizar e documentar os diferentes cenários de teste de um sistema. Ela lista condições de entrada, ações esperadas e resultados obtidos, garantindo uma cobertura abrangente dos testes. 
<br>
<br>

### Organização
<p align="justify">Foram criadas quatro personas representando os principais usuários do sistema, cada uma com cinco histórias de usuário, totalizando 20 histórias. Com base nessas histórias, foram elaboradas cinco tabelas de classes de equivalência para identificar entradas válidas e inválidas. A partir dessas tabelas, foram desenvolvidos cinco conjuntos de casos de teste equivalentes. Essa organização visa garantir a cobertura dos principais fluxos do sistema. O objetivo é validar o comportamento esperado de cada funcionalidade.
<br>
<br>

## MÉDICO

### H26 - Como médico, eu gostaria de me cadastrar no aplicativo para que eu possa ter acesso ao aplicativo B Health.
<br>

### <p align="center">Tabela de Equivalência
| CONDIÇÃO DE ENTRADA                    | CLASSES VÁLIDAS                                       | CLASSES INVÁLIDAS                                   |
| -------------------------------------- | ----------------------------------------------------- | --------------------------------------------------- |
| Campo de ocupação é fixo como “Médico” | Campo “Médico” pré-definido e não editável (1)        | Campo permite editar ocupação (2)                   |
| CRM é obrigatório e validado           | CRM inserido corretamente e validado (3)              | CRM inválido (4)                                    |
| E-mail válido é exigido                | E-mail com formato válido é aceito (5)                | E-mail em formato inválido (6)                      |
| Senha com no mínimo 8 caracteres       | Senha com 8 ou mais caracteres (7)                    | Senha com menos de 8 caracteres e sem validação (8) |
| Senha contém letras e números          | Senha com letras maiúsculas, minúsculas e números (9) | Senha com apenas números ou apenas letras (10)      |
| Validação de senha duplicada           | Senhas iguais e válidas (11)                          | Senhas diferentes (12)                              |
| Acesso ao perfil do médico             | Acesso liberado com funcionalidades médicas (13)      | Acesso liberado com funcionalidades erradas (14)    |

<br>

### <p align="center">Tabela de Casos de Teste
| CASOS DE TESTE | CLASSES DE EQUIVALÊNCIA      | ENTRADAS                                                   | RESULTADOS ESPERADOS                      |
|----------------|------------------------------|------------------------------------------------------------|------------------------------------------|
| Caso 1         | 1, 3, 5, 7, 9, 11, 13        | Campo "Médico" fixo, CRM válido, e-mail válido, senha ≥8 caracteres com letras e números, senhas iguais, acesso ao perfil médico | Cadastro realizado com sucesso e acesso correto |
| Caso 2         | 2, 3, 5, 7, 9, 11, 13        | Campo de ocupação editável, CRM válido, e-mail válido, senha correta, senhas iguais, acesso ao perfil | Falha: campo de ocupação não deveria ser editável |
| Caso 3         | 1, 4, 5, 7, 9, 11, 13        | Campo fixo, CRM inválido, e-mail válido, senha correta, senhas iguais, acesso ao perfil | Cadastro rejeitado por CRM inválido     |
| Caso 4         | 1, 3, 6, 7, 9, 11, 13        | Campo fixo, CRM válido, e-mail mal formatado, senha correta, senhas iguais, acesso ao perfil | Falha de validação de e-mail             |
| Caso 5         | 1, 3, 5, 8, 9, 11, 13        | Campo fixo, CRM válido, e-mail válido, senha com menos de 8 caracteres, senhas iguais, acesso ao perfil | Rejeição por senha muito curta           |
| Caso 6         | 1, 3, 5, 7, 10, 11, 13       | Campo fixo, CRM válido, e-mail válido, senha longa com apenas números, senhas iguais, acesso ao perfil | Rejeição por falta de complexidade na senha |
| Caso 7         | 1, 3, 5, 7, 9, 12, 13        | Campo fixo, CRM válido, e-mail válido, senha correta, senhas diferentes, acesso ao perfil | Rejeição por senhas não coincidentes     |
| Caso 8         | 1, 3, 5, 7, 9, 11, 14        | Campo fixo, CRM válido, e-mail válido, senha correta, senhas iguais, acesso com funcionalidades erradas | Erro de permissão ao acessar perfil      |
<br>

---

### H27 - Como médico, eu gostaria de realizar o login no aplicativo para que eu tenha acesso aos serviços do aplicativo.
<br>

### <p align="center">Tabela de Equivalência
| CONDIÇÃO DE ENTRADA                     | CLASSES VÁLIDAS                                  | CLASSES INVÁLIDAS                                         |
| --------------------------------------- | ------------------------------------------------ | --------------------------------------------------------- |
| CRM ou e-mail cadastrado                | CRM ou E-mail previamente cadastrado (1)         | Login aceito com dados não cadastrados e inexistentes (2) |
| Senha incorreta                         | Senha corresponde ao cadastro (3)                | Senha incorreta (4)                                       |
| Cadastro validado oficialmente          | Cadastro válido via integração ou manual (5)     | Validação pendente e login permitido (6)                  |
| Link de recuperação de senha disponível | Link “Esqueci minha senha” funcional (7)         | Link ausente na interface (8)                             |
| Acesso ao painel exclusivo do médico    | Direcionado para painel correto após o login (9) | Acesso negado após login (10)                             |

<br>

### <p align="center">Tabela de Casos de Teste
| CASOS DE TESTE | CLASSES DE EQUIVALÊNCIA | ENTRADAS                                                                                                         | RESULTADOS ESPERADOS                             |
| -------------- | ----------------------- | ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| Caso 1         | 1, 3, 5, 7, 9           | Login com CRM cadastrado, senha correta, cadastro validado, link de recuperação visível, acesso ao painel médico | Login bem-sucedido com acesso completo           |
| Caso 2         | 2, 3, 5, 7, 9           | CRM/e-mail inexistente, senha correta, cadastro validado, link visível, acesso ao painel médico                  | Erro: login permitido com credenciais inválidas  |
| Caso 3         | 1, 4, 5, 7, 9           | CRM cadastrado, senha incorreta, cadastro validado, link visível, painel acessível                               | Login rejeitado por senha inválida               |
| Caso 4         | 1, 3, 6, 7, 9           | CRM válido, senha correta, validação pendente, link visível, painel acessível                                    | Erro de segurança: login permitido sem validação |
| Caso 5         | 1, 3, 5, 8, 9           | CRM válido, senha correta, cadastro validado, link de recuperação ausente, painel acessível                      | Interface incompleta (sem link de recuperação)   |
| Caso 6         | 1, 3, 5, 7, 10          | CRM válido, senha correta, cadastro validado, link funcional, acesso negado ao painel                            | Falha no redirecionamento ao painel médico       |

<br>

---

### H28 - Como médico, eu gostaria de acessar uma lista de pacientes, para que eu possa acessar o seu perfil e carteira de vacina.
<br>

### <p align="center">Tabela de Equivalência
| CONDIÇÃO DE ENTRADA                                                                 | CLASSES VÁLIDAS                                                      | CLASSES INVÁLIDAS                                            |
| ----------------------------------------------------------------------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------ |
| Lista de pacientes apresentada em scroll contínuo e ordenada alfabeticamente        | Lista carrega automaticamente e está organizada por nome (1)         | Lista incompleta (2)                                         |
| Pesquisa por nome completo, CPF ou CNS funciona com filtragem em tempo real         | Resultados são filtrados corretamente conforme entrada do médico (3) | Pesquisa sem retorno correto (4)                             |
| Acesso limitado a um paciente por vez                                               | Médico acessa apenas um perfil de cada vez (5)                       | Acesso simultâneo a múltiplos perfis (6)                     |
| Perfil exibe nome completo, CNS e carteira de vacinação                             | Informações corretas e completas são exibidas (7)                    | Dados inconsistentes ao cadastro (8)                         |
| Médico não pode alterar dados pessoais do paciente (nome, endereço, CNS, e-mail)    | Campos protegidos contra edição (9)                                  | Sistema permite alterações indevidas em dados sensíveis (10) |
| Dados e carteira de vacinação são exibidos na mesma tela (scroll vertical contínuo) | Exibição única e fluida em tela única com rolagem (11)               | Interface dividida em abas (12)                              |
| Médico pode editar a carteira de vacinação                                          | Alterações autorizadas e salvas corretamente (13)                    | Edição não permitida (14)                                    |

<br>

### <p align="center">Tabela de Casos de Teste
| CASOS DE TESTE | CLASSES DE EQUIVALÊNCIA | ENTRADAS                                                                                                                                                                 | RESULTADOS ESPERADOS                               |
| -------------- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------- |
| Caso 1         | 1, 3, 5, 7, 9, 11, 13   | Lista carregada e ordenada, busca em tempo real, acesso a 1 paciente por vez, perfil completo, campos protegidos, dados em scroll contínuo, edição da carteira permitida | Acesso e interação corretos com perfil do paciente |
| Caso 2         | 2, 3, 5, 7, 9, 11, 13   | Lista incompleta, busca em tempo real, acesso único, perfil completo, dados protegidos, scroll contínuo, edição da carteira ok                                           | Problema na listagem inicial dos pacientes         |
| Caso 3         | 1, 4, 5, 7, 9, 11, 13   | Lista correta, busca sem retorno correto, acesso único, perfil completo, campos protegidos, scroll contínuo, edição da carteira permitida                                | Falha na funcionalidade de pesquisa                |
| Caso 4         | 1, 3, 6, 7, 9, 11, 13   | Lista correta, busca funcional, acesso simultâneo a múltiplos perfis, perfil completo, campos protegidos, scroll contínuo, edição da carteira permitida                  | Falha de segurança: acesso múltiplo indevido       |
| Caso 5         | 1, 3, 5, 8, 9, 11, 13   | Lista correta, busca funcional, acesso único, perfil com dados inconsistentes, campos protegidos, scroll contínuo, edição da carteira permitida                          | Dados do paciente incorretos ou incompletos        |
| Caso 6         | 1, 3, 5, 7, 10, 11, 13  | Lista correta, busca funcional, acesso único, perfil completo, sistema permite alteração de dados sensíveis, scroll contínuo, edição da carteira ok                      | Restrição de edição violada                        |
| Caso 7         | 1, 3, 5, 7, 9, 12, 13   | Lista correta, busca funcional, acesso único, perfil completo, campos protegidos, interface em abas, edição da carteira permitida                                        | Layout da interface despadronizado                 |
| Caso 8         | 1, 3, 5, 7, 9, 11, 14   | Lista correta, busca funcional, acesso único, perfil completo, campos protegidos, scroll contínuo, edição da carteira não permitida                                      | Restrição inadequada na edição da carteira         |

<br>

---

### H31 - Como usuário (médico) do aplicativo B Health, eu gostaria de visualizar avisos sobre campanhas de vacinação, para informar sobre elas ao paciente durante uma consulta.
<br>

### <p align="center">Tabela de Equivalência
| CONDIÇÃO DE ENTRADA                   | CLASSES VÁLIDAS                             | CLASSES INVÁLIDAS                      |
| ------------------------------------- | ------------------------------------------- | -------------------------------------- |
| Visualizar apenas campanhas ativas    | Campanhas ativas são exibidas no mapa (1)   | Campanhas inativas são exibidas (2)    |
| Médico não pode publicar campanhas    | Médico apenas visualiza campanhas (3)       | Médico consegue publicar campanhas (4) |
| Campanhas contém datas visíveis       | Sistema exibe data de início e fim (5)      | Datas não são exibidas (6)             |
| Campanha emergencial notifica médicos | Notificação push é enviada via Firebase (7) | Notificação não é enviada (8)          |

<br>

### <p align="center">Tabela de Casos de Teste
| CASOS DE TESTE | CLASSES DE EQUIVALÊNCIA | ENTRADAS                                                                                             | RESULTADOS ESPERADOS                            |
| -------------- | ----------------------- | ---------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| Caso 1         | 1, 3, 5, 7              | Campanhas ativas exibidas, médico apenas visualiza, datas visíveis, notificação enviada via Firebase | Comportamento esperado                          |
| Caso 2         | 2, 3, 5, 7              | Campanhas inativas exibidas, médico apenas visualiza, datas visíveis, notificação enviada            | Exibição indevida de campanhas                  |
| Caso 3         | 1, 4, 5, 7              | Campanhas ativas exibidas, médico publica campanha, datas visíveis, notificação enviada              | Restrição violada (médico não deveria publicar) |
| Caso 4         | 1, 3, 6, 7              | Campanhas ativas exibidas, médico apenas visualiza, datas ausentes, notificação enviada              | Falta de informação (datas não exibidas)        |
| Caso 5         | 1, 3, 5, 8              | Campanhas ativas exibidas, médico apenas visualiza, datas visíveis, notificação não enviada          | Falha na comunicação (sem push)                 |

<br>

---

### H32 - Como médico, eu gostaria de saber os locais onde as campanhas de vacinação estão ocorrendo, através de um mapa de vacinação interativo, para que eu possa orientar o paciente a ir até esse lugar se vacinar.
<br>

### <p align="center">Tabela de Equivalência
| CONDIÇÃO DE ENTRADA                    | CLASSES VÁLIDAS                                           | CLASSES INVÁLIDAS                             |
| -------------------------------------- | --------------------------------------------------------- | --------------------------------------------- |
| Notificação exibe locais das campanhas | Locais exibidos na notificação push (1)                   | Locais ausentes na notificação (2)            |
| Endereço completo visível              | Endereço completo exibido no mapa (3)                     | Endereço incompleto (4)                       |
| Período da campanha visível            | Médico vê o intervalo da campanha (5)                     | Período não é informado (6)                   |
| Dados são atualizados pela enfermagem  | Alterações feitas pela enfermagem aparecem no sistema (7) | Sistema não reflete alterações (8)            |
| Médico vê apenas sua jurisdição        | Apenas locais do município do médico são exibidos (9)     | Locais de outros municípios são exibidos (10) |

<br>

### <p align="center">Tabela de Casos de Teste
| CASOS DE TESTE | CLASSES DE EQUIVALÊNCIA | ENTRADAS                                                                                                                                                | RESULTADOS ESPERADOS                     |
| -------------- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------- |
| Caso 1         | 1, 3, 5, 7, 9           | Notificação com locais, mapa com endereço completo, campanha de 01 a 15/07, atualização feita pela enfermagem, locais do município do médico            | Exibição correta das informações         |
| Caso 2         | 2, 3, 5, 7, 9           | Notificação sem locais, mapa com endereço completo, campanha de 01 a 15/07, atualização feita pela enfermagem, locais do município do médico            | Notificação incompleta (locais ausentes) |
| Caso 3         | 1, 4, 5, 7, 9           | Notificação com locais, endereço incompleto no mapa, campanha de 01 a 15/07, atualização feita pela enfermagem, locais do município do médico           | Mapa apresenta erro de localização       |
| Caso 4         | 1, 3, 6, 7, 9           | Notificação com locais, endereço completo no mapa, sem período informado, atualização feita pela enfermagem, locais do município do médico              | Falta informação do período da campanha  |
| Caso 5         | 1, 3, 5, 8, 9           | Notificação com locais, endereço completo no mapa, campanha de 01 a 15/07, sistema não refletiu alterações da enfermagem, locais do município do médico | Dados desatualizados no sistema          |
| Caso 6         | 1, 3, 5, 7, 10          | Notificação com locais, endereço completo no mapa, campanha de 01 a 15/07, atualização feita pela enfermagem, locais de outros municípios exibidos      | Médicos acessam locais indevidos         |

<br>
