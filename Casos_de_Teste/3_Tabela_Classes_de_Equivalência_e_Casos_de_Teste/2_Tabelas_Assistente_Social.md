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

## ASSISTENTE SOCIAL

### H12 - Como assistente social, gostaria de me cadastrar no aplicativo para que eu possa ter acesso ao aplicativo B Health
<br>

### <p align="center">Tabela de Equivalência
| CONDIÇÃO DE ENTRADA                                                 | CLASSES VÁLIDAS                                              | CLASSES INVÁLIDAS                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------ | ----------------------------------------- |
| Formulário de cadastro identifica ocupação como “Assistente Social” | Campo “ocupação” fixo e visível como “Assistente Social” (1) | Campo de ocupação ausente (2)             |
| Número do CRESS validado quando ocupação é “Assistente Social”      | Número CRESS válido e obrigatório (3)                        | CRESS inválido (4)                        |
| E-mail digitado segue padrão RFC 5322                               | E-mail com @, domínio e extensão correta (5)                 | E-mail com erro de digitação (6)          |
| E-mail não está cadastrado anteriormente                            | E-mail novo e único no sistema (7)                           | E-mail já utilizado por outro usuário (8) |
| Senha tem no mínimo 8 caracteres                                    | Senha com 8 ou mais caracteres (9)                           | Senha com menos de 8 caracteres (10)      |
| Senha contém letras maiúsculas, minúsculas e números                | Composição aceita, por exemplo, Sabrina123 (11)              | Senha composta apenas por letras (12)     |
| Confirmação de senha igual à senha digitada                         | Ambas senhas coincidem (13)                                  | Senhas diferentes (14)                    |
| Cadastro finalizado com sucesso                                     | Mensagem de “Cadastro realizado com sucesso” exibida (15)    | Mensagem não exibida (16)                 |

<br>

### <p align="center">Tabela de Casos de Teste
| CASOS DE TESTE   | CLASSES DE EQUIVALÊNCIA    | ENTRADAS                                                                                                                                   | RESULTADOS ESPERADOS                                                |
| ------ | -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------- |
| Caso 1 | 1, 3, 5, 7, 9, 11, 13, 15  | Ocupação “Assistente Social” visível, CRESS válido, e-mail correto e não cadastrado, senha forte com letras e números, confirmação correta | Cadastro realizado com sucesso                                      |
| Caso 2 | 2, 3, 5, 7, 9, 11, 13, 15  | Campo de ocupação ausente, demais campos válidos                                                                                           | Cadastro rejeitado (ocupação obrigatória ausente)                   |
| Caso 3 | 1, 4, 5, 7, 9, 11, 13, 15  | Ocupação correta, CRESS inválido, demais campos válidos                                                                                    | Cadastro rejeitado (CRESS inválido)                                 |
| Caso 4 | 1, 3, 6, 7, 9, 11, 13, 15  | CRESS válido, e-mail com erro de digitação (sem “@”), demais campos válidos                                                                | Cadastro rejeitado (formato de e-mail inválido)                     |
| Caso 5 | 1, 3, 5, 8, 9, 11, 13, 15  | CRESS válido, e-mail já cadastrado, demais dados corretos                                                                                  | Cadastro rejeitado (e-mail duplicado)                               |
| Caso 6 | 1, 3, 5, 7, 10, 11, 13, 15 | Senha com menos de 8 caracteres, demais campos válidos                                                                                     | Cadastro rejeitado (senha muito curta)                              |
| Caso 7 | 1, 3, 5, 7, 9, 12, 13, 15  | Senha composta apenas por letras, sem números                                                                                              | Cadastro rejeitado (senha fora do padrão exigido)                   |
| Caso 8 | 1, 3, 5, 7, 9, 11, 14, 15  | Confirmação de senha diferente da senha principal                                                                                          | Cadastro rejeitado (senhas não coincidem)                           |
| Caso 9 | 1, 3, 5, 7, 9, 11, 13, 16  | Todos os campos válidos, mas mensagem de confirmação não exibida                                                                           | Cadastro realizado, mas sem feedback ao usuário (erro de interface) |

<br>

---

### H13 - Como assistente social, gostaria de realizar o login no aplicativo para que eu tenha acesso aos serviços do aplicativo
<br>

### <p align="center">Tabela de Equivalência
| CONDIÇÃO DE ENTRADA                                                | CLASSES VÁLIDAS                                            | CLASSES INVÁLIDAS           |
| ------------------------------------------------------------------ | ---------------------------------------------------------- | --------------------------- |
| Campos de e-mail e senha preenchidos no login                      | Ambos os campos preenchidos corretamente (1)               | Campos em branco (2)        |
| E-mail e senha são válidos e cadastrados                           | Credenciais correspondem ao cadastro (3)                   | Campos incorretos (4)       |
| Clique em “Esqueci minha senha” disponível                         | Link presente e funcional para recuperação por e-mail (5)  | Link ausente (6)            |
| Após login, usuário é direcionado à interface de assistente social | Interface específica com funções de assistente exibida (7) | Redirecionamento errado (8) |

<br>

### <p align="center">Tabela de Casos de Teste
| CASOS DE TESTE  | CLASSES DE EQUIVALÊNCIA | ENTRADAS                                                                                                                        | RESULTADOS ESPERADOS                                         |
| ------ | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| Caso 1 | 1, 3, 5, 7              | E-mail e senha preenchidos corretamente, credenciais válidas, link “Esqueci minha senha” funcional, redirecionamento correto    | Login bem-sucedido e acesso à interface de assistente social |
| Caso 2 | 2, 3, 5, 7              | Campos de login em branco, mas credenciais seriam válidas                                                                       | Login rejeitado (campos obrigatórios não preenchidos)        |
| Caso 3 | 1, 4, 5, 7              | Campos preenchidos, mas e-mail e senha incorretos                                                                               | Login rejeitado (credenciais inválidas)                      |
| Caso 4 | 1, 3, 6, 7              | Credenciais corretas, mas link “Esqueci minha senha” ausente                                                                    | Falha na usabilidade (sem opção de recuperação)              |
| Caso 5 | 1, 3, 5, 8              | Credenciais corretas, link funcional, mas redirecionamento vai para interface errada (ex: perfil de paciente ou tela em branco) | Erro de redirecionamento (acesso à área incorreta)           |

<br>

---

### H14 - Como assistente social, quero agendar visitas no aplicativo, para que os pacientes sejam notificados.
<br>

### <p align="center">Tabela de Equivalência
| CONDIÇÃO DE ENTRADA                                                  | CLASSES VÁLIDAS                                | CLASSES INVÁLIDAS                                                    |
| -------------------------------------------------------------------- | ---------------------------------------------- | -------------------------------------------------------------------- |
| Paciente existe e está ativo no banco PostgreSQL                     | Paciente cadastrado e ativo (1)                | Paciente inexistente (2)                                             |
| Data e hora da visita selecionadas                                   | Data e hora escolhidas (3)                     | Campo de data/hora não selecionado (4)                               |
| Data e hora armazenadas corretamente no sistema                      | Registro salvo com sucesso no banco (5)        | Falha ao armazenar no banco (6)                                      |
| Assistente social deseja cancelar visita agendada                    | Cancela agendamento com sucesso (7)            | Sistema impede alteração (8)                                         |
| Nova visita não colide com outro agendamento                         | Data e hora disponíveis e não sobrepostas (9)  | Data e hora já estão ocupadas por outro agendamento (10)             |
| Validação feita tanto no cliente (Flutter) quanto no servidor (Node) | Ambas as camadas rejeitam datas inválidas (11) | Sistema aceita datas passadas por falha na interface ou backend (12) |

<br>

### <p align="center">Tabela de Casos de Teste
| CASOS DE TESTE   | CLASSES DE EQUIVALÊNCIA | ENTRADAS                                                                                                                                     | RESULTADOS ESPERADOS                                                  |
| ------ | ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Caso 1 | 1, 3, 5, 7, 9, 11       | Paciente cadastrado e ativo, data/hora escolhidas, registro salvo no banco, cancelamento possível, horário não sobreposto, validação correta | Agendamento e cancelamento funcionam corretamente                     |
| Caso 2 | 2, 3, 5, 7, 9, 11       | Paciente inexistente, data/hora escolhidas, registro salvo, cancelamento permitido, horário livre, validação correta                         | Falha no agendamento (paciente não encontrado)                        |
| Caso 3 | 1, 4, 5, 7, 9, 11       | Paciente ativo, data/hora não selecionadas, registro salvo, cancelamento permitido, horário livre, validação correta                         | Falha: data/hora obrigatória não selecionada                          |
| Caso 4 | 1, 3, 6, 7, 9, 11       | Paciente ativo, data/hora escolhidas, falha ao armazenar no banco, cancelamento permitido, horário livre, validação correta                  | Erro de persistência (dados não salvos)                               |
| Caso 5 | 1, 3, 5, 8, 9, 11       | Paciente ativo, data/hora escolhidas, registro salvo, sistema impede cancelamento, horário livre, validação correta                          | Cancelamento não realizado (restrição do sistema)                     |
| Caso 6 | 1, 3, 5, 7, 10, 11      | Paciente ativo, data/hora escolhidas, registro salvo, cancelamento permitido, horário já ocupado, validação correta                          | Conflito de agendamento (colisão de horários)                         |
| Caso 7 | 1, 3, 5, 7, 9, 12       | Paciente ativo, data/hora escolhidas, registro salvo, cancelamento permitido, horário livre, sistema aceita data passada                     | Falha: sistema permitiu agendamento com data inválida (sem validação) |

<br>

---


### H17 - Como assistente social, eu gostaria de visualizar uma lista de pacientes prioritários (idosos, gestantes, crianças), para planejar visitas de acordo com a prioridade.
<br>

### <p align="center">Tabela de Equivalência
| CONDIÇÃO DE ENTRADA                                                           | CLASSES VÁLIDAS                                                              | CLASSES INVÁLIDAS                                                                  |
| ----------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Lista exibe apenas pacientes prioritários                                     | Lista com idosos, gestantes, crianças com vacinação incompleta (1)           | Lista contém pacientes fora dos grupos prioritários (2)                            |
| Sistema identifica prioridade automaticamente                                 | Identificação correta via data de nascimento, sexo ou campo "prioridade" (3) | Sistema não identifica corretamente o grupo de prioridade (4)                      |
| Ordenação por tipo de prioridade disponível                                   | Lista pode ser ordenada por idoso, gestante ou criança (5)                   | Sistema não permite ordenação (6)                                                  |
| Lista atualizada automaticamente                                              | Novo paciente com prioridade aparece na lista após cadastro (7)              | Novo paciente com prioridade não aparece na lista (8)                              |
| Sistema separa visualmente os tipos de prioridade                             | Uso correto de cores ou ícones (verde, amarelo, vermelho) conforme nível (9) | Ausência de distinção visual (10)                                                  |
| Paciente com esquema vacinal incompleto exibido mesmo sem estar em grupo alvo | Inclusão de pacientes com vacinação pendente (11)                            | Exclusão de pacientes fora dos grupos-alvo mas com esquema vacinal incompleto (12) |

<br>

### <p align="center">Tabela de Casos de Teste
| CASOS DE TESTE   | CLASSES DE EQUIVALÊNCIA | ENTRADAS                                                                                                                                                                                                                                         | RESULTADOS ESPERADOS                                                     |
| ------ | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| Caso 1 | 1, 3, 5, 7, 9, 11       | Lista exibe apenas idosos, gestantes e crianças com vacinação incompleta, prioridade identificada corretamente, ordenação funcional, lista atualiza ao cadastrar, distinção visual presente, inclui paciente fora do grupo com vacina incompleta | Lista correta, bem organizada e funcional                                |
| Caso 2 | 2, 3, 5, 7, 9, 11       | Lista contém pacientes fora do grupo prioritário, prioridade identificada, ordenação funcional, lista atualiza, visualização correta, pacientes com vacina pendente incluídos                                                                    | Erro: lista exibe pacientes não prioritários                             |
| Caso 3 | 1, 4, 5, 7, 9, 11       | Lista com apenas grupos prioritários, mas sistema falha ao identificar corretamente, ordenação ok, lista atualiza, distinção visual ok, pacientes pendentes incluídos                                                                            | Falha de classificação (prioridade não atribuída corretamente)           |
| Caso 4 | 1, 3, 6, 7, 9, 11       | Lista correta com prioridade bem identificada, mas sistema não permite ordenação, lista atualiza, visual ok, inclui pacientes com vacina incompleta                                                                                              | Funcionalidade de ordenação ausente                                      |
| Caso 5 | 1, 3, 5, 8, 9, 11       | Lista correta, prioridade identificada, ordenação ok, mas novo paciente prioritário não aparece após cadastro                                                                                                                                    | Falha de atualização automática                                          |
| Caso 6 | 1, 3, 5, 7, 10, 11      | Lista correta, prioridade bem atribuída, ordenação ok, lista atualiza, mas sem distinção visual por tipo                                                                                                                                         | Interface pouco clara (ausência de destaque visual)                      |
| Caso 7 | 1, 3, 5, 7, 9, 12       | Lista correta, prioridade bem identificada, ordenação e atualização funcionais, visual ok, mas paciente com vacinação pendente fora de grupo não aparece                                                                                         | Omissão de paciente com vacinação incompleta fora de grupos prioritários |

<br>

---


### H19 - Como assistente social, eu gostaria de acessar o perfil completo de um paciente, para visualizar seus dados pessoais antes de uma visita.
<br>

### <p align="center">Tabela de Equivalência
| CONDIÇÃO DE ENTRADA                                                    | CLASSES VÁLIDAS                                             | CLASSES INVÁLIDAS                             |
| ---------------------------------------------------------------------- | ----------------------------------------------------------- | --------------------------------------------- |
| Paciente está cadastrado no sistema                                    | Perfil acessível para paciente existente (1)                | Perfil inexistente (2)                        |
| Dados exibidos incluem nome, contato, endereço e carteira de vacinação | Todos os campos necessários visíveis (3)                    | Dados incompletos (4)                         |
| Assistente social não pode editar dados pessoais                       | Campos como nome, endereço, CNS, CPF são apenas leitura (5) | Permissão indevida para editar (6)            |
| Carteira de vacinação é exibida no mesmo scroll da página do perfil    | Exibição contínua com rolagem vertical (7)                  | Exibição separada em abas (8)                 |
| Assistente social não pode alterar a carteira de vacinação             | Apenas visualização permitida (9)                           | Sistema permite editar e remover vacinas (10) |

<br>

### <p align="center">Tabela de Casos de Teste
| CASOS DE TESTE  | CLASSES DE EQUIVALÊNCIA | ENTRADAS                                                                                                                                                                                                 | RESULTADOS ESPERADOS                                              |
| ------ | ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| Caso 1 | 1, 3, 5, 7, 9           | Paciente cadastrado, dados completos visíveis (nome, contato, endereço, carteira), campos de dados pessoais são apenas leitura, exibição contínua via scroll, carteira de vacinação visível e sem edição | Perfil exibido corretamente para assistente social                |
| Caso 2 | 2, 3, 5, 7, 9           | Paciente não cadastrado, demais regras em conformidade                                                                                                                                                   | Erro: perfil inexistente                                          |
| Caso 3 | 1, 4, 5, 7, 9           | Paciente cadastrado, dados incompletos (faltando nome ou endereço, por exemplo), campos bloqueados corretamente, scroll único, carteira visualizada                                                      | Exibição incompleta (dados faltando)                              |
| Caso 4 | 1, 3, 6, 7, 9           | Paciente válido, dados completos, mas assistente pode editar nome ou endereço                                                                                                                            | Falha de segurança: permissão indevida para editar dados pessoais |
| Caso 5 | 1, 3, 5, 8, 9           | Paciente válido, dados corretos, visualização em abas separadas, carteira exibida, mas não editável                                                                                                      | Interface não ideal (exibição separada do perfil)                 |
| Caso 6 | 1, 3, 5, 7, 10          | Paciente válido, dados completos, exibição por scroll, carteira de vacinação permite edição/remoção                                                                                                      | Erro crítico: alteração indevida na carteira de vacinação         |

<br>
