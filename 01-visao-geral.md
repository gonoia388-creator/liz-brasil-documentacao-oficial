# Visao Geral

[Voltar ao indice](./README.md) | [Proximo: Arquitetura do Sistema](./02-arquitetura-do-sistema.md)

## Proposito

A Liz Brasil e uma aplicacao de assistencia por IA com foco em produtividade, clareza e fluxo continuo de trabalho. O produto combina chat, historico, configuracoes de experiencia, modos de modelo e recursos visuais em uma interface unica para desktop e mobile.

## Objetivos do produto

- entregar resposta util com latencia previsivel;
- manter UX consistente em tema escuro/claro e variacoes de enfase;
- permitir evolucao modular sem quebrar o front;
- oferecer base segura para autenticacao, perfil e preferencias;
- suportar resposta padrao e resposta em streaming.

## Estado atual (codigo)

- Frontend: HTML, CSS e JavaScript modular (sem framework pesado).
- Backend: Python + FastAPI com rotas versionadas em `/api/v1`.
- Chat: envio tradicional e modo stream (`/chat/messages/stream`).
- Persistencia de UI: configuracoes gerais no navegador (MVP local).
- Seguranca: validacao de schema, middlewares, cabecalhos e controle de acesso por token.

## Principios tecnicos

1. Separacao de responsabilidades por camada.
2. Contrato estavel entre frontend e backend.
3. Fallback seguro quando o provedor de IA estiver indisponivel.
4. Protecao contra entrada invalida e abuso de requests.
5. Observabilidade basica por logs e health checks.

## Estrutura macro do repositorio

- `frontend/`: interface, estilos e logica de UX.
- `backend/`: API, regras de negocio, autenticacao e servicos.
- `docs/`: documentacao operacional interna do projeto.
- `liz-brasil-documentacao-oficial-main/`: pacote de documentacao institucional.

## O que esta fora deste capitulo

Este documento nao entra em detalhes de payload, contratos de cada rota e procedimentos de deploy. Esses pontos estao distribuidos nos capitulos seguintes.

## Navegacao

[Proximo: Arquitetura do Sistema](./02-arquitetura-do-sistema.md)
