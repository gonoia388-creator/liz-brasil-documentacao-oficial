# Conformidade e Etica

[Voltar ao indice](./README.md) | [Anterior: Guia de Configuracao](./06-guia-de-configuracao.md)

## Diretrizes de conformidade

A Liz Brasil adota um conjunto de praticas para manter seguranca funcional, previsibilidade operacional e respeito ao usuario.

## Controles tecnicos observaveis

### 1. Validacao de entrada

- schemas com restricao de tipos e tamanhos;
- campos extras proibidos em requests sensiveis;
- normalizacao de email, username, avatar e mensagem.

### 2. Controle de acesso

- rotas protegidas exigem autenticacao;
- operacoes de perfil e historico vinculadas ao usuario autenticado;
- ownership de conversa validado antes de leitura/escrita.

### 3. Reducao de abuso

- limitacao de taxa no fluxo de chat;
- bloqueio de payloads invalidos;
- resposta controlada em cenarios de erro.

### 4. Tratamento de erro seguro

- erros com formato padronizado;
- inclusao de request id para rastreabilidade;
- mensagens sem vazamento de detalhes sensiveis.

### 5. Higiene de segredos

- credenciais devem ficar em variaveis de ambiente;
- segredos nao devem ser versionados;
- rotacao obrigatoria em caso de exposicao.

## Etica de produto

A Liz deve responder com:

- clareza e utilidade pratica;
- linguagem respeitosa e acessivel;
- neutralidade em situacoes sensiveis;
- transparencia sobre limites tecnicos quando necessario.

## Politica de comunicacao

1. Nao inventar acesso que nao existe.
2. Nao ocultar falhas criticas.
3. Priorizar seguranca sobre conveniencia quando houver conflito.
4. Preservar contexto sem expor dados indevidos.

## Risco e responsabilidade

Toda alteracao em auth, chat, perfil e settings deve passar por:

- validacao tecnica;
- revisao de impacto front-back;
- checklist minimo de seguranca;
- documentacao da mudanca.

## Conclusao

A conformidade da Liz Brasil depende de disciplina operacional continua: contrato estavel, validacao forte, manejo correto de segredos e evolucao de UX sem comprometer seguranca.
