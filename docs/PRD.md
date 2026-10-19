# PRD — MonitoraAí

> **Product Requirements Document** · Versão 1.2 · Etapa de planejamento
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
- Novas mensagens exibidas em **tempo real** para os participantes, usando os *listeners* nativos do **Firebase Realtime Database**.
- **Sem servidor próprio**: o front-end acessa o Firebase (Authentication + Realtime Database), protegido por *Security Rules*.

### 2.3 Entrega final (até 16/11/2026)

Após o MVP, a entrega final acrescenta:

- **Salas de estudo por disciplina** (F06).
- **Indicador de mensagens não lidas** (F08).
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
| RNF01 | Desempenho | Carregar as 30 últimas mensagens de uma conversa deve levar no máximo 1 s (p95), baixando apenas essas 30 mensagens, mesmo com 100 mil mensagens armazenadas. |
| RNF02 | Desempenho | O envio de uma mensagem deve ser confirmado ao remetente em até 1 s (p95). |
| RNF03 | Segurança | Autenticação gerenciada pelo Firebase Authentication; senhas nunca são armazenadas pelo sistema. |
| RNF04 | Segurança | Toda leitura e escrita no banco exige usuário autenticado e é validada pelas *Security Rules* do Realtime Database. |
| RNF05 | Segurança | Comunicação via HTTPS em produção. |
| RNF06 | Privacidade | Dados pessoais limitados ao necessário (nome, e-mail, curso), em conformidade com a LGPD. |
| RNF07 | Disponibilidade | Meta de 99% de disponibilidade durante o período de avaliação. |
| RNF08 | Usabilidade | Interface responsiva, utilizável em telas a partir de 360 px de largura. |
| RNF09 | Manutenibilidade | Código versionado no GitHub, com revisão por *pull request* e README com instruções de execução. |
| RNF10 | Escalabilidade | O modelo de dados deve usar estrutura plana, paginação por chave e `.indexOn`, para que o crescimento do histórico não degrade a abertura de conversas. |
| RNF11 | Portabilidade | O sistema deve rodar localmente com o Firebase Emulator Suite, sem depender do projeto em produção. |

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
- **CA05.5** — Dado que não participo da conversa, quando tento enviar mensagem a ela, então a escrita é recusada pelas Security Rules (`PERMISSION_DENIED`) e nada é salvo.

#### HU06 — Consultar histórico

**Como** participante, **quero** ver o histórico de mensagens, **para** rever explicações anteriores.

- **CA06.1** — Dado que abro uma conversa, quando ela carrega, então vejo as 30 mensagens mais recentes, da mais antiga para a mais recente (de cima para baixo).
- **CA06.2** — Dado que existem mais de 30 mensagens, quando rolo até o topo ou clico em "Carregar anteriores", então as 30 mensagens imediatamente anteriores são carregadas, sem repetição nem lacunas.
- **CA06.3** — Dado que duas mensagens são enviadas no mesmo instante, quando o histórico é exibido, então a ordem entre elas é determinística (ordenação pela chave da mensagem).
- **CA06.4** — Dado que não participo da conversa, quando tento consultar o histórico, então a leitura é recusada pelas Security Rules (`PERMISSION_DENIED`).
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

| Integrante | GitHub | Papel | Responsabilidades principais |
|---|---|---|---|
| **Rafael** | **Product Owner / Documentação / QA** | Manter o PRD, o README e o backlog; organizar o GitHub Project; perfil do monitor e busca; testes dos critérios de aceitação |
| **Guilherme** | **Líder técnico / Firebase** | Arquitetura, projeto Firebase e Emulator Suite, Security Rules, criação de conversas e envio de mensagens, salas de estudo |
| **Lucca** | **Modelagem de dados / Back-end** | Modelagem da árvore do Realtime Database, dados de exemplo, autenticação, histórico paginado, tempo real e mensagens não lidas |
| **Metheus** | **Front-end** | Telas de cadastro/login, busca, lista de conversas, chat e salas; integração com o SDK do Firebase |

> Todos revisam *pull requests* uns dos outros. Cada issue tem **um** responsável principal.

### 4.2 Backlog priorizado

Prioridade: **P0** = essencial para o MVP · **P1** = importante · **P2** = desejável.
Entrega: **MVP** = até 02/11/2026 · **Final** = até 16/11/2026.
Cada linha deve virar uma **issue** no GitHub.

| # | Item (título da issue) | Tipo | Prioridade | Responsável | Entrega |
|---|---|---|---|---|---|
| 1 | Escrever e publicar o PRD em `docs/PRD.md` | Documentação | P0 | Rafael | MVP |
| 2 | Criar repositório, README e GitHub Project | Organização | P0 | Rafael | MVP |
| 3 | Cadastrar issues, status e responsáveis no Project | Organização | P0 | Rafael | MVP |
| 4 | Definir arquitetura (front-end + Firebase) e stack tecnológica | Técnico | P0 | Guilherme | MVP |
| 5 | Modelar a árvore do Realtime Database (users, conversations, messages, userConversations) | Banco | P0 | Lucca | MVP |
| 6 | Criar dados de exemplo (seed JSON) e índices (`.indexOn`) | Banco | P0 | Lucca | MVP |
| 7 | Criar projeto Firebase (Authentication + Realtime Database) e configurar Emulator Suite | DevOps | P0 | Guilherme | MVP |
| 8 | Implementar cadastro e login com Firebase Authentication (RF01–RF03) | Feature | P0 | Lucca | MVP |
| 9 | Implementar perfil e disciplinas do monitor (RF04) | Feature | P0 | Rafael | MVP |
| 10 | Implementar busca de monitores por disciplina (RF05) | Feature | P0 | Rafael | MVP |
| 11 | Implementar criação de conversa direta sem duplicidade (RF06–RF07) | Feature | P0 | Guilherme | MVP |
| 12 | Implementar envio de mensagens com validação (RF08) | Feature | P0 | Guilherme | MVP |
| 13 | Implementar consulta paginada do histórico (RF09–RF10) | Feature | P0 | Lucca | MVP |
| 14 | Escrever Security Rules de controle de acesso por participante (RF14) | Feature | P0 | Guilherme | MVP |
| 15 | Tela de cadastro e login | Front-end | P0 | Metheus | MVP |
| 16 | Tela de busca de monitores | Front-end | P0 | Metheus | MVP |
| 17 | Tela de chat (envio, histórico, rolagem e tempo real) | Front-end | P0 | Metheus | MVP |
| 18 | Lista de conversas ordenada por atividade (RF11) | Feature | P0 | Metheus | MVP |
| 19 | Contador de mensagens não lidas (RF12) | Feature | P1 | Lucca | Final |
| 20 | Salas de estudo por disciplina (RF13) | Feature | P1 | Guilherme | Final |
| 21 | Sincronização em tempo real com *listeners* (`onChildAdded`) | Técnico | P0 | Lucca | MVP |
| 22 | Testes dos critérios de aceitação (HU01–HU08) e das Security Rules | Qualidade | P1 | Rafael | Final |
| 23 | Edição de perfil (RF15) | Feature | P2 | Metheus | Final |
| 24 | Documentar estrutura de dados, Security Rules e instruções de execução no README | Documentação | P2 | Rafael | Final |
| 25 | Telas de salas de estudo e indicador de não lidas | Front-end | P1 | Metheus | Final |

### 4.3 Etapas e prazos

| Etapa | Período | Entregas | Marco |
|---|---|---|---|
| **1. Planejamento** | 19/10 – 22/10/2026 | PRD publicado, repositório e GitHub Project com issues | Entrega do planejamento |
| **2. Fundação técnica** | 23/10 – 26/10/2026 | Projeto Firebase, Emulator Suite, árvore de dados modelada, Security Rules iniciais, autenticação | Ambiente rodando para todos |
| **3. Núcleo do chat (MVP)** | 27/10 – 02/11/2026 | Perfil, busca de monitores, conversa direta, envio, histórico paginado, tempo real, lista de conversas | **MVP entregue até 02/11/2026** |
| **4. Complementos** | 03/11 – 09/11/2026 | Salas de estudo, mensagens não lidas, edição de perfil | Funcionalidades finais prontas |
| **5. Testes e documentação** | 10/11 – 14/11/2026 | Testes dos critérios de aceitação e das Security Rules, correções, README | Versão estável |
| **6. Entrega final** | 15/11 – 16/11/2026 | Revisão dos links, do PRD e do Project | **Entrega final até 16/11/2026** |

### 4.4 Dependências

| Dependência | Impacto | Tratamento |
|---|---|---|
| Projeto Firebase (#7) criado antes de qualquer código que use o banco | Alto | Primeira tarefa técnica da etapa 2 (até 24/10) |
| Modelagem da árvore do Realtime Database (#5) precisa estar pronta antes das features de chat (#11–#14, #21) | Alto | Concluir #5 e #6 na etapa 2 (até 26/10) |
| Autenticação (#8) é pré-requisito para as Security Rules (#14), que usam `auth.uid` | Alto | Priorizar logo após a criação do projeto Firebase |
| Telas de chat (#17) dependem dos serviços de envio, histórico e tempo real (#12, #13, #21) | Médio | Front-end usa dados simulados (*mock*) ou o Emulator até os serviços ficarem prontos |
| Lista de conversas (#18) depende da estrutura de conversas (#11) | Médio | Lista de conversas no MVP; não lidas (#19) na etapa 4 |
| Disponibilidade de ferramentas externas (GitHub, Firebase, Node.js) | Baixo | Alternativa: Firebase Emulator Suite local |

### 4.5 Riscos e estratégias de mitigação

| # | Risco | Probabilidade | Impacto | Estratégia |
|---|---|---|---|---|
| R1 | Prazo curto: MVP em 2 semanas (até 02/11) com 4 integrantes | Alta | Alto | MVP reduzido ao fluxo essencial; salas e não lidas ficam para a entrega final; itens P2 só entram se sobrar tempo |
| R2 | Pouca experiência do grupo com Realtime Database e Security Rules | Média | Médio | Estudo guiado na etapa 2; modelagem e regras revisadas em conjunto; testes no Emulator Suite |
| R3 | Integrante ausente ou com pouca disponibilidade (equipe de 4 pessoas) | Média | Alto | Revisão cruzada de PRs; conhecimento compartilhado; redistribuir issues na reunião |
| R4 | Limites do plano gratuito do Firebase e Security Rules mal configuradas | Média | Médio | Conferir os limites do plano antes da demonstração; manter dados de teste pequenos; testar as regras no Emulator e evitar regras abertas (`.read/.write: true`) no projeto publicado |
| R5 | Conflitos de merge | Alta | Baixo | Branches curtas por issue, PRs pequenos, `main` protegida |
| R6 | Degradação de desempenho com muitas mensagens | Baixa | Médio | Índices desde o início; paginação por cursor; teste com dados de exemplo em volume |
| R7 | Vazamento de conversas por falha de autorização | Baixa | Alto | Verificação de participação em **toda** consulta/escrita; testes dedicados (CA05.5, CA06.4) |
| R8 | Dados pessoais de estudantes (LGPD) | Baixa | Médio | Coletar apenas o necessário; usar dados fictícios em testes e demonstração |

### 4.6 Acompanhamento do andamento

- **GitHub Project público** com colunas **A fazer → Em andamento → Concluído**, vinculado ao repositório.
- **Campos do Project:** responsável, prioridade (P0/P1/P2), entrega (MVP ou Final), etapa (milestone).
- **Issues** com critérios de aceitação no corpo e rótulos (`feature`, `banco`, `front-end`, `documentação`, `bug`).
- **Reunião** de 30 min **duas vezes por semana** (prazo curto): o que foi concluído, o que está bloqueado, replanejamento.
- **Daily assíncrona** (mensagem curta no grupo): ontem, hoje, bloqueios.
- **Regra de fluxo:** ninguém tem mais de 2 issues em "Em andamento" ao mesmo tempo.
- **Definição de pronto:** código revisado em PR, critérios de aceitação verificados, issue movida para "Concluído".
- **Acompanhamento de progresso:** issues concluídas vs. planejadas por etapa (e por entrega: MVP e Final), comparadas a cada reunião.

---

## 5. Funcionalidade de conversa com NoSQL

Banco escolhido: **Firebase Realtime Database**, banco NoSQL que guarda os dados em uma **árvore JSON** e sincroniza as alterações com os clientes conectados em tempo real.

### 5.1 Quem pode conversar

| Tipo de conversa | Participantes | Quem pode iniciar |
|---|---|---|
| **Direta (1:1)** | Exatamente 2 usuários cadastrados | Qualquer usuário autenticado, a partir do perfil de outro |
| **Sala de estudo (grupo)** *(entrega final)* | Vários usuários, vinculada a uma disciplina | Salas são criadas pela equipe (seed/console do Firebase); qualquer usuário autenticado pode entrar |

Combinações permitidas na conversa direta: aluno ↔ monitor, aluno ↔ aluno, monitor ↔ monitor.

### 5.2 Como as conversas são iniciadas

**Conversa direta** (três passos, nesta ordem):

1. O usuário abre o perfil de outra pessoa e clica em **Conversar**.
2. O app monta a chave `directKey` com os dois UIDs em ordem alfabética (ex.: `uidAna_uidBruno`) e tenta gravar `directConversations/{directKey} = {conversationId}`. A regra `!data.exists()` faz a gravação funcionar **uma única vez**. Se ela falhar, a conversa já existe: o app lê o `conversationId` salvo e a abre (nenhuma duplicata, mesmo com dois cliques simultâneos).
3. Se a gravação foi aceita, o app cria `conversations/{conversationId}` (metadados e os 2 participantes) e, em seguida, registra a conversa em `userConversations/{uid}/{conversationId}` para os dois usuários.

**Sala de estudo** *(entrega final, até 16/11)*

1. O usuário abre a lista de salas por disciplina e clica em **Entrar**.
2. Seu UID é gravado em `conversations/{id}/participants/{uid}` (operação idempotente).
3. Para sair, esse nó é removido; o acesso ao histórico é encerrado imediatamente.

### 5.3 Como as mensagens são enviadas, consultadas e armazenadas

**Envio**

1. O app gera a chave da mensagem com `push()`. Essas chaves são **ordenadas cronologicamente**.
2. O app grava tudo em **uma única operação atômica** (`update` em vários caminhos): a mensagem em `messages/{conversationId}/{messageId}`, o resumo `lastMessage`/`lastMessageAt` em `conversations/{id}/meta` e o `lastMessageAt` de cada participante em `userConversations`.
3. O horário `createdAt` é o **do servidor** (`serverTimestamp()`), nunca o do dispositivo.
4. As **Security Rules** validam a escrita (usuário é participante, `senderId` é o usuário autenticado, texto de 1 a 2.000 caracteres). Se qualquer regra falhar, **nada** é gravado.
5. Os outros participantes recebem a mensagem pelo *listener* (`onChildAdded`), sem recarregar a página.

**Consulta**

- Histórico: lê as 30 últimas mensagens ordenadas pela chave; páginas anteriores usam a menor chave já carregada como cursor.
- Lista de conversas: lê `userConversations/{uid}` ordenado por `lastMessageAt` e busca os metadados de cada conversa.

**Armazenamento**

- As mensagens ficam em uma **árvore separada** (`messages`), e não dentro de `conversations`. Como o Realtime Database baixa **todos os filhos** de um nó ao lê-lo, essa separação permite abrir uma conversa ou listar as conversas sem baixar o histórico completo.

### 5.4 Banco NoSQL escolhido e justificativa

**Escolha: Firebase Realtime Database** (banco NoSQL em árvore JSON, definido como requisito da disciplina).

| Critério | Justificativa |
|---|---|
| **Tempo real nativo** | O SDK mantém uma conexão aberta e notifica os clientes a cada nova mensagem (`onChildAdded`), sem *polling* nem servidor WebSocket próprio. |
| **Adequação ao chat** | Dados simples, gravações pequenas e frequentes e necessidade de baixa latência, que é o caso de uso típico do Realtime Database. |
| **Sem servidor próprio** | O front-end acessa o banco direto; as Security Rules garantem o controle de acesso. Isso reduz o trabalho do MVP de 2 semanas. |
| **Autenticação integrada** | O Firebase Authentication fornece `auth.uid`, usado nas regras para saber quem é o participante. |
| **Ordenação por chave** | As chaves geradas por `push()` são cronológicas, o que dá ordem estável das mensagens sem precisar de campo extra. |
| **Desenvolvimento local** | O Firebase Emulator Suite permite testar banco, autenticação e regras sem usar o projeto publicado. |
| **Custo** | O plano gratuito atende o volume de uma demonstração acadêmica. |

**Limitações do Realtime Database e como o projeto lida com elas**

| Limitação | Como lidamos |
|---|---|
| Não há *joins* entre nós | Dados **denormalizados**: o resumo da última mensagem fica na conversa; um índice por usuário (`userConversations`) lista suas conversas. |
| Ler um nó baixa todos os seus filhos | Estrutura **plana**: mensagens, participantes e metadados em árvores separadas. |
| Consultas aceitam apenas uma ordenação/filtro por vez | Uso da **chave** como ordenação principal do histórico e de `.indexOn` onde há `orderByChild`. |
| Não há contagem nativa de itens | "Não lidas" é calculado a partir de `lastReadKey` (última mensagem lida) de cada usuário. |
| Não há transações entre vários nós sem regras próprias | Uso de `update` em múltiplos caminhos (atômico) e regra `!data.exists()` para evitar duplicatas. |

**Alternativas consideradas**

- **Cloud Firestore:** também NoSQL e do Firebase, com consultas mais ricas, mas o Realtime Database é o solicitado e é mais simples para mensagens em fluxo contínuo.
- **MongoDB:** consultas mais flexíveis, porém exigiria servidor próprio e WebSocket para o tempo real, o que não cabe no prazo do MVP.

### 5.5 Organização dos dados

Árvore principal do banco (nós no nível raiz):

```
/
├── users/{uid}
├── subjects/{subjectId}
├── subjectTutors/{subjectId}/{uid}
├── directConversations/{directKey}
├── conversations/{conversationId}/meta
│                                 /participants/{uid}
├── messages/{conversationId}/{messageId}
└── userConversations/{uid}/{conversationId}
```

| Nó | Função |
|---|---|
| `users` | Perfil público do usuário (nome, papel, curso, disciplinas). O e-mail e a senha ficam apenas no Firebase Authentication. |
| `subjects` | Catálogo de disciplinas. |
| `subjectTutors` | Índice para a **busca de monitores por disciplina**. |
| `directConversations` | Garante **uma única** conversa direta por par de usuários. |
| `conversations` | Metadados, resumo da última mensagem e participantes. |
| `messages` | **Todas as mensagens**, agrupadas por conversa. |
| `userConversations` | Índice por usuário: lista de conversas, atividade mais recente e última mensagem lida. |

#### Exemplo de dados (árvore JSON)

> Valores de tempo são *timestamps* em milissegundos. As chaves como `-Oa1mMsg0012` representam IDs gerados por `push()`.

```json
{
  "users": {
    "uidAna": {
      "name": "Ana Souza",
      "role": "student",
      "course": "Ciência da Computação",
      "createdAt": 1793000000000
    },
    "uidBruno": {
      "name": "Bruno Lima",
      "role": "tutor",
      "course": "Ciência da Computação",
      "subjects": { "calculo1": true, "programacao1": true },
      "createdAt": 1793000300000
    }
  },

  "subjects": {
    "calculo1":     { "name": "Cálculo I" },
    "programacao1": { "name": "Programação I" }
  },

  "subjectTutors": {
    "calculo1":     { "uidBruno": true },
    "programacao1": { "uidBruno": true }
  },

  "directConversations": {
    "uidAna_uidBruno": "-Oa1cConvAnaBruno"
  },

  "conversations": {
    "-Oa1cConvAnaBruno": {
      "meta": {
        "type": "direct",
        "createdBy": "uidAna",
        "createdAt": 1793714400000,
        "lastMessage": {
          "text": "Obrigada, entendi a regra da cadeia!",
          "senderId": "uidAna",
          "createdAt": 1793715730000
        },
        "lastMessageAt": 1793715730000
      },
      "participants": { "uidAna": true, "uidBruno": true }
    },
    "-Oa1cRoomCalculo1": {
      "meta": {
        "type": "group",
        "name": "Sala de Estudo — Cálculo I",
        "subject": "calculo1",
        "createdBy": "system",
        "createdAt": 1793000600000,
        "lastMessage": {
          "text": "Alguém tem a lista 3 resolvida?",
          "senderId": "uidCarla",
          "createdAt": 1793900000000
        },
        "lastMessageAt": 1793900000000
      },
      "participants": { "uidAna": true, "uidBruno": true, "uidCarla": true }
    }
  },

  "messages": {
    "-Oa1cConvAnaBruno": {
      "-Oa1mMsg0011": {
        "senderId": "uidBruno",
        "text": "Derive a função de fora e multiplique pela derivada da de dentro.",
        "createdAt": 1793715645000
      },
      "-Oa1mMsg0012": {
        "senderId": "uidAna",
        "text": "Obrigada, entendi a regra da cadeia!",
        "createdAt": 1793715730000
      }
    }
  },

  "userConversations": {
    "uidAna": {
      "-Oa1cConvAnaBruno": { "lastMessageAt": 1793715730000, "lastReadKey": "-Oa1mMsg0012" },
      "-Oa1cRoomCalculo1": { "lastMessageAt": 1793900000000, "lastReadKey": "-Oa1mRoom0040" }
    },
    "uidBruno": {
      "-Oa1cConvAnaBruno": { "lastMessageAt": 1793715730000, "lastReadKey": "-Oa1mMsg0011" }
    }
  }
}
```

No exemplo, Bruno leu até `-Oa1mMsg0011`; portanto, tem **1 mensagem não lida** (a `-Oa1mMsg0012`).

**Campos importantes**

| Campo | Função |
|---|---|
| Chave da mensagem (`push()`) | Ordem cronológica estável e única; serve de **cursor** na paginação. |
| `createdAt` | Horário do servidor (`serverTimestamp()`), para exibição e para evitar manipulação do histórico. |
| `directConversations/{directKey}` | Trava contra conversas diretas duplicadas. |
| `userConversations/{uid}/{cid}/lastReadKey` | Última mensagem lida pelo usuário; não lidas = mensagens com chave maior que ela. |
| `meta/lastMessage` e `lastMessageAt` | Dados desnormalizados para montar a lista de conversas sem ler `messages`. |

#### Índices

O Realtime Database ordena por **chave** sem configuração. Só é preciso declarar índice para `orderByChild`:

```json
{
  "rules": {
    "userConversations": {
      "$uid": { ".indexOn": ["lastMessageAt"] }
    }
  }
}
```

#### Consultas principais (SDK modular do Firebase para JavaScript)

```javascript
import {
  ref, query, get, push, update, serverTimestamp,
  orderByKey, orderByChild, limitToLast, limitToFirst,
  endBefore, startAfter, onChildAdded
} from "firebase/database";

// 1. Lista de conversas do usuário (as 20 mais recentes; o app inverte para exibir a mais nova primeiro)
query(ref(db, `userConversations/${uid}`), orderByChild("lastMessageAt"), limitToLast(20));

// 2. Últimas 30 mensagens + novas mensagens em tempo real
onChildAdded(
  query(ref(db, `messages/${cid}`), orderByKey(), limitToLast(30)),
  (snap) => renderMessage(snap.key, snap.val())
);

// 3. Página anterior (cursor = menor chave já carregada)
query(ref(db, `messages/${cid}`), orderByKey(), endBefore(oldestKey), limitToLast(30));

// 4. Envio atômico (mensagem + resumo da conversa + atividade dos participantes)
const msgKey = push(ref(db, `messages/${cid}`)).key;
await update(ref(db), {
  [`messages/${cid}/${msgKey}`]: { senderId: uid, text, createdAt: serverTimestamp() },
  [`conversations/${cid}/meta/lastMessage`]: { text, senderId: uid, createdAt: serverTimestamp() },
  [`conversations/${cid}/meta/lastMessageAt`]: serverTimestamp(),
  [`userConversations/${uid}/${cid}/lastMessageAt`]: serverTimestamp(),
  [`userConversations/${otherUid}/${cid}/lastMessageAt`]: serverTimestamp(),
});

// 5. Mensagens não lidas (as que vieram depois da última lida)
query(ref(db, `messages/${cid}`), orderByKey(), startAfter(lastReadKey), limitToFirst(100));

// 6. Monitores de uma disciplina (depois, lê-se users/{uid} de cada um)
get(ref(db, `subjectTutors/${subjectId}`));

// 7. Trava contra conversa direta duplicada (falha se a chave já existir)
await update(ref(db), { [`directConversations/${directKey}`]: cid });
```

### 5.6 Regras de acesso às conversas e ao histórico

As regras são aplicadas **no servidor do Firebase** (Security Rules), em toda leitura e escrita.

| # | Regra |
|---|---|
| **RA01** | Somente usuários **autenticados** (Firebase Authentication) acessam qualquer dado de conversa. |
| **RA02** | Só é possível **ler** o histórico e **enviar** mensagens em conversas em que o usuário consta em `participants`. Caso contrário, o Firebase recusa a operação com `PERMISSION_DENIED`. |
| **RA03** | A verificação é feita pelas Security Rules, **nunca** apenas no front-end. |
| **RA04** | O `senderId` da mensagem precisa ser igual ao `auth.uid` de quem escreve. |
| **RA05** | Mensagens **não podem ser editadas nem apagadas** no MVP: a regra só permite escrita se o nó ainda não existe (`!data.exists()`). |
| **RA06** | Conversa direta: ambos os participantes têm acesso a **todo** o histórico, de forma permanente. |
| **RA07** | Sala de estudo: o participante vê o histórico enquanto for membro. Ao sair, o nó em `participants` é removido e a leitura passa a ser negada. Ao entrar, vê o histórico anterior à entrada (decisão de transparência para estudo; pode mudar em versão futura). |
| **RA08** | Cada usuário só altera o **próprio** `lastReadKey`. Os demais participantes só podem atualizar `lastMessageAt` no índice dele. |
| **RA09** | `userConversations/{uid}` só pode ser **lido** pelo próprio usuário; a lista de conversas é sempre a do usuário autenticado. |
| **RA10** | Texto com 1 a 2.000 caracteres e ao menos um caractere visível; na exibição, o texto é tratado (*escape*) para evitar injeção de HTML/script. |
| **RA11** | O horário `createdAt` deve ser igual ao horário do servidor (`now` nas regras). |
| **RA12** | Não há permissão de leitura na raiz nem em `/messages` ou `/conversations` como um todo: só se lê por conversa, e apenas se for participante. |
| **RA13** | O projeto publicado **nunca** usa regras abertas (`".read": true` / `".write": true`). |

**Esboço inicial das Security Rules** (será refinado e testado no Emulator Suite durante a etapa 2):

```json
{
  "rules": {
    ".read": false,
    ".write": false,

    "users": {
      "$uid": {
        ".read": "auth != null",
        ".write": "auth != null && auth.uid === $uid",
        "role": { ".validate": "newData.val() === 'student' || newData.val() === 'tutor'" }
      }
    },

    "subjects": { ".read": "auth != null" },

    "subjectTutors": {
      "$subjectId": {
        ".read": "auth != null",
        "$uid": { ".write": "auth != null && auth.uid === $uid" }
      }
    },

    "directConversations": {
      "$key": {
        ".read":  "auth != null && ($key.beginsWith(auth.uid) || $key.endsWith(auth.uid))",
        ".write": "auth != null && !data.exists() && ($key.beginsWith(auth.uid) || $key.endsWith(auth.uid))"
      }
    },

    "conversations": {
      "$cid": {
        ".read": "auth != null && data.child('participants').child(auth.uid).exists()",
        ".write": "auth != null && !data.exists() && newData.child('meta').child('type').val() === 'direct' && newData.child('participants').numChildren() === 2 && newData.child('participants').child(auth.uid).exists()",
        "meta": {
          "lastMessage":   { ".write": "auth != null && root.child('conversations').child($cid).child('participants').child(auth.uid).exists()" },
          "lastMessageAt": { ".write": "auth != null && root.child('conversations').child($cid).child('participants').child(auth.uid).exists()" }
        },
        "participants": {
          "$uid": {
            ".write": "auth != null && auth.uid === $uid && data.parent().parent().child('meta').child('type').val() === 'group'"
          }
        }
      }
    },

    "messages": {
      "$cid": {
        ".read": "auth != null && root.child('conversations').child($cid).child('participants').child(auth.uid).exists()",
        "$mid": {
          ".write": "auth != null && !data.exists() && root.child('conversations').child($cid).child('participants').child(auth.uid).exists()",
          ".validate": "newData.hasChildren(['senderId','text','createdAt']) && newData.child('senderId').val() === auth.uid && newData.child('text').isString() && newData.child('text').val().length > 0 && newData.child('text').val().length <= 2000 && newData.child('text').val().matches(/.*\\S.*/) && newData.child('createdAt').val() === now"
        }
      }
    },

    "userConversations": {
      "$uid": {
        ".indexOn": ["lastMessageAt"],
        ".read": "auth != null && auth.uid === $uid",
        "$cid": {
          ".write": "auth != null && auth.uid === $uid",
          "lastMessageAt": {
            ".write": "auth != null && root.child('conversations').child($cid).child('participants').child(auth.uid).exists()"
          }
        }
      }
    }
  }
}
```

### 5.7 Critérios de aceitação da funcionalidade de conversa

#### Envio

| ID | Critério verificável |
|---|---|
| **CN01** | Dado um participante autenticado, quando envia texto válido, então a mensagem é gravada em `messages/{conversationId}/{messageId}` com `senderId`, `text` e `createdAt` (horário do servidor) preenchidos. |
| **CN02** | Dado o envio de uma mensagem, então `meta/lastMessage`, `meta/lastMessageAt` e o `lastMessageAt` de **todos** os participantes são atualizados na mesma operação. |
| **CN03** | Dadas duas mensagens enviadas em sequência na mesma conversa, então a chave da segunda é **maior** que a da primeira. |
| **CN04** | Dado texto vazio, só com espaços ou com mais de 2.000 caracteres, então a escrita é recusada (`PERMISSION_DENIED`) e nada é salvo. |
| **CN05** | Dado um usuário que não está em `participants`, quando tenta enviar, então a escrita é recusada (`PERMISSION_DENIED`) e nada é salvo. |
| **CN06** | Dado que o `senderId` informado é diferente do `auth.uid` do usuário, então a escrita é recusada. |
| **CN07** | Dada uma mensagem já salva, quando alguém tenta editá-la ou apagá-la, então a operação é recusada. |

#### Consulta

| ID | Critério verificável |
|---|---|
| **CN08** | Dada uma conversa com 100 mensagens, quando o histórico é aberto, então são exibidas as 30 mais recentes (mensagens 71 a 100). |
| **CN09** | Dado o cursor igual à chave da mensagem 71, quando a página anterior é pedida, então retornam as mensagens 41 a 70, sem repetir nem pular nenhuma. |
| **CN10** | Dado que não há mais mensagens antigas, quando o usuário tenta carregar mais, então o app indica o fim do histórico. |
| **CN11** | Dado um usuário que não participa da conversa, quando consulta o histórico, então a leitura é recusada (`PERMISSION_DENIED`). |
| **CN12** | Dado que o usuário fecha e reabre o app, quando abre a conversa, então todas as mensagens anteriores permanecem (persistência no banco). |
| **CN13** | Dado um usuário com várias conversas, quando abre a lista, então elas aparecem ordenadas por `lastMessageAt` (mais recente primeiro) e **somente** as dele aparecem. |

#### Tempo real

| ID | Critério verificável |
|---|---|
| **CN14** | Dados dois usuários com a mesma conversa aberta, quando um envia uma mensagem, então ela aparece para o outro em até 2 s, **sem recarregar a página**. |
| **CN15** | Dado que a lista de conversas está aberta, quando chega mensagem em uma conversa, então essa conversa sobe para o topo da lista sem recarregar. |

#### Ordenação

| ID | Critério verificável |
|---|---|
| **CN16** | As mensagens são sempre exibidas em ordem **crescente de chave** (mais antiga no topo, mais recente embaixo). |
| **CN17** | Dado o envio simultâneo por dois usuários, então as duas mensagens são salvas, com chaves distintas, e **todos** os participantes as veem na mesma ordem. |

#### Início de conversa e não lidas

> CN18 e CN19 fazem parte do **MVP**; CN20 e CN21 (não lidas) fazem parte da **entrega final**.

| ID | Critério verificável |
|---|---|
| **CN18** | Dado que não existe conversa direta entre A e B, quando A inicia conversa com B, então são criados `directConversations/{uidA_uidB}`, a conversa com 2 participantes e as entradas em `userConversations` dos dois. |
| **CN19** | Dado que já existe conversa entre A e B, quando B inicia conversa com A (ou A clica duas vezes seguidas), então a conversa existente é reutilizada e continua existindo **uma só** conversa para o par. |
| **CN20** | Dadas 3 mensagens novas de B para A após o `lastReadKey` de A, então o indicador de A mostra 3 não lidas. |
| **CN21** | Dado que A abre a conversa, então `lastReadKey` de A passa a ser a chave da última mensagem e o indicador volta a 0. |

#### Desempenho e segurança

| ID | Critério verificável |
|---|---|
| **CN22** | Com 100 mil mensagens em uma conversa, abrir o histórico baixa apenas 30 mensagens e leva até 1 s (p95). |
| **CN23** | Dado um usuário **não autenticado**, quando tenta ler ou escrever em qualquer nó, então a operação é recusada. |
| **CN24** | As Security Rules possuem testes automatizados no Emulator Suite cobrindo CN05, CN06, CN07 e CN11. |

### 5.8 Decisões técnicas em aberto (a definir na etapa 2, até 26/10)

| Tema | Opções | Critério de decisão |
|---|---|---|
| Front-end | React **ou** HTML/JS simples (com o SDK modular do Firebase) | Conhecimento do grupo |
| Hospedagem | Firebase Hosting **ou** GitHub Pages | Facilidade para a demonstração |
| Região do banco | Opções oferecidas pelo Firebase no momento da criação | Menor latência disponível; a região não pode ser trocada depois |
| Automação das regras | Testes com Emulator Suite via `@firebase/rules-unit-testing` | Tempo disponível; ao menos testes manuais no Emulator |

---

## Apêndice — Estrutura sugerida do repositório

```
monitoraai/
├── README.md              # descrição, link para docs/PRD.md e para o GitHub Project
├── docs/
│   └── PRD.md             # este documento
├── firebase/
│   ├── database.rules.json   # Security Rules
│   └── seed.json             # dados de exemplo para importar
└── (código do front-end — etapas seguintes)
```
