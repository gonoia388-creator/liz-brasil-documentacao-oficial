# Dicionario de Arquivos

[Voltar ao indice](./README.md) | [Anterior: Integracao com a IA](./03-integracao-com-a-ia.md) | [Proximo: Fluxo de Dados](./05-fluxo-de-dados.md)

## Criterio desta secao

Mapa objetivo dos arquivos principais em uso no projeto atual, com foco em manutencao e impacto de mudanca.

## Frontend (principal)

| Arquivo | Responsabilidade |
|---|---|
| `frontend/public/index.html` | Estrutura principal da aplicacao web |
| `frontend/public/login.html` | Tela de autenticacao |
| `frontend/public/register.html` | Tela de cadastro |
| `frontend/src/js/main.js` | Bootstrap da aplicacao e inicializacao de modulos |
| `frontend/src/js/ui.js` | Estado de interface, navegacao, modais e interacoes visuais |
| `frontend/src/js/chat.js` | Fluxo de chat, historico, render e stream |
| `frontend/src/js/auth.js` | Sessao, login/logout, guardas de autenticacao |
| `frontend/src/js/api.js` | Cliente HTTP e camada de acesso a API |
| `frontend/src/js/markdown.js` | Parse/render de markdown e blocos de codigo |
| `frontend/src/js/help.js` | Fluxos da area de ajuda |
| `frontend/src/js/login.js` | Comportamento da pagina de login |
| `frontend/src/js/register.js` | Comportamento da pagina de cadastro |
| `frontend/src/styles/variables.css` | Tokens visuais (cores, espacamentos, tema) |
| `frontend/src/styles/layout.css` | Estrutura de layout e import do CSS base |
| `frontend/src/styles/components.css` | Componentes de UI (chat, modais, listas, etc.) |
| `frontend/src/styles/login.css` | Estilo da pagina de login |
| `frontend/src/styles/register.css` | Estilo da pagina de cadastro |

## Backend (principal)

| Arquivo | Responsabilidade |
|---|---|
| `backend/app/main.py` | Criacao da app FastAPI, middlewares, handlers globais e health checks |
| `backend/app/routes/auth.py` | Endpoints de cadastro, login, refresh e logout |
| `backend/app/routes/users.py` | Endpoints de perfil e atividade do usuario |
| `backend/app/routes/chat.py` | Endpoints de envio de mensagem, stream e historico |
| `backend/app/routes/settings.py` | Endpoints de leitura/escrita de configuracoes |
| `backend/app/controllers/*.py` | Adaptacao da rota para servicos |
| `backend/app/services/auth_service.py` | Regras de autenticacao e tokens |
| `backend/app/services/chat_service.py` | Regras de chat, persistencia e stream NDJSON |
| `backend/app/services/ai_service.py` | Integracao externa de IA e fallback |
| `backend/app/services/user_service.py` | Perfil do usuario |
| `backend/app/services/activity_service.py` | Estatisticas de atividade |
| `backend/app/schemas/*.py` | Contratos de request/response com Pydantic |
| `backend/app/middlewares/*.py` | Auth middleware, CORS e logs |
| `backend/app/utils/security.py` | Funcoes de seguranca, rate limit e suporte a chat |
| `backend/app/utils/validators.py` | Validadores de entrada |
| `backend/app/core/config.py` | Leitura de configuracoes por ambiente |

## Operacao local

| Arquivo | Responsabilidade |
|---|---|
| `start-liz.cmd` | Inicializacao local (wrapper) |
| `local-start.ps1` | Sobe frontend + backend e valida readiness |
| `stop-liz.cmd` | Encerramento local |
| `local-stop.ps1` | Para processos e limpa estado de execucao |

## Observacao de manutencao

Antes de alterar qualquer fluxo principal (auth, chat, perfil, settings), revisar este dicionario e validar impacto cruzado front-back.

## Navegacao

[Proximo: Fluxo de Dados](./05-fluxo-de-dados.md)
