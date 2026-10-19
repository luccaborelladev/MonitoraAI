# PRD — MonitoraAí

> **Product Requirements Document** · Versão 1.1 · Etapa de planejamento
> **Equipe:** Rafael, Guilherme, Lucca e Metheus · **MVP:** até 02/11/2026 · **Entrega final:** até 16/11/2026
> Repositório: `<https://github.com/luccaborelladev/MonitoraAI>` · GitHub Project: `<https://github.com/luccaborelladev/MonitoraAI/projects>`

---

## Sumário

1. [Visão do produto](#1-visão-do-produto)
2. [Escopo](#2-escopo)
3. [Requisitos](#3-requisitos)
4. [Gerência do projeto](#4-gerência-do-projeto)
5. [Funcionalidade de conversa com NoSQL](#5-funcionalidade-de-conversa-com-nosql)

---

## 1. Visão do produto

### 1.1 Nome do projeto

**MonitoraAí** — plataforma que conecta estudantes que precisam de ajuda em uma disciplina com monitores e colegas que dominam o conteúdo.

### 1.2 Problema identificado

Em cursos de graduação e ensino técnico, muitos estudantes têm dificuldade em disciplinas com alta reprovação (cálculo, programação, física etc.). A ajuda existe (monitores, veteranos, colegas), mas está **dispersa e desorganizada**:

- Os contatos de monitores ficam em grupos de WhatsApp lotados, murais físicos ou listas em PDF.
- Não há como saber **quem ajuda em qual disciplina e em quais horários**.
- As dúvidas se perdem em conversas misturadas com avisos e memes, e o histórico não pode ser consultado depois.
- Monitores não têm visibilidade de quantos alunos atendem nem de quais temas geram mais dúvidas.

### 1.3 Público-alvo

| Perfil | Descrição | Necessidade principal |
|---|---|---|
| **Estudante (aluno)** | Matriculado em curso presencial ou híbrido, com dificuldade em disciplinas específicas | Encontrar rapidamente alguém que explique um conteúdo e tirar dúvidas por conversa |
| **Monitor** | Estudante veterano, bolsista ou voluntário, que auxilia em disciplinas | Receber dúvidas organizadas e manter histórico dos atendimentos |
| **Coordenador / Professor** *(secundário, pós-MVP)* | Responsável pelo programa de monitoria | Acompanhar demanda e engajamento |

### 1.4 Objetivos

**Objetivo geral:** facilitar o contato entre estudantes e monitores por disciplina, centralizando as dúvidas e o histórico de conversas em um único lugar.

**Objetivos específicos:**

1. Permitir que o aluno encontre monitores por disciplina em menos de 1 minuto.
2. Permitir conversa direta entre aluno e monitor, com histórico persistente.
3. Permitir que grupos de estudo conversem em salas por disciplina.
4. Reduzir o tempo médio de resposta a dúvidas (meta de referência: resposta em até 24 h).

### 1.5 Benefícios esperados

- **Para o aluno:** acesso rápido a ajuda, menos dúvidas acumuladas, histórico para revisar explicações antes das provas.
- **Para o monitor:** atendimento organizado, sem misturar com conversas pessoais.
- **Para a instituição:** base para medir o uso da monitoria e identificar disciplinas críticas (pós-MVP).

### 1.6 Métricas de sucesso (referência para o MVP)

| Métrica | Meta |
|---|---|
| Mensagens enviadas com sucesso | ≥ 99% |
| Tempo de entrega de mensagem (envio → visível para o destinatário) | ≤ 2 s em 95% dos casos |
| Alunos que iniciam ao menos 1 conversa após o cadastro | ≥ 60% |
| Tempo para encontrar um monitor e abrir conversa | ≤ 1 min |

---

## 2. Escopo

### 2.1 Funcionalidades previstas (visão completa do produto)

| ID | Funcionalidade | Entrega |
|---|---|---|
| F01 | Cadastro e login de usuários | **MVP (até 02/11)** |
| F02 | Perfil de usuário (nome, curso, papel: aluno ou monitor) | **MVP (até 02/11)** |
| F03 | Cadastro de disciplinas atendidas pelo monitor | **MVP (até 02/11)** |
| F04 | Busca de monitores por disciplina | **MVP (até 02/11)** |
| F05 | Conversa direta (1:1) entre usuários | **MVP (até 02/11)** |
| F06 | Conversa em grupo por disciplina (sala de estudo) | Entrega final (até 16/11) |
| F07 | Histórico de mensagens com paginação e lista de conversas | **MVP (até 02/11)** |
| F08 | Indicador de mensagens não lidas | Entrega final (até 16/11) |
| F09 | Agendamento de monitorias com horário | Versão futura |
| F10 | Envio de arquivos e imagens no chat | Versão futura |
| F11 | Notificações por e-mail / push | Versão futura |
| F12 | Avaliação do monitor após o atendimento | Versão futura |
| F13 | Painel para coordenação com métricas | Versão futura |
| F14 | Moderação e denúncia de conteúdo | Versão futura |

### 2.2 Definição do MVP (entrega até 02/11/2026)

O MVP entrega o **fluxo essencial**: *cadastrar → achar um monitor → conversar → consultar o histórico.*

**Incluído no MVP:**

- F01 a F05 e F07: cadastro/login, perfil, disciplinas do monitor, busca de monitores, conversa direta (1:1), envio de mensagens, histórico paginado e lista de conversas ordenada pela atividade mais recente.
- Controle de acesso por participante em todas as consultas e envios.
- Aplicação web responsiva (funciona no navegador do celular e do computador).
- Mensagens em **texto simples**.
- Novas mensagens exibidas por **polling simples** (consulta periódica de poucos segundos).

### 2.3 Entrega final (até 16/11/2026)

Após o MVP, a entrega final acrescenta:

- **Salas de estudo por disciplina** (F06).
- **Indicador de mensagens não lidas** (F08).
- **Atualização em tempo real** com WebSocket, substituindo o polling.
- Edição de perfil, testes completos dos critérios de aceitação e documentação final.

### 2.4 Fora do escopo do MVP e da entrega final

- Agendamento de monitorias (F09).
- Envio de arquivos, imagens, áudio ou vídeo (F10).
- Notificações push e por e-mail (F11).
- Avaliação de monitores (F12).
- Painel de coordenação e relatórios (F13).
- Denúncia e moderação avançada (F14).
- Aplicativo móvel nativo.
- Integração com sistemas acadêmicos da instituição (SSO, matrícula).
- Chamadas de voz ou vídeo.
- Criptografia de ponta a ponta.

---

## 3. Requisitos

### 3.1 Requisitos funcionais

| ID | Requisito | Prioridade | Entrega |
|---|---|---|---|
| RF01 | O sistema deve permitir cadastro com nome, e-mail e senha. | Alta | MVP |
| RF02 | O sistema deve permitir login e logout. | Alta | MVP |
| RF03 | O usuário deve poder escolher o papel **aluno** ou **monitor** no cadastro. | Alta | MVP |
| RF04 | O monitor deve poder cadastrar as disciplinas em que atende. | Alta | MVP |
| RF05 | O aluno deve poder buscar monitores filtrando por disciplina. | Alta | MVP |
| RF06 | O usuário deve poder iniciar conversa direta com outro usuário a partir do perfil. | Alta | MVP |
| RF07 | O sistema deve impedir a criação de conversas diretas duplicadas entre os mesmos dois usuários. | Alta | MVP |
| RF08 | O usuário deve poder enviar mensagens de texto em uma conversa da qual participa. | Alta | MVP |
| RF09 | O usuário deve poder consultar o histórico de mensagens de suas conversas, em ordem cronológica. | Alta | MVP |
| RF10 | O histórico deve ser paginado (carregar mensagens mais antigas sob demanda). | Alta | MVP |
| RF11 | O usuário deve ver a lista de suas conversas ordenada pela atividade mais recente. | Alta | MVP |
| RF12 | O sistema deve exibir a quantidade de mensagens não lidas por conversa. | Média | Final |
| RF13 | O usuário deve poder entrar em salas de estudo por disciplina e sair delas. | Média | Final |
| RF14 | Um usuário que **não** participa de uma conversa não pode ler nem enviar mensagens nela. | Alta | MVP |
| RF15 | O usuário deve poder editar seu perfil. | Baixa | Final |

### 3.2 Requisitos não funcionais

| ID | Categoria | Requisito |
|---|---|---|
| RNF01 | Desempenho | Listar as 30 últimas mensagens de uma conversa deve levar no máximo 500 ms (p95) com 100 mil mensagens armazenadas. |
| RNF02 | Desempenho | O envio de uma mensagem deve ser confirmado ao remetente em até 1 s (p95). |
| RNF03 | Segurança | Senhas armazenadas com hash seguro (bcrypt ou argon2); nunca em texto puro. |
| RNF04 | Segurança | Toda requisição ao chat exige autenticação (token JWT ou sessão). |
| RNF05 | Segurança | Comunicação via HTTPS em produção. |
| RNF06 | Privacidade | Dados pessoais limitados ao necessário (nome, e-mail, curso), em conformidade com a LGPD. |
| RNF07 | Disponibilidade | Meta de 99% de disponibilidade durante o período de avaliação. |
| RNF08 | Usabilidade | Interface responsiva, utilizável em telas a partir de 360 px de largura. |
| RNF09 | Manutenibilidade | Código versionado no GitHub, com revisão por *pull request* e README com instruções de execução. |
| RNF10 | Escalabilidade | O modelo de dados do chat deve permitir crescimento do volume de mensagens sem degradar a consulta do histórico (uso de índices e paginação). |
| RNF11 | Portabilidade | O sistema deve rodar localmente via Docker Compose. |

### 3.3 Histórias de usuário e critérios de aceitação

> Formato dos critérios: **Dado** (contexto) **Quando** (ação) **Então** (resultado verificável).

#### HU01 — Cadastro e login

**Como** estudante, **quero** criar uma conta e entrar na plataforma, **para** acessar os monitores e conversas.

**Critérios de aceitação**

- **CA01.1** — Dado um e-mail ainda não cadastrado, quando preencho nome, e-mail e senha válidos, então a conta é criada e sou redirecionado para a tela inicial.
- **CA01.2** — Dado um e-mail já cadastrado, quando tento me cadastrar com ele, então vejo a mensagem "E-mail já cadastrado" e nenhuma conta nova é criada.
- **CA01.3** — Dado que tenho conta, quando informo e-mail e senha corretos, então sou autenticado e recebo acesso às minhas conversas.
- **CA01.4** — Dado que informo senha incorreta, quando tento entrar, então o acesso é negado com mensagem genérica de erro.

#### HU02 — Monitor cadastra disciplinas

**Como** monitor, **quero** informar as disciplinas em que atendo, **para** que alunos me encontrem.

- **CA02.1** — Dado que sou monitor autenticado, quando adiciono a disciplina "Cálculo I", então ela aparece no meu perfil.
- **CA02.2** — Dado que adicionei uma disciplina, quando um aluno busca por ela, então meu perfil aparece nos resultados.
- **CA02.3** — Dado que removo uma disciplina, quando um aluno busca por ela, então meu perfil não aparece mais.

#### HU03 — Aluno busca monitor

**Como** aluno, **quero** buscar monitores por disciplina, **para** pedir ajuda a quem domina o conteúdo.

- **CA03.1** — Dado que existem monitores de "Programação I", quando busco por essa disciplina, então vejo a lista com nome e disciplinas de cada um.
- **CA03.2** — Dado que não há monitores para a disciplina buscada, quando faço a busca, então vejo a mensagem "Nenhum monitor encontrado".

#### HU04 — Iniciar conversa direta

**Como** aluno, **quero** iniciar uma conversa com um monitor, **para** tirar minha dúvida.

- **CA04.1** — Dado que estou no perfil de um monitor, quando clico em "Conversar", então uma conversa direta é aberta entre nós dois.
- **CA04.2** — Dado que já existe conversa direta entre mim e esse monitor, quando clico em "Conversar", então a conversa existente é aberta (nenhuma duplicada é criada).
- **CA04.3** — Dado que tento iniciar conversa comigo mesmo, quando clico em "Conversar", então a ação é recusada.

#### HU05 — Enviar mensagem

**Como** participante de uma conversa, **quero** enviar mensagens de texto, **para** me comunicar com a outra pessoa ou o grupo.

- **CA05.1** — Dado que participo da conversa, quando envio uma mensagem com texto, então ela é salva no banco com remetente, conversa e data/hora do servidor.
- **CA05.2** — Dado que envio uma mensagem, quando o envio é concluído, então ela aparece no final da conversa para mim e para os demais participantes em até 2 s.
- **CA05.3** — Dado que tento enviar mensagem vazia ou só com espaços, quando clico em enviar, então nada é salvo e vejo aviso de validação.
- **CA05.4** — Dado que a mensagem excede 2.000 caracteres, quando tento enviar, então ela é recusada com aviso.
- **CA05.5** — Dado que não participo da conversa, quando tento enviar mensagem a ela (ex.: via API), então recebo resposta **403 Forbidden** e nada é salvo.

#### HU06 — Consultar histórico

**Como** participante, **quero** ver o histórico de mensagens, **para** rever explicações anteriores.

- **CA06.1** — Dado que abro uma conversa, quando ela carrega, então vejo as 30 mensagens mais recentes, da mais antiga para a mais recente (de cima para baixo).
- **CA06.2** — Dado que existem mais de 30 mensagens, quando rolo até o topo ou clico em "Carregar anteriores", então as 30 mensagens imediatamente anteriores são carregadas, sem repetição nem lacunas.
- **CA06.3** — Dado que duas mensagens têm o mesmo horário, quando o histórico é exibido, então a ordem entre elas é determinística (desempate por número de sequência).
- **CA06.4** — Dado que não participo da conversa, quando tento consultar o histórico, então recebo **403 Forbidden**.
- **CA06.5** — Dado que recarrego a página, quando abro a mesma conversa, então todas as mensagens enviadas anteriormente continuam disponíveis (persistência).

#### HU07 — Lista de conversas e não lidas

> CA07.1 faz parte do **MVP**; CA07.2 e CA07.3 (não lidas) fazem parte da **entrega final**.

**Como** usuário, **quero** ver minhas conversas ordenadas pela atividade mais recente com a contagem de não lidas, **para** saber o que responder primeiro.

- **CA07.1** — Dado que tenho várias conversas, quando abro a lista, então a conversa com a mensagem mais recente aparece no topo.
- **CA07.2** — Dado que recebi 3 mensagens novas em uma conversa que não abri, quando vejo a lista, então ela mostra o indicador "3".
- **CA07.3** — Dado que abro a conversa, quando as mensagens são exibidas, então o contador de não lidas dessa conversa volta a zero.

#### HU08 — Sala de estudo por disciplina *(entrega final)*

**Como** aluno, **quero** entrar em uma sala de conversa da minha disciplina, **para** discutir dúvidas com colegas e monitores.

- **CA08.1** — Dado que existe a sala "Cálculo I", quando clico em "Entrar", então passo a ser participante e vejo o histórico a partir da minha entrada.
- **CA08.2** — Dado que sou participante, quando envio uma mensagem, então todos os participantes da sala a veem.
- **CA08.3** — Dado que clico em "Sair da sala", quando confirmo, então deixo de receber mensagens e perco acesso ao histórico da sala.

---

## 4. Gerência do projeto

### 4.1 Integrantes e responsabilidades

> Substituir os usuários do GitHub pelos reais.

| Integrante | Papel | Responsabilidades principais |
|---|---|---|---|
| **Rafael** | **Product Owner / Documentação / QA** | Manter o PRD, o README e o backlog; organizar o GitHub Project; perfil do monitor e busca; testes dos critérios de aceitação |
| **Guilherme** | **Líder técnico / Back-end / DevOps** | Arquitetura, Docker Compose, API de conversas (criação, envio, controle de acesso), WebSocket, salas de estudo |
| **Lucca** | **Back-end / Banco de dados** | Modelagem do MongoDB, índices, dados de exemplo, autenticação, histórico paginado, mensagens não lidas |
| **Metheus** | **Front-end** | Telas de cadastro/login, busca, lista de conversas, chat e salas; integração com a API |

> Todos revisam *pull requests* uns dos outros. Cada issue tem **um** responsável principal.

### 4.2 Backlog priorizado

Prioridade: **P0** = essencial para o MVP · **P1** = importante · **P2** = desejável.
Entrega: **MVP** = até 02/11/2026 · **Final** = até 16/11/2026.
Cada linha deve virar uma **issue** no GitHub.

| # | Item (título da issue) | Tipo | Prioridade | Responsável | Entrega |
|---|---|---|---|---|---|---|
| 1 | Escrever e publicar o PRD em `docs/PRD.md` | Documentação | P0 | Rafael | MVP |
| 2 | Criar repositório, README e GitHub Project | Organização | P0 | Rafael | MVP |
| 3 | Cadastrar issues, status e responsáveis no Project | Organização | P0 | Rafael | MVP |
| 4 | Definir arquitetura e stack tecnológica | Técnico | P0 | Guilherme | MVP |
| 5 | Modelar coleções do MongoDB (users, conversations, messages) | Banco | P0 | Lucca | MVP |
| 6 | Criar índices e script de dados de exemplo | Banco | P0 | Lucca | MVP |
| 7 | Configurar Docker Compose (API + MongoDB) | DevOps | P0 | Guilherme | MVP |
| 8 | Implementar cadastro e login (RF01–RF03) | Feature | P0 | Lucca | MVP |
| 9 | Implementar perfil e disciplinas do monitor (RF04) | Feature | P0 | Rafael | MVP |
| 10 | Implementar busca de monitores por disciplina (RF05) | Feature | P0 | Rafael | MVP |
| 11 | Implementar criação de conversa direta sem duplicidade (RF06–RF07) | Feature | P0 | Guilherme | MVP |
| 12 | Implementar envio de mensagens com validação (RF08) | Feature | P0 | Guilherme | MVP |
| 13 | Implementar consulta paginada do histórico (RF09–RF10) | Feature | P0 | Lucca | MVP |
| 14 | Implementar controle de acesso por participante (RF14) | Feature | P0 | Guilherme | MVP |
| 15 | Tela de cadastro e login | Front-end | P0 | Metheus | MVP |
| 16 | Tela de busca de monitores | Front-end | P0 | Metheus | MVP |
| 17 | Tela de chat (envio, histórico, rolagem, polling) | Front-end | P0 | Metheus | MVP |
| 18 | Lista de conversas ordenada por atividade (RF11) | Feature | P0 | Metheus | MVP |
| 19 | Contador de mensagens não lidas (RF12) | Feature | P1 | Lucca | Final |
| 20 | Salas de estudo por disciplina (RF13) | Feature | P1 | Guilherme | Final |
| 21 | Atualização em tempo real com WebSocket | Técnico | P1 | Guilherme | Final |
| 22 | Testes dos critérios de aceitação (HU01–HU08) | Qualidade | P1 | Rafael | Final |
| 23 | Edição de perfil (RF15) | Feature | P2 | Metheus | Final |
| 24 | Documentar API e instruções de execução no README | Documentação | P2 | Rafael | Final |
| 25 | Telas de salas de estudo e indicador de não lidas | Front-end | P1 | Metheus | Final |


### 4.3 Etapas e prazos

| Etapa | Período | Entregas | Marco |
|---|---|---|---|
| **1. Planejamento** | 19/10 – 22/10/2026 | PRD publicado, repositório e GitHub Project com issues | Entrega do planejamento |
| **2. Fundação técnica** | 23/10 – 26/10/2026 | Stack definida, Docker Compose, coleções e índices, autenticação | Ambiente rodando para todos |
| **3. Núcleo do chat (MVP)** | 27/10 – 02/11/2026 | Perfil, busca de monitores, conversa direta, envio, histórico paginado, controle de acesso, lista de conversas | **MVP entregue até 02/11/2026** |
| **4. Complementos** | 03/11 – 09/11/2026 | Salas de estudo, mensagens não lidas, WebSocket, edição de perfil | Funcionalidades finais prontas |
| **5. Testes e documentação** | 10/11 – 14/11/2026 | Testes dos critérios de aceitação, correções, README e documentação da API | Versão estável |
| **6. Entrega final** | 15/11 – 16/11/2026 | Revisão dos links, do PRD e do Project | **Entrega final até 16/11/2026** |

### 4.4 Dependências

| Dependência | Impacto | Tratamento |
|---|---|---|
| Modelagem do MongoDB (#5) precisa estar pronta antes das features de chat (#11–#14) | Alto | Concluir #5 e #6 na etapa 2 (até 26/10) |
| Autenticação (#8) é pré-requisito para todo o controle de acesso | Alto | Priorizar logo após Docker Compose |
| Telas de chat (#17) dependem dos endpoints de envio e histórico (#12, #13) | Médio | Front-end usa dados simulados (*mock*) até a API ficar pronta |
| Lista de conversas (#18) e não lidas (#19) dependem da estrutura de conversas (#11) | Médio | Lista de conversas (#18) no MVP; não lidas (#19) na etapa 4 |
| Disponibilidade de ferramentas externas (GitHub, Docker, MongoDB local ou Atlas) | Baixo | Alternativa: MongoDB local via Docker |

### 4.5 Riscos e estratégias de mitigação

| # | Risco | Probabilidade | Impacto | Estratégia |
|---|---|---|---|---|
| R1 | Prazo curto: MVP em 2 semanas (até 02/11) com 4 integrantes | Alta | Alto | MVP reduzido ao fluxo essencial; salas, não lidas e WebSocket ficam para a entrega final; itens P2 só entram se sobrar tempo |
| R2 | Pouca experiência do grupo com MongoDB | Média | Médio | Estudo guiado na etapa 2; modelagem revisada em conjunto |
| R3 | Integrante ausente ou com pouca disponibilidade (equipe de 4 pessoas) | Média | Alto | Revisão cruzada de PRs; conhecimento compartilhado; redistribuir issues na reunião |
| R4 | Dificuldade com tempo real (WebSocket) | Média | Médio | O MVP já usa *polling* a cada poucos segundos (atende ao critério de 2 s); se o WebSocket não ficar pronto até 09/11, o *polling* permanece na entrega final |
| R5 | Conflitos de merge | Alta | Baixo | Branches curtas por issue, PRs pequenos, `main` protegida |
| R6 | Degradação de desempenho com muitas mensagens | Baixa | Médio | Índices desde o início; paginação por cursor; teste com dados de exemplo em volume |
| R7 | Vazamento de conversas por falha de autorização | Baixa | Alto | Verificação de participação em **toda** consulta/escrita; testes dedicados (CA05.5, CA06.4) |
| R8 | Dados pessoais de estudantes (LGPD) | Baixa | Médio | Coletar apenas o necessário; usar dados fictícios em testes e demonstração |

### 4.6 Acompanhamento do andamento

- **GitHub Project público** com colunas **A fazer → Em andamento → Concluído**, vinculado ao repositório.
- **Campos do Project:** responsável, prioridade (P0/P1/P2), estimativa, etapa (milestone).
- **Issues** com critérios de aceitação no corpo e rótulos (`feature`, `banco`, `front-end`, `documentação`, `bug`).
- **Reunião** de 30 min **duas vezes por semana** (prazo curto): o que foi concluído, o que está bloqueado, replanejamento.
- **Daily assíncrona** (mensagem curta no grupo): ontem, hoje, bloqueios.
- **Regra de fluxo:** ninguém tem mais de 2 issues em "Em andamento" ao mesmo tempo.
- **Definição de pronto:** código revisado em PR, critérios de aceitação verificados, issue movida para "Concluído".
- **Acompanhamento de progresso:** pontos concluídos vs. planejados por etapa, comparados a cada reunião.

---

## 5. Funcionalidade de conversa com NoSQL

### 5.1 Quem pode conversar

| Tipo de conversa | Participantes | Quem pode iniciar |
|---|---|---|
| **Direta (1:1)** | Exatamente 2 usuários cadastrados | Qualquer usuário autenticado, a partir do perfil de outro |
| **Sala de estudo (grupo)** *(entrega final)* | Vários usuários, vinculada a uma disciplina | Salas são criadas pela equipe/seed; qualquer usuário autenticado pode entrar |

Combinações permitidas: aluno ↔ monitor, aluno ↔ aluno, monitor ↔ monitor.

### 5.2 Como as conversas são iniciadas

**Conversa direta**

1. O usuário abre o perfil de outra pessoa e clica em **Conversar**.
2. O sistema gera uma chave determinística `directKey` com os dois IDs em ordem alfabética (ex.: `u_ana#u_bruno`).
3. Se já existe conversa com essa chave, ela é reaberta; senão, uma nova é criada.
4. Um **índice único** sobre `directKey` garante que não haja duplicatas, mesmo com dois cliques simultâneos.

**Sala de estudo** *(entrega final, até 16/11)*

1. O usuário abre a lista de salas por disciplina e clica em **Entrar**.
2. Seu ID é adicionado à lista de participantes (operação idempotente).
3. Para sair, seu ID é removido; o acesso ao histórico é encerrado.

### 5.3 Como as mensagens são enviadas, consultadas e armazenadas

**Envio**

1. O cliente envia `POST /conversations/{id}/messages` com o texto.
2. A API autentica o usuário e confere se ele está em `participantIds` da conversa.
3. A API valida o texto (não vazio, até 2.000 caracteres).
4. A API insere o documento em `messages`, com `createdAt` definido **pelo servidor**.
5. A API atualiza a conversa (`lastMessage`, `lastMessageAt`, `messageCount`) para refletir a atividade mais recente.
6. A API responde `201 Created` com a mensagem salva; os outros participantes a recebem por *polling* no MVP e por WebSocket na entrega final.

**Consulta**

- `GET /conversations/{id}/messages?limit=30&before={cursor}` — retorna as mensagens mais recentes (ou as imediatamente anteriores ao cursor), com paginação.
- `GET /conversations` — lista as conversas do usuário, da atividade mais recente para a mais antiga.

**Armazenamento**

- Cada mensagem é um **documento próprio** na coleção `messages` (não embutido na conversa). Isso evita documentos que crescem sem limite (MongoDB limita documentos a 16 MB) e permite paginar e indexar por conversa.

### 5.4 Banco NoSQL escolhido e justificativa

**Escolha: MongoDB** (banco de documentos).

| Critério | Justificativa |
|---|---|
| **Modelo de dados** | Mensagens e conversas são naturalmente documentos JSON, com estrutura simples e pouco relacionamento complexo. |
| **Flexibilidade de esquema** | Versões futuras (anexos, reações, respostas a mensagens) adicionam campos sem migração de tabelas. |
| **Desempenho de leitura/escrita** | Inserções rápidas e consultas eficientes por `conversationId` + data, com índice composto. |
| **Paginação** | Suporte natural a ordenação e paginação por cursor usando índices. |
| **Escalabilidade** | Permite escalar horizontalmente (sharding por `conversationId`) se o volume crescer. |
| **Ecossistema** | Drivers maduros (Node.js, Python, Java), MongoDB Compass para inspeção, imagem oficial no Docker, camada gratuita no Atlas. |
| **Curva de aprendizado** | Sintaxe simples e ampla documentação, adequada ao prazo do grupo. |

**Alternativas consideradas**

- **Firebase Firestore:** ótimo para tempo real, mas prende o projeto a um serviço proprietário e limita a prática de modelagem e índices.
- **Cassandra:** excelente para mensagens em escala muito grande, porém com complexidade operacional desproporcional ao MVP.
- **Redis:** rápido, mas voltado a cache e estruturas em memória; não ideal como armazenamento principal e durável do histórico.

### 5.5 Organização dos dados

Três coleções: `users`, `conversations` e `messages`.

> Os dados de **perfil** ficam em `users`. Os participantes são referenciados por ID em `conversations`, e a conversa guarda um pequeno *resumo* (`lastMessage`) para a lista de conversas ser montada **sem consultar `messages`**.

#### Coleção `users`

```json
{
  "_id": "u_ana",
  "name": "Ana Souza",
  "email": "ana@exemplo.com",
  "passwordHash": "$2b$12$...",
  "role": "student",
  "course": "Ciência da Computação",
  "subjects": [],
  "createdAt": "2026-10-27T13:00:00Z"
}
```

```json
{
  "_id": "u_bruno",
  "name": "Bruno Lima",
  "email": "bruno@exemplo.com",
  "passwordHash": "$2b$12$...",
  "role": "tutor",
  "course": "Ciência da Computação",
  "subjects": ["Cálculo I", "Programação I"],
  "createdAt": "2026-10-27T13:05:00Z"
}
```

#### Coleção `conversations`

**Conversa direta**

```json
{
  "_id": "c_001",
  "type": "direct",
  "directKey": "u_ana#u_bruno",
  "participantIds": ["u_ana", "u_bruno"],
  "subject": null,
  "createdBy": "u_ana",
  "createdAt": "2026-11-03T14:00:00Z",
  "lastMessage": {
    "text": "Obrigada, entendi a regra da cadeia!",
    "senderId": "u_ana",
    "createdAt": "2026-11-03T14:22:10Z"
  },
  "lastMessageAt": "2026-11-03T14:22:10Z",
  "messageCount": 12,
  "lastSeq": 12,
  "readState": {
    "u_ana": { "lastReadSeq": 12 },
    "u_bruno": { "lastReadSeq": 11 }
  }
}
```

**Sala de estudo**

```json
{
  "_id": "c_calc1",
  "type": "group",
  "directKey": null,
  "name": "Sala de Estudo — Cálculo I",
  "subject": "Cálculo I",
  "participantIds": ["u_ana", "u_bruno", "u_carla"],
  "createdBy": "system",
  "createdAt": "2026-10-27T13:30:00Z",
  "lastMessage": {
    "text": "Alguém tem a lista 3 resolvida?",
    "senderId": "u_carla",
    "createdAt": "2026-11-05T19:41:00Z"
  },
  "lastMessageAt": "2026-11-05T19:41:00Z",
  "messageCount": 48,
  "lastSeq": 48,
  "readState": {
    "u_ana": { "lastReadSeq": 40 },
    "u_bruno": { "lastReadSeq": 48 },
    "u_carla": { "lastReadSeq": 48 }
  }
}
```

#### Coleção `messages`

```json
{
  "_id": "m_00012",
  "conversationId": "c_001",
  "seq": 12,
  "senderId": "u_ana",
  "text": "Obrigada, entendi a regra da cadeia!",
  "type": "text",
  "createdAt": "2026-11-03T14:22:10Z"
}
```

```json
{
  "_id": "m_00011",
  "conversationId": "c_001",
  "seq": 11,
  "senderId": "u_bruno",
  "text": "Derive a função de fora e multiplique pela derivada da de dentro.",
  "type": "text",
  "createdAt": "2026-11-03T14:20:45Z"
}
```

**Campos importantes**

| Campo | Função |
|---|---|
| `seq` | Número sequencial **por conversa** (incrementado atomicamente em `conversations.lastSeq`). Garante ordem estável e serve de cursor e de base para "não lidas". |
| `createdAt` | Data/hora definida pelo servidor (nunca pelo cliente), para evitar manipulação do histórico. |
| `directKey` | Impede conversas diretas duplicadas via índice único. |
| `readState.<userId>.lastReadSeq` | Última mensagem lida; não lidas = `lastSeq − lastReadSeq`. |
| `lastMessage` / `lastMessageAt` | Dados desnormalizados para montar a lista de conversas sem consultar `messages`. |

#### Índices

```javascript
// users
db.users.createIndex({ email: 1 }, { unique: true })
db.users.createIndex({ subjects: 1, role: 1 })          // busca de monitores por disciplina

// conversations
db.conversations.createIndex({ directKey: 1 }, { unique: true, sparse: true })
db.conversations.createIndex({ participantIds: 1, lastMessageAt: -1 }) // lista de conversas

// messages
db.messages.createIndex({ conversationId: 1, seq: -1 })                // histórico paginado
db.messages.createIndex({ conversationId: 1, seq: 1 }, { unique: true }) // sem seq duplicado
```

#### Consultas principais

```javascript
// 1. Lista de conversas do usuário (mais recente primeiro)
db.conversations
  .find({ participantIds: "u_ana" })
  .sort({ lastMessageAt: -1 })

// 2. Últimas 30 mensagens de uma conversa
db.messages
  .find({ conversationId: "c_001" })
  .sort({ seq: -1 })
  .limit(30)
// (a API devolve ao cliente em ordem crescente de seq)

// 3. Página anterior (cursor = menor seq já carregada, ex.: 83)
db.messages
  .find({ conversationId: "c_001", seq: { $lt: 83 } })
  .sort({ seq: -1 })
  .limit(30)

// 4. Monitores de uma disciplina
db.users.find({ role: "tutor", subjects: "Cálculo I" })

// 5. Obter seq atômica ao enviar mensagem
db.conversations.findOneAndUpdate(
  { _id: "c_001", participantIds: "u_ana" },   // exige participação
  { $inc: { lastSeq: 1, messageCount: 1 } },
  { returnDocument: "after" }
)
```

### 5.6 Regras de acesso às conversas e ao histórico

| # | Regra |
|---|---|
| **RA01** | Somente usuários **autenticados** acessam qualquer recurso de conversa. |
| **RA02** | Só é possível **ler** o histórico e **enviar** mensagens em conversas em que o usuário consta em `participantIds`. Caso contrário: **403 Forbidden**. |
| **RA03** | A verificação de participação é feita **no servidor, em toda requisição** (nunca confiando só no front-end). |
| **RA04** | O `senderId` da mensagem vem do usuário autenticado, **nunca** do corpo da requisição. |
| **RA05** | Mensagens **não podem ser editadas nem apagadas** no MVP (histórico imutável). |
| **RA06** | Conversa direta: ambos os participantes têm acesso a **todo** o histórico, de forma permanente. |
| **RA07** | Sala de estudo: o participante vê o histórico enquanto for membro. Ao sair, perde o acesso. Ao entrar, vê o histórico anterior à entrada (decisão de transparência para estudo; pode ser alterada em versão futura). |
| **RA08** | Um usuário só altera o **próprio** `readState` (marcar como lido). |
| **RA09** | A listagem de conversas retorna **apenas** as do usuário autenticado. |
| **RA10** | Mensagens têm limite de 2.000 caracteres e o texto é tratado (*escape*) na exibição, para evitar injeção de HTML/script. |
| **RA11** | O banco não é exposto publicamente: somente a API se conecta a ele, com usuário e senha próprios. |

### 5.7 Critérios de aceitação da funcionalidade de conversa

#### Envio

| ID | Critério verificável |
|---|---|
| **CN01** | Dado um participante autenticado, quando envia texto válido, então o documento é inserido em `messages` com `conversationId`, `senderId`, `text`, `seq` e `createdAt` preenchidos, e a API responde **201**. |
| **CN02** | Dado o envio de uma mensagem, então `conversations.lastMessage`, `lastMessageAt` e `messageCount` são atualizados. |
| **CN03** | Dadas duas mensagens enviadas em sequência na mesma conversa, então a segunda tem `seq` **maior** que a primeira, sem repetição. |
| **CN04** | Dado texto vazio, só com espaços ou com mais de 2.000 caracteres, então a API responde **400** e nada é salvo. |
| **CN05** | Dado um usuário que não está em `participantIds`, quando tenta enviar, então a API responde **403** e nada é salvo. |
| **CN06** | Dado que o corpo da requisição traz um `senderId` diferente do usuário autenticado, então o valor é ignorado e o autenticado é usado. |

#### Consulta

| ID | Critério verificável |
|---|---|
| **CN07** | Dada uma conversa com 100 mensagens, quando o histórico é aberto, então são retornadas as 30 mais recentes (`seq` 71 a 100). |
| **CN08** | Dado o cursor `before=71`, quando a próxima página é pedida, então retorna `seq` 41 a 70, sem repetir nem pular mensagens. |
| **CN09** | Dado que a última página foi carregada, quando não há mais mensagens, então a resposta indica fim do histórico (lista vazia / `hasMore = false`). |
| **CN10** | Dado um usuário que não participa da conversa, quando consulta o histórico, então a API responde **403**. |
| **CN11** | Dado um `conversationId` inexistente, quando consultado, então a API responde **404**. |
| **CN12** | Dada a reinicialização da aplicação, quando o histórico é consultado, então todas as mensagens anteriores permanecem (persistência no MongoDB). |
| **CN13** | Dado um usuário com várias conversas, quando lista suas conversas, então elas vêm ordenadas por `lastMessageAt` decrescente e **somente** as dele aparecem. |

#### Ordenação

| ID | Critério verificável |
|---|---|
| **CN14** | As mensagens são sempre exibidas em ordem **crescente de `seq`** (mais antiga no topo, mais recente embaixo). |
| **CN15** | Mensagens com `createdAt` idêntico mantêm ordem estável, pois a ordenação usa `seq`. |
| **CN16** | Dado o envio simultâneo por dois usuários, então as mensagens recebem `seq` distintos e consecutivos (sem colisão). |

#### Início de conversa e não lidas

> CN17 e CN18 fazem parte do **MVP**; CN19 e CN20 (não lidas) fazem parte da **entrega final**.

| ID | Critério verificável |
|---|---|
| **CN17** | Dado que não existe conversa direta entre A e B, quando A inicia conversa com B, então é criada **uma** conversa com `directKey` = IDs ordenados e `participantIds` = [A, B]. |
| **CN18** | Dado que já existe conversa entre A e B, quando B inicia conversa com A, então a conversa existente é reutilizada (coleção continua com **um** documento para o par). |
| **CN19** | Dadas 3 mensagens novas de B enviadas a A, então o contador de não lidas de A é 3 (`lastSeq − lastReadSeq`). |
| **CN20** | Dado que A abre a conversa, então `readState.A.lastReadSeq` passa a ser igual a `lastSeq` e o contador volta a 0. |

#### Desempenho

| ID | Critério verificável |
|---|---|
| **CN21** | Com 100 mil mensagens na coleção, a consulta das 30 últimas de uma conversa responde em até 500 ms (p95) e o `explain()` mostra uso do índice `{conversationId, seq}` (sem `COLLSCAN`). |

### 5.8 Decisões técnicas em aberto (a definir na etapa 2, até 26/10)

| Tema | Opções | Critério de decisão |
|---|---|---|
| Atualização das mensagens | MVP: *polling* a cada 2–3 s. Entrega final: WebSocket (Socket.IO) | Tempo disponível; *polling* permanece como plano B |
| Stack back-end | Node.js + Express **ou** Python + FastAPI | Conhecimento do grupo |
| Stack front-end | React **ou** HTML/JS simples | Conhecimento do grupo |
| Hospedagem do MongoDB | Docker local **ou** MongoDB Atlas (camada gratuita) | Facilidade para o grupo e para a apresentação |

---

## Apêndice — Estrutura sugerida do repositório

```
monitoraai/
├── README.md          # descrição, link para docs/PRD.md e para o GitHub Project
├── docs/
│   └── PRD.md         # este documento
└── (código — etapas seguintes)
```
