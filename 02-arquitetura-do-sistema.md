# Arquitetura do Sistema

[Voltar ao indice](./README.md) | [Anterior: Visao Geral](./01-visao-geral.md) | [Proximo: Integracao com a IA](./03-integracao-com-a-ia.md)

## Visao arquitetural

A Liz Brasil adota arquitetura em camadas com fronteiras claras entre UX, API e servicos de negocio.

```text
Usuario -> Frontend (UI) -> API Client -> FastAPI -> Controllers -> Services -> Provedor externo
```

## Camadas principais

### 1. Camada de experiencia (Frontend)

Responsavel por navegacao, layout, chat, modais (perfil, atividade, configuracoes), historico e renderizacao de markdown/codigo.

Arquivos-chave:

- `frontend/public/index.html`
- `frontend/src/js/main.js`
- `frontend/src/js/ui.js`
- `frontend/src/js/chat.js`
- `frontend/src/js/auth.js`
- `frontend/src/js/api.js`
- `frontend/src/js/markdown.js`
- `frontend/src/styles/*.css`

### 2. Camada de API (FastAPI)

Responsavel por receber requests, validar payloads, autenticar usuario, aplicar regras de negocio e responder com contrato consistente.

Arquivos-chave:

- `backend/app/main.py`
- `backend/app/routes/*.py`
- `backend/app/controllers/*.py`
- `backend/app/schemas/*.py`

### 3. Camada de servicos

Responsavel por autenticao, chat, geracao de resposta, atividade e perfil.

Arquivos-chave:

- `backend/app/services/auth_service.py`
- `backend/app/services/chat_service.py`
- `backend/app/services/ai_service.py`
- `backend/app/services/user_service.py`
- `backend/app/services/activity_service.py`

### 4. Camada transversal de seguranca

Responsavel por validacoes, headers, rate limit, middleware de auth e utilitarios de seguranca.

Arquivos-chave:

- `backend/app/middlewares/auth_middleware.py`
- `backend/app/middlewares/log_middleware.py`
- `backend/app/utils/security.py`
- `backend/app/utils/validators.py`

## Rotas de alto nivel

- Auth: `/api/v1/auth/*`
- Usuario: `/api/v1/users/*`
- Chat: `/api/v1/chat/*`
- Configuracoes: `/api/v1/settings`
- Health: `/health/live` e `/health/ready`

## Decisoes de projeto importantes

1. **Schemas com validacao forte**: requests com campos extras sao rejeitados.
2. **Streaming opcional**: mesma experiencia de chat com endpoint dedicado para resposta progressiva.
3. **Modularidade**: UI e API evoluem em modulos, reduzindo risco de regressao.
4. **Fallback de IA**: sistema nao quebra se o provedor estiver fora.

## Riscos conhecidos

- Dependencia de provedores externos pode elevar latencia.
- Estado local no frontend requer cuidado ao sincronizar com backend.
- Alteracoes de contrato exigem validacao end-to-end.

## Navegacao

[Proximo: Integracao com a IA](./03-integracao-com-a-ia.md)
