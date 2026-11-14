# MonitoraAí

Plataforma que conecta estudantes que precisam de ajuda em uma disciplina com monitores e colegas que dominam o conteúdo, centralizando dúvidas e histórico de conversas em um único lugar.

> **Status:** etapa de planejamento (PRD e organização do projeto). O sistema ainda não foi implementado.

## Links do projeto

| Item | Link |
|---|---|
| 📄 **PRD (Documento de Requisitos do Produto)** | [docs/PRD.md](docs/PRD.md) |
| 📋 **GitHub Project (acompanhamento das atividades)** | `https://github.com/luccaborelladev/MonitoraAI/projects` |
| 📁 **Repositório** | `https://github.com/luccaborelladev/MonitoraAI` |

## Sobre o projeto

### Problema

Em cursos de graduação e técnicos, a ajuda de monitores e veteranos existe, mas está dispersa em grupos de WhatsApp, murais e listas em PDF. Não há como saber quem ajuda em qual disciplina, e as dúvidas se perdem em conversas misturadas, sem histórico consultável.

### Solução

Uma aplicação web onde:

- monitores cadastram as disciplinas em que atendem;
- alunos buscam monitores por disciplina;
- usuários conversam em **chats diretos (1:1)** e em **salas de estudo por disciplina**;
- todo o histórico de mensagens fica salvo e pode ser consultado depois.

### Público-alvo

Estudantes (alunos), monitores e, em versões futuras, coordenadores de monitoria.

## Funcionalidade de conversa (NoSQL)

As conversas, participantes e mensagens são armazenadas no **Firebase Realtime Database**, banco NoSQL em árvore JSON com sincronização em tempo real. O controle de acesso é feito pelas *Security Rules*, com login via Firebase Authentication.

| Nó do banco | Conteúdo |
|---|---|
| `users` | Perfil público, papel (aluno ou monitor) e disciplinas atendidas |
| `subjectTutors` | Índice para buscar monitores por disciplina |
| `directConversations` | Garante uma única conversa direta por par de usuários |
| `conversations` | Metadados, última mensagem e participantes |
| `messages` | Mensagens agrupadas por conversa, ordenadas pela chave |
| `userConversations` | Lista de conversas de cada usuário e última mensagem lida |

A justificativa da escolha, exemplos de dados, regras de acesso e critérios de aceitação estão na [seção 5 do PRD](docs/PRD.md#5-funcionalidade-de-conversa-com-nosql).

## Escopo e prazos

**MVP — até 02/11/2026**

- Cadastro, login e perfil
- Cadastro de disciplinas pelo monitor
- Busca de monitores por disciplina
- Conversa direta (1:1) com histórico paginado
- Lista de conversas ordenada por atividade
- Controle de acesso por participante
- Mensagens em tempo real

**Entrega final — até 16/11/2026**

- Salas de estudo por disciplina
- Indicador de mensagens não lidas
- Edição de perfil, testes e documentação final

Fora do projeto atual: agendamento, envio de arquivos, notificações, avaliação de monitores e painel de coordenação. Veja o [escopo completo](docs/PRD.md#2-escopo).

## Equipe

| Integrante | Papel |
|---|---|
| Rafael | Product Owner / Documentação / QA |
| Guilherme | Líder técnico / Firebase |
| Lucca | Modelagem de dados / Back-end |
| Metheus | Front-end |

Responsabilidades detalhadas, backlog, prazos, dependências e riscos estão na [gerência do projeto](docs/PRD.md#4-gerência-do-projeto).

## Organização do trabalho

- **Atividades:** cada tarefa é uma *issue* com responsável, prioridade e entrega (MVP ou Final).
- **Acompanhamento:** GitHub Project com colunas **A fazer → Em andamento → Concluído**.
- **Fluxo:** uma branch por issue, *pull request* com revisão de outro integrante e merge na `main`.

## Estrutura do repositório

```
.
├── README.md
└── docs/
    └── PRD.md
```

A estrutura do código será definida nas próximas etapas.
