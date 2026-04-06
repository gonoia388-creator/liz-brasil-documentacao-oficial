# Integracao com a IA

[Voltar ao indice](./README.md) | [Anterior: Arquitetura do Sistema](./02-arquitetura-do-sistema.md) | [Proximo: Dicionario de Arquivos](./04-dicionario-de-arquivos.md)

## Objetivo desta camada

A camada de IA transforma uma mensagem do usuario em resposta assistida, respeitando o modelo selecionado e o contexto da conversa.

## Modelos suportados no codigo atual

- `mini`
- `2.3`
- `2.5`

A selecao de modelo chega no backend via payload de chat e e normalizada antes da chamada externa.

## Endpoints de chat

### 1) Resposta tradicional

`POST /api/v1/chat/messages`

- salva mensagem do usuario;
- gera resposta do assistente;
- persiste a resposta;
- retorna `user_message` e `assistant_message`.

### 2) Resposta em streaming

`POST /api/v1/chat/messages/stream`

- retorna `application/x-ndjson`;
- eventos: `meta`, `chunk`, `done`;
- permite renderizacao progressiva no frontend.

## Estrutura do payload de entrada

Campos principais:

- `message` (obrigatorio)
- `conversation_id` (opcional)
- `attachments` (lista)
- `model` (`mini`, `2.3`, `2.5`)

Validacoes relevantes:

- mensagem vazia e rejeitada;
- `conversation_id` passa por validacao;
- anexos passam por normalizacao;
- campos extras nao permitidos.

## Fallback operacional

Quando a IA externa nao responde, o sistema retorna mensagem de fallback controlada. Isso evita quebra da UX e preserva previsibilidade para o usuario.

## Rate limit e protecao

Antes de processar chat, o backend aplica limite de requisicoes por janela de tempo para reduzir abuso.

## Integracao no frontend

- `frontend/src/js/chat.js`: fluxo de envio e renderizacao;
- `frontend/src/js/api.js`: chamadas para endpoint tradicional e stream;
- `frontend/src/js/markdown.js`: render de conteudo estruturado (incluindo blocos de codigo).

## Pontos de evolucao recomendados

1. melhorar tratamento de timeout e retries.
2. adicionar telemetria de latencia por modelo.
3. versionar contrato de stream para compatibilidade futura.
4. separar claramente resposta final de mensagens de status internas.

## Navegacao

[Proximo: Dicionario de Arquivos](./04-dicionario-de-arquivos.md)
