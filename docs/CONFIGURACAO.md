# Como configurar e executar o MonitoraAí

O chat usa **Firebase Authentication** (login) e **Firebase Realtime Database** (conversas e mensagens). Não há servidor próprio: o arquivo `app/index.html` conversa direto com o Firebase, e as **Security Rules** (`firebase/database.rules.json`) controlam quem pode ler e escrever.

## 1. Criar o projeto no Firebase

1. Acesse o [console do Firebase](https://console.firebase.google.com) com uma conta Google e clique em **Criar um projeto** (pode desativar o Google Analytics).
2. No menu **Build → Authentication**, clique em **Vamos começar**, abra **Sign-in method** e ative **E-mail/senha**.
3. No menu **Build → Realtime Database**, clique em **Criar banco de dados**. Escolha a região e inicie no **modo bloqueado** (as regras do passo 3 liberam o acesso certo).

## 2. Publicar as regras de segurança

1. Em **Realtime Database → Regras**, apague o conteúdo e cole o arquivo `firebase/database.rules.json`.
2. Clique em **Publicar**.

## 3. Importar os dados iniciais (disciplinas e salas de estudo)

1. Em **Realtime Database → Dados**, clique no menu de três pontos (⋮) do nó raiz e escolha **Importar JSON**.
2. Selecione o arquivo `firebase/seed.json`. Faça isso com o banco **vazio**, pois a importação na raiz substitui o conteúdo.

## 4. Conectar o app ao seu projeto

1. Em **Configurações do projeto (engrenagem) → Seus apps**, clique no ícone `</>` (Web) e registre um app.
2. Copie o objeto `firebaseConfig` mostrado pelo Firebase.
3. Abra `app/index.html`, procure o bloco `COLE AQUI A CONFIGURAÇÃO` e substitua os valores.
4. Se o `databaseURL` não aparecer no objeto, copie a URL que aparece no topo da aba **Realtime Database → Dados**.

> Os valores do `firebaseConfig` não são senhas: eles identificam o projeto. Quem protege os dados são as Security Rules do passo 2.

## 5. Executar

Os módulos do Firebase não funcionam abrindo o arquivo direto (`file://`). Use um servidor local, por exemplo:

```bash
# na raiz do repositório
python3 -m http.server 8000
# abra http://localhost:8000/app/
```

(ou a extensão **Live Server** do VS Code).

## 6. Testar o fluxo completo

Use **duas janelas** (uma normal e uma anônima) para simular dois usuários:

1. Janela A: **Criar conta** como **Monitor**, marque as disciplinas que atende.
2. Janela B: **Criar conta** como **Aluno**, escolha a disciplina, clique em **Conversar** no monitor e envie uma mensagem.
3. Janela A: a conversa aparece na lista com o contador de não lidas. Abra e responda. A mensagem chega na janela B **sem recarregar**.
4. Entre nas **salas de estudo** com as duas contas e converse no grupo.
5. Teste o histórico: envie mais de 30 mensagens, saia e abra a conversa de novo e use **Carregar mensagens anteriores**.

## 7. Publicar no GitHub Pages (opcional)

1. No repositório: **Settings → Pages**, escolha a branch `main` e a pasta `/ (root)`.
2. O app ficará em `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/app/`.
3. No Firebase, em **Authentication → Configurações → Domínios autorizados**, adicione `SEU-USUARIO.github.io`. Sem isso, o login não funciona no site publicado.

## 8. Emulador local (opcional, avançado)

O `firebase.json` já traz a configuração do **Firebase Emulator Suite** (Auth na porta 9099, Realtime Database na 9000 e interface na 4000). Com o [Firebase CLI](https://firebase.google.com/docs/cli) instalado:

```bash
firebase emulators:start --only auth,database --project demo-monitoraai
# abra http://localhost:8000/app/?emulator
```

Com o parâmetro `?emulator`, o app usa o emulador em vez do projeto real. Os dados iniciais (`seed.json`) precisam ser adicionados manualmente na interface do emulador (porta 4000).

## Mapa: PRD x código

| Item do PRD | Onde está |
|---|---|
| Cadastro e login (RF01–RF03) | `app/index.html` (Firebase Authentication) |
| Disciplinas do monitor e busca (RF04–RF05) | `users`, `subjects`, `subjectTutors` |
| Conversa direta sem duplicidade (RF06–RF07) | `directConversations` + regra `!data.exists()` |
| Envio de mensagens (RF08) | `update()` atômico em vários caminhos |
| Histórico paginado (RF09–RF10) | `limitToLast(30)` e `endBefore(chave)` |
| Lista de conversas (RF11) | `userConversations` + `lastMessageAt` |
| Mensagens não lidas (RF12) | `lastReadKey` + `startAfter` |
| Salas de estudo (RF13) | conversas `room_<disciplina>` |
| Controle de acesso (RF14) | `firebase/database.rules.json` |
| Tempo real | `onChildAdded` e `onValue` |
