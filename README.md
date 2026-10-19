# MonitoraAí

Plataforma que conecta estudantes que precisam de ajuda em uma disciplina com monitores e colegas que dominam o conteúdo, centralizando dúvidas e histórico de conversas em um único lugar.

> **Status:** etapa de planejamento (PRD e organização do projeto). O sistema ainda não foi implementado.

## Links do projeto

| Item | Link |
|---|---|
| 📄 **PRD (Documento de Requisitos do Produto)** | [docs/PRD.md](docs/PRD.md) |
| 📋 **GitHub Project (acompanhamento das atividades)** | `<COLE AQUI O LINK DO GITHUB PROJECT>` |
| 📁 **Repositório** | `<COLE AQUI O LINK DO REPOSITÓRIO>` |

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

As conversas, participantes e mensagens são armazenadas em **MongoDB**, organizadas em três coleções:

| Coleção | Conteúdo |
|---|---|
| `users` | Dados de perfil, papel (aluno ou monitor) e disciplinas atendidas |
| `conversations` | Conversas diretas e salas, com participantes, última mensagem e estado de leitura |
| `messages` | Uma mensagem por documento, com número de sequência por conversa |

A justificativa da escolha, exemplos de documentos, índices, regras de acesso e critérios de aceitação estão na [seção 5 do PRD](docs/PRD.md#5-funcionalidade-de-conversa-com-nosql).

## Escopo do MVP

- Cadastro, login e perfil
- Cadastro de disciplinas pelo monitor
- Busca de monitores por disciplina
- Conversa direta (1:1) e salas de estudo
- Histórico de mensagens com paginação
- Indicador de mensagens não lidas

Fora do MVP: agendamento, envio de arquivos, notificações, avaliação de monitores e painel de coordenação. Veja o [escopo completo](docs/PRD.md#2-escopo).


Responsabilidades detalhadas, backlog, prazos, dependências e riscos estão na [gerência do projeto](docs/PRD.md#4-gerência-do-projeto).

## Organização do trabalho

- **Atividades:** cada tarefa é uma *issue* com responsável, prioridade e estimativa.
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
