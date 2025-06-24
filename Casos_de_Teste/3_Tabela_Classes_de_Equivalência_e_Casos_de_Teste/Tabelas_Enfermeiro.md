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

## ENFERMEIRO
### H33 - Como enfermeiro, eu quero me cadastrar no aplicativo, para que eu possa acessar as funcionalidades
<br>

### <p align="center">Tabela de Equivalência
| **CONDIÇÃO DE ENTRADA**                                                               | **CLASSES VÁLIDAS**                                          | **CLASSES INVÁLIDAS**                       |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------- |
| COREN válido e ativo                                                                  | COREN reconhecido pelo sistema e com status ativo (1)        | COREN inválido (2)                          |
| Senha contém ao menos 8 caracteres, com letra maiúscula, número e símbolo (@, # etc.) | Senha no formato exigido (3)                                 | Senha com menos de 8 caracteres (4)         |
| Campos obrigatórios preenchidos: Nome, COREN, e-mail institucional, unidade de saúde  | Todos os dados inseridos corretamente (5)                    | Campos obrigatórios ausentes (6)            |
| COREN inativo bloqueia conta após verificação manual em até 24h                       | Conta bloqueada corretamente com registro do motivo (7)      | COREN inativo continua com acesso (8)       |
| Três tentativas de login incorretas bloqueiam a conta por 1h                          | Bloqueio realizado corretamente após terceira tentativa (11) | Tentativas ilimitadas (12)                  |
| E-mail de bloqueio enviado com motivo e link para redefinir senha                     | E-mail com mensagem e link enviado após bloqueio (13)        | Nenhuma notificação enviada (14)            |
| Sessão expirada após inatividade exige novo login                                     | Sessão finalizada automaticamente e acesso bloqueado (15)    | Sessão permanece ativa indefinidamente (16) |

<br>

### <p align="center">Tabela de Casos de Teste
| **CASOS DE TESTE** | **CLASSES DE EQUIVALÊNCIA** | **ENTRADAS**                                                                                                                                         | **RESULTADOS ESPERADOS**                       |
| ------------------ | --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| Caso 1             | 1, 3, 5, 7, 11, 13, 15      | COREN válido e ativo, senha forte, todos os dados preenchidos, COREN inativo bloqueado, 3 falhas de login, e-mail de bloqueio enviado, sessão expira | Acesso controlado corretamente                 |
| Caso 2             | 2, 3, 5, 7, 11, 13, 15      | COREN inválido, senha forte, dados completos, verificação manual ativa, login incorreto 3x, e-mail enviado, sessão expira                            | Cadastro rejeitado (COREN inválido)            |
| Caso 3             | 1, 4, 5, 7, 11, 13, 15      | COREN válido, senha fraca (< 8 caracteres), dados completos, verificação manual ativa, bloqueio por login, e-mail enviado, sessão expira             | Senha rejeitada por padrão incorreto           |
| Caso 4             | 1, 3, 6, 7, 11, 13, 15      | COREN válido, senha forte, dados incompletos, verificação ativa, login incorreto 3x, e-mail enviado, sessão expira                                   | Cadastro incompleto (campos obrigatórios)      |
| Caso 5             | 1, 3, 5, 8, 11, 13, 15      | COREN válido, senha forte, dados completos, COREN inativo permanece com acesso, bloqueio por login, e-mail enviado, sessão expira                    | Falha de segurança (COREN inativo com acesso)  |
| Caso 6             | 1, 3, 5, 7, 12, 13, 15      | COREN válido, senha forte, dados completos, verificação manual OK, tentativas ilimitadas de login, e-mail enviado, sessão expira                     | Falha: sem bloqueio após tentativas erradas    |
| Caso 7             | 1, 3, 5, 7, 11, 14, 15      | COREN válido, senha forte, dados completos, verificação OK, 3 tentativas erradas, nenhum e-mail enviado, sessão expira                               | Falha na comunicação (ausência de notificação) |
| Caso 8             | 1, 3, 5, 7, 11, 13, 16      | COREN válido, senha forte, dados completos, verificação OK, login bloqueado corretamente, e-mail enviado, sessão nunca expira                        | Sessão insegura (não expira automaticamente)   |

<br>

---

### H20 - Como enfermeiro, quero registrar a aplicação de vacinas diretamente no aplicativo, para que eu possa atualizar o histórico do paciente.
<br>

### <p align="center">Tabela de Equivalência
| **CONDIÇÃO DE ENTRADA**                                       | **CLASSES VÁLIDAS**                                                              | **CLASSES INVÁLIDAS**                     |
| ------------------------------------------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------- |
| Busca de paciente por CPF ou número do SUS                    | CPF com 11 dígitos e CNS com 15 dígitos válidos (1)                              | CPF e CNS inválidos (2)                   |
| Vacinas disponíveis na lista estática oficial do SUS/ANVISA   | Lista correta com vacinas do calendário atualizado (3)                           | Lista desatualizada (4)                   |
| Sistema aceita registrar até 50 vacinas por sessão            | Registros aceitos até o limite de 50 por sessão (5)                              | Excede o limite sem nova autenticação (6) |
| Sistema permite registros tanto online quanto offline         | Registro salvo localmente e sincronizado quando online (7)                       | Falha na sincronização (8)                |
| Enfermeiro possui COREN ativo e está vinculado a uma UBS      | COREN validado e vínculo confirmado (9)                                          | COREN inativo (10)                        |
| Registro de lote de vacina completo com os dados obrigatórios | Lote registrado com nº do lote, validade, fabricante, CPF, COREN, data/hora (11) | Registro incompleto (12)                  |
| Backups criptografados garantem rastreabilidade               | Registros armazenados com criptografia e retenção por 10 anos (13)               | Falha no backup (14)                      |

<br>

### <p align="center">Tabela de Casos de Teste
| **CASOS DE TESTE** | **CLASSES DE EQUIVALÊNCIA** | **ENTRADAS**                                                                                                                                                     | **RESULTADOS ESPERADOS**                     |
| ------------------ | --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| Caso 1             | 1, 3, 5, 7, 9, 11, 13       | CPF e CNS válidos, lista oficial do SUS, até 50 vacinas registradas, registro offline sincronizado, COREN ativo e vinculado, lote completo, backup criptografado | Registro concluído com sucesso e seguro      |
| Caso 2             | 2, 3, 5, 7, 9, 11, 13       | CPF/CNS inválidos, lista oficial, até 50 vacinas, sincronização OK, COREN válido, lote completo, backup ok                                                       | Busca inválida (CPF/CNS incorretos)          |
| Caso 3             | 1, 4, 5, 7, 9, 11, 13       | CPF/CNS válidos, lista desatualizada, até 50 vacinas, sincronização OK, COREN válido, lote completo, backup ok                                                   | Lista de vacinas incorreta                   |
| Caso 4             | 1, 3, 6, 7, 9, 11, 13       | CPF/CNS válidos, lista oficial, mais de 50 vacinas sem nova autenticação, sincronização OK, COREN válido, lote completo, backup ok                               | Erro: excedeu limite de registros            |
| Caso 5             | 1, 3, 5, 8, 9, 11, 13       | CPF/CNS válidos, lista oficial, até 50 vacinas, falha na sincronização offline, COREN válido, lote completo, backup ok                                           | Registros não sincronizados corretamente     |
| Caso 6             | 1, 3, 5, 7, 10, 11, 13      | CPF/CNS válidos, lista oficial, até 50 vacinas, sincronização ok, COREN inativo, lote completo, backup ok                                                        | Acesso negado ao enfermeiro (COREN inválido) |
| Caso 7             | 1, 3, 5, 7, 9, 12, 13       | CPF/CNS válidos, lista oficial, até 50 vacinas, sincronização ok, COREN válido, lote incompleto, backup ok                                                       | Registro de vacina incompleto                |
| Caso 8             | 1, 3, 5, 7, 9, 11, 14       | CPF/CNS válidos, lista oficial, até 50 vacinas, sincronização ok, COREN válido, lote completo, backup com falha                                                  | Falha na rastreabilidade dos registros       |

<br>

---


### H21 - Como enfermeiro, quero acessar um mapa com unidades de saúde, para que eu possa orientar pacientes sobre locais disponíveis para vacinação.
<br>

### <p align="center">Tabela de Equivalência
| **CONDIÇÃO DE ENTRADA**                                                       | **CLASSES VÁLIDAS**                                                           | **CLASSES INVÁLIDAS**                               |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | --------------------------------------------------- |
| Indicador de lotação exibido corretamente por cor                             | Verde (≤50%), Amarelo (51–80%), Vermelho (>80%), atualizado a cada 15 min (1) | Cores erradas (2)                                   |
| Mapa mostra unidades num raio inicial de 500m e expande automaticamente       | Raio de busca aumenta para 1km, 3km e 5km caso não haja unidades (3)          | Raio não expande (4)                                |
| Raio ajustável manualmente pelo usuário                                       | Interface permite alterar manualmente a distância de busca (5)                | Usuário não consegue ajustar o raio (6)             |
| Endereços das unidades validados automaticamente                              | Endereço com CEP, número e cidade validados e marcados como verificados (7)   | Endereços inválidos (8)                             |
| Sistema marca como “não verificado” em caso de falha de validação de endereço | Sistema identifica corretamente falhas e marca visualmente (9)                | Endereços incorretos são exibidos como válidos (10) |

<br>

### <p align="center">Tabela de Casos de Teste
| **CASOS DE TESTE** | **CLASSES DE EQUIVALÊNCIA** | **ENTRADAS**                                                                                                                                                                  | **RESULTADOS ESPERADOS**                      |
| ------------------ | --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------- |
| Caso 1             | 1, 3, 5, 7, 9               | Indicador de lotação com cores corretas, raio expandido automaticamente, raio ajustável pelo usuário, endereços válidos e verificados, falhas marcadas como "não verificadas" | Comportamento ideal do sistema                |
| Caso 2             | 2, 3, 5, 7, 9               | Cores de lotação erradas (ex: vermelho com 40%), raio expandido corretamente, ajuste manual disponível, endereços válidos, falhas marcadas                                    | Exibição incorreta das cores de lotação       |
| Caso 3             | 1, 4, 5, 7, 9               | Cores corretas, raio não expande automaticamente, ajuste manual ok, endereços válidos, falhas marcadas                                                                        | Falha na lógica de expansão automática        |
| Caso 4             | 1, 3, 6, 7, 9               | Cores corretas, raio expande corretamente, raio não ajustável manualmente, endereços válidos, falhas marcadas                                                                 | Interface não permite ajuste de raio          |
| Caso 5             | 1, 3, 5, 8, 9               | Cores corretas, raio expande automaticamente, raio ajustável, endereços inválidos, falhas corretamente marcadas                                                               | Endereços inválidos, mas sistema reage bem    |
| Caso 6             | 1, 3, 5, 7, 10              | Cores corretas, raio expande, ajuste manual OK, endereços válidos, falhas **não** marcadas visualmente                                                                        | Endereços incorretos são considerados válidos |

<br>

---


### H22 - Como enfermeiro, eu quero cadastrar os detalhes de campanhas de vacinação no aplicativo, para informar a todos os pacientes.
<br>

### <p align="center">Tabela de Equivalência
| **CONDIÇÃO DE ENTRADA**                                        | **CLASSES VÁLIDAS**                                                               | **CLASSES INVÁLIDAS**                      |
| -------------------------------------------------------------- | --------------------------------------------------------------------------------- | ------------------------------------------ |
| Campanha submetida por enfermeiro com COREN                    | Enfermeiro-chefe com COREN ativo aprova a campanha (1)                            | Campanha enviada por usuário sem COREN (2) |
| Aprovação da campanha ocorre em até 2 horas                    | Campanha validada dentro do prazo e publicada (3)                                 | Aprovação não ocorre em 2 horas (4)        |
| Campanha reprovada pode ser reenviada após revisão             | Sistema permite correção e reenvio para nova tentativa de aprovação (5)           | Sistema bloqueia reenvio (6)               |
| Notificações são enviadas a todos os perfis com formato padrão | Push enviado com mensagem no formato: ‘Campanha \[x] em \[Posto] até \[Data]’ (7) | Notificação não enviada (8)                |

<br>

### <p align="center">Tabela de Casos de Teste
| **CASOS DE TESTE** | **CLASSES DE EQUIVALÊNCIA** | **ENTRADAS**                                                                                                                          | **RESULTADOS ESPERADOS**                           |
| ------------------ | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------- |
| Caso 1             | 1, 3, 5, 7                  | Campanha submetida por enfermeiro com COREN, aprovada em até 2h, reprovada anteriormente e reenviada com sucesso, notificação enviada | Fluxo completo e esperado                          |
| Caso 2             | 2, 3, 5, 7                  | Campanha enviada por usuário sem COREN, aprovada em até 2h, reenvio habilitado, notificação enviada                                   | Erro de submissão (sem COREN)                      |
| Caso 3             | 1, 4, 5, 7                  | Enfermeiro com COREN envia campanha, aprovação demorada (após 2h), reenvio permitido, notificação enviada                             | Atraso no fluxo de publicação                      |
| Caso 4             | 1, 3, 6, 7                  | Enfermeiro com COREN envia, aprovada em até 2h, reprovação sem permitir reenvio, notificação enviada                                  | Falha de usabilidade (sistema não permite reenvio) |
| Caso 5             | 1, 3, 5, 8                  | Enfermeiro com COREN envia campanha, aprovada em até 2h, reenvio possível, notificação não enviada                                    | Comunicação falhou (push ausente)                  |

<br>

---


### H23 - Como enfermeiro, eu gostaria de registrar as vacinas que foram aplicadas no paciente para que atualize a carteira de vacina do paciente.
<br>

### <p align="center">Tabela de Equivalência
| **CONDIÇÃO DE ENTRADA**                                                    | **CLASSES VÁLIDAS**                                                                    | **CLASSES INVÁLIDAS**                                                      |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Registro segue intervalo mínimo do PNI ou é reforço autorizado             | Sistema aceita vacina dentro do prazo e com dose de reforço válida (1)                 | Sistema bloqueia registro duplicado fora do prazo sem justificativa (2)    |
| Vacinas/doses pendentes geram alertas automáticos                          | Notificações visuais e push informam vacina, dose e prazo conforme PNI (3)             | Nenhum alerta é exibido (4)                                                |
| Paciente visualiza histórico atualizado em até 1 minuto após o registro    | Atualização dentro do tempo limite (5)                                                 | Histórico não atualizado (6)                                               |
| Histórico pode ser exportado em PDF conforme modelo do Ministério da Saúde | PDF gerado com QR Code e dados oficiais disponíveis ao paciente e profissionais (7)    | PDF ausente (8)                                                            |
| Vacina reaplicada fora do prazo com justificativa médica                   | Cadastro autorizado com CRM, token, justificativa e prontuário (9)                     | Reaplicação fora do intervalo sem justificativa e documentação médica (10) |
| Registro feito offline é sincronizado e verificado na reconexão            | Sincronização verifica duplicidade (CPF + lote + data + tipo) e permite resolução (11) | Sincronização falha (12)                                                   |

<br>

### <p align="center">Tabela de Casos de Teste
| **CASOS DE TESTE** | **CLASSES DE EQUIVALÊNCIA** | **ENTRADAS**                                                                                                                                                                                                     | **RESULTADOS ESPERADOS**                               |
| ------------------ | --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| Caso 1             | 1, 3, 5, 7, 9, 11           | Vacina registrada dentro do intervalo mínimo, alerta exibido corretamente, histórico atualizado em até 1 minuto, PDF gerado com QR Code, reaplicação com justificativa médica, sincronização resolve duplicidade | Registro válido e completo                             |
| Caso 2             | 2, 3, 5, 7, 9, 11           | Registro duplicado fora do prazo e sem justificativa, alerta gerado, histórico atualizado, PDF gerado, reaplicação com justificativa médica, sincronização resolve duplicidade                                   | Registro bloqueado por duplicidade fora do prazo       |
| Caso 3             | 1, 4, 5, 7, 9, 11           | Registro válido, nenhum alerta é exibido, histórico atualizado, PDF gerado, reaplicação com justificativa, sincronização ok                                                                                      | Falha na geração de alerta automático                  |
| Caso 4             | 1, 3, 6, 7, 9, 11           | Registro válido, alerta ok, histórico não é atualizado, PDF gerado, reaplicação com justificativa, sincronização ok                                                                                              | Histórico do paciente inconsistente                    |
| Caso 5             | 1, 3, 5, 8, 9, 11           | Registro válido, alerta ok, histórico atualizado, PDF não é gerado, reaplicação com justificativa, sincronização ok                                                                                              | Falha na exportação do histórico em PDF                |
| Caso 6             | 1, 3, 5, 7, 10, 11          | Registro válido, alerta ok, histórico atualizado, PDF gerado, reaplicação sem justificativa médica, sincronização ok                                                                                             | Registro rejeitado por falta de justificativa médica   |
| Caso 7             | 1, 3, 5, 7, 9, 12           | Registro válido, alerta ok, histórico atualizado, PDF gerado, reaplicação justificada, sincronização falha                                                                                                       | Risco de dados não integrados (falha de sincronização) |

<br>
