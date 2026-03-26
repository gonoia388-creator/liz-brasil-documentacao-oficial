# Visão Geral

[Voltar ao índice](./README.md) | [Próximo: Arquitetura do Sistema](./02-arquitetura-do-sistema.md)

## Propósito

A Liz Brasil é uma aplicação de inteligência artificial voltada para interação em linguagem natural com foco em clareza, acolhimento e utilidade prática. A experiência combina interface web, personas especializadas e uma camada serverless para tarefas operacionais e de segurança.

## Direção do produto

A aplicação foi estruturada para:

- oferecer conversas fluidas em português do Brasil
- adaptar a resposta conforme modo, contexto e persona
- manter uma experiência responsiva em desktop e mobile
- sustentar recursos como geração de imagens, modos especializados e processamento assíncrono

## Princípios observados no código

- separação entre interface, lógica de orquestração e serviços serverless
- personalização da IA por persona e instruções contextuais
- proteção por autenticação, validação de payload e controle de abuso
- experiência de uso pensada para continuidade, clareza e tom humano

## Estrutura macro

O repositório é organizado em blocos principais:

- interface principal em HTML, CSS e JavaScript
- SDK e personas da Liz em `bin/`
- funções serverless em `supabase/functions/`
- módulos auxiliares como comunidade, imagens, login e service worker

## Navegação

[Próximo: Arquitetura do Sistema](./02-arquitetura-do-sistema.md)
