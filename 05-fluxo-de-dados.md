# Fluxo de Dados

[Voltar ao indice](./README.md) | [Anterior: Dicionario de Arquivos](./04-dicionario-de-arquivos.md) | [Proximo: Guia de Configuracao](./06-guia-de-configuracao.md)

## 1. Fluxo de autenticacao

1. Usuario envia credenciais via `login.html`.
2. Front chama `POST /api/v1/auth/login`.
3. Backend valida payload e autentica usuario.
4. Front recebe bundle de tokens e dados do usuario.
5. Sessao e aplicada no estado da aplicacao.

## 2. Fluxo de envio de mensagem (nao-stream)

1. Usuario digita no input principal.
2. `chat.js` monta payload (`message`, `conversation_id`, `attachments`, `model`).
3. `api.js` chama `POST /api/v1/chat/messages`.
4. Backend aplica auth e rate limit.
5. Backend persiste mensagem do usuario.
6. Backend solicita resposta no servico de IA.
7. Backend persiste resposta do assistente.
8. Front renderiza as duas mensagens no chat.

## 3. Fluxo de envio de mensagem (stream)

1. Front chama `POST /api/v1/chat/messages/stream`.
2. Backend devolve NDJSON com eventos.
3. Front consome eventos em tempo real:
   - `meta`: ids de controle.
   - `chunk`: texto parcial acumulado.
   - `done`: mensagens finais persistidas.
4. Interface atualiza resposta progressivamente.

## 4. Fluxo de historico

1. Front seleciona conversa no painel lateral.
2. Chama `GET /api/v1/chat/history` com `conversation_id` e `limit`.
3. Backend valida ownership e retorna itens.
4. Front reidrata a timeline do chat.

## 5. Fluxo de perfil

1. Usuario abre modal de perfil.
2. Front chama `GET /api/v1/users/me` para carga inicial.
3. Usuario altera display name, username, avatar.
4. Front chama `PATCH /api/v1/users/me`.
5. Backend valida e persiste.
6. Front atualiza avatar e nome na UI.

## 6. Fluxo de atividade

1. Front abre modal de atividade.
2. Chama `GET /api/v1/users/me/activity?months=N`.
3. Backend calcula serie mensal e total.
4. Front monta grafico/lista de meses.

## 7. Fluxo de configuracoes

1. Front carrega preferencias locais no bootstrap.
2. Usuario altera tema, enfase, idioma e linguagem falada.
3. Front aplica imediatamente na interface.
4. Front persiste no navegador (MVP).
5. Quando habilitado, pode sincronizar via `GET|PUT /api/v1/settings`.

## Fluxo resumido (chat)

```text
UI -> api.js -> /api/v1/chat/messages -> controller -> chat_service -> ai_service -> resposta -> UI
```

## Controles de seguranca no caminho

- autenticacao obrigatoria nas rotas protegidas;
- validacao de schema e campos extras proibidos;
- limite de taxa por usuario;
- validacao de ownership de conversa;
- tratamento padronizado de erro com request id.

## Navegacao

[Proximo: Guia de Configuracao](./06-guia-de-configuracao.md)
