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
|CONDIÇÃO DE ENTRADA|CLASSES VÁLIDAS| CLASSES INVÁLIDAS**  |
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
| CASOS DE TESTE| CLASSES DE EQUIVALÊNCIA | ENTRADAS                                                                                                                                        | RESULTADOS ESPERADOS                      |
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

### H20 - Como enfermeiro, quero registrar a aplicação de vacinas diretamente no aplicativo, para atualizar o histórico do paciente imediatamente quando online ou quando a conexão for restabelecida se estiver offline.
<br>

### <p align="center">Tabela de Equivalência
<br>

### <p align="center">Tabela de Casos de Teste
<br>

---

### H21 - Como enfermeiro, quero acessar um mapa com unidades de saúde, para que eu possa orientar pacientes sobre locais disponíveis para vacinação.
<br>

### <p align="center">Tabela de Equivalência
| CONDIÇÃO DE ENTRADA                                                     | CLASSES VÁLIDAS                                                           | CLASSES INVÁLIDAS                              |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | --------------------------------------------------- |
| Indicador de lotação exibido corretamente por cor                             | Verde (≤50%), Amarelo (51–80%), Vermelho (>80%), atualizado a cada 15 min (1) | Cores erradas (2)                                   |
| Mapa mostra unidades num raio inicial de 500m e expande automaticamente       | Raio de busca aumenta para 1km, 3km e 5km caso não haja unidades (3)          | Raio não expande (4)                                |
| Raio ajustável manualmente pelo usuário                                       | Interface permite alterar manualmente a distância de busca (5)                | Usuário não consegue ajustar o raio (6)             |
| Endereços das unidades validados automaticamente                              | Endereço com CEP, número e cidade validados e marcados como verificados (7)   | Endereços inválidos (8)                             |
| Sistema marca como “não verificado” em caso de falha de validação de endereço | Sistema identifica corretamente falhas e marca visualmente (9)                | Endereços incorretos são exibidos como válidos (10) |

<br>

### <p align="center">Tabela de Casos de Teste
| CASOS DE TESTE| CLASSES DE EQUIVALÊNCIA | ENTRADAS                                                                                                                                                                  | RESULTADOS ESPERADOS                     |
| ------------------ | --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------- |
| Caso 1             | 1, 3, 5, 7, 9               | Indicador de lotação com cores corretas, raio expandido automaticamente, raio ajustável pelo usuário, endereços válidos e verificados, falhas marcadas como "não verificadas" | Comportamento ideal do sistema                |
| Caso 2             | 2, 3, 5, 7, 9               | Cores de lotação erradas (ex: vermelho com 40%), raio expandido corretamente, ajuste manual disponível, endereços válidos, falhas marcadas                                    | Exibição incorreta das cores de lotação       |
| Caso 3             | 1, 4, 5, 7, 9               | Cores corretas, raio não expande automaticamente, ajuste manual ok, endereços válidos, falhas marcadas                                                                        | Falha na lógica de expansão automática        |
| Caso 4             | 1, 3, 6, 7, 9               | Cores corretas, raio expande corretamente, raio não ajustável manualmente, endereços válidos, falhas marcadas                                                                 | Interface não permite ajuste de raio          |
| Caso 5             | 1, 3, 5, 8, 9               | Cores corretas, raio expande automaticamente, raio ajustável, endereços inválidos, falhas corretamente marcadas                                                               | Endereços inválidos, mas sistema reage bem    |
| Caso 6             | 1, 3, 5, 7, 10              | Cores corretas, raio expande, ajuste manual OK, endereços válidos, falhas **não** marcadas visualmente                                                                        | Endereços incorretos são considerados válidos |

<br>

---


### H22 - Como enfermeiro, quero cadastrar campanhas de vacinação no aplicativo, para que os pacientes sejam informados com precisão e rapidez sobre oportunidades de vacinação em sua região.
<br>

### <p align="center">Tabela de Equivalência
| CONDIÇÃO DE ENTRADA                              | CLASSES VÁLIDAS                          | CLASSES INVÁLIDAS                   |
| ---------------------------------------------------- | -------------------------------------------- | ---------------------------------------- |
| Validação feita por enfermeiro-chefe com COREN ativo | Enfermeiro-chefe com COREN ativo aprovou (1) | Enfermeiro-chefe sem COREN ativo (2)     |
| Aprovação dentro do prazo de 2 horas                 | Campanha aprovada em até 2 horas (3)         | Campanha não aprovada em até 2 horas (4) |
| Reenvio da campanha após reprovação                  | Campanha reenviada para aprovação (5)        | Campanha não reenviada (6)               |
| Notificação enviada no formato padrão                | Notificação no formato correto via push (7)  | Notificação no formato incorreto (8)     |
<br>

### <p align="center">Tabela de Casos de Teste
| CASOS DE TESTE| CLASSES DE EQUIVALÊNCIA | ENTRADAS                                                                                     | RESULTADOS ESPERADOS                            |
| ------------------ | --------------------------- | ------------------------------------------------------------------------------------------------ | --------------------------------------------------- |
| Caso 1             | 1, 3, 5, 7                  | Enfermeiro-chefe com COREN ativo aprova campanha dentro do prazo; notificação no formato correto | Campanha aprovada, publicada e notificação enviada  |
| Caso 2             | 2, 4, 8                     | Enfermeiro-chefe sem COREN ativo; campanha não aprovada em até 2 horas; notificação ausente      | Campanha reprovada automaticamente, sem notificação |
| Caso 3             | 2, 4, 6                     | Campanha não aprovada em 2h, reprovada; enfermeiro responsável reenvia campanha para aprovação   | Campanha reenviada para nova aprovação              |
| Caso 4             | 1, 3, 5, 8                  | Campanha aprovada; notificação com formato incorreto ou não enviada                              | Campanha publicada; falha na notificação            |

<br>

---


### H23 - Como enfermeiro, quero registrar no aplicativo todos os dados da aplicação de vacinas, para que o histórico vacinal seja atualizado com informações completas e rastreáveis conforme exigências do PNI.
<br>

### <p align="center">Tabela de Equivalência
| CONDIÇÃO DE ENTRADA                                         | CLASSES VÁLIDAS                                   | CLASSES INVÁLIDAS                                     |
| --------------------------------------------------------------- | ----------------------------------------------------- | --------------------------------------------------------- |
| Registro duplicado bloqueado conforme intervalo PNI             | Registro bloqueado se duplicado fora das exceções (1) | Registro duplicado permitido indevidamente (2)            |
| Doses de reforço autorizadas permitidas                         | Registro permitido para doses de reforço (3)          | Registro bloqueado indevidamente para dose de reforço (4) |
| Alertas automáticos exibidos para vacinas pendentes             | Alertas visuais e push exibidos corretamente (5)      | Alertas ausentes de push (6)                              |
| Histórico atualizado no app em até 1 minuto                     | Atualização visível em até 1 minuto (7)               | Atualização demora mais que 1 minuto e não atualiza (8)   |
| Histórico exportável em PDF com modelo MS e QR Code             | PDF gerado conforme padrão MS com QR Code (9)         | PDF gerado em formato incorreto e sem QR Code (10)        |
| Acesso ao histórico é disponível para pacientes e profissionais | Acesso permitido conforme perfil (11)                 | Acesso negado indevidamente (12)                          |

<br>

### <p align="center">Tabela de Casos de Teste
| CASOS DE TESTE| CLASSES DE EQUIVALÊNCIA| ENTRADAS                                                                                                                   | RESULTADOS ESPERADOS                                                                |
| ------------------ | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Caso 1             | 1, 3, 5, 7, 9, 11           | Registro de vacina completo, dose não duplicada, alerta exibido, atualização do histórico rápida, acesso ao histórico permitido | Registro salvo, alerta mostrado, histórico atualizado e disponível em PDF com QR Code    |
| Caso 2             | 2, 3, 5, 7, 9, 11           | Registro duplicado indevido, alerta exibido, histórico atualizado, PDF gerado corretamente                                      | Registro bloqueado, alerta mostrado, histórico atualizado e PDF disponível               |
| Caso 3             | 1, 4, 6, 7, 9, 11           | Registro de dose de reforço autorizado, alerta exibido, histórico atualizado, PDF gerado                                        | Registro permitido, alerta mostrado, histórico atualizado e PDF disponível               |
| Caso 4             | 1, 3, 5, 8, 9, 11           | Registro de vacina sem alerta exibido, atualização do histórico demora mais de 1 minuto                                         | Registro salvo, alerta não exibido, atraso na atualização do histórico                   |
| Caso 5             | 1, 3, 5, 7, 10, 12          | Registro completo, alerta exibido, histórico atualizado, PDF gerado com formato incorreto ou acesso negado                      | Registro salvo, alerta mostrado, histórico atualizado, falha na geração ou acesso ao PDF |

<br>
