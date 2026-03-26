# Arquitetura do Sistema

[Voltar ao índice](./README.md) | [Anterior: Visão Geral](./01-visao-geral.md) | [Próximo: Integração com a IA](./03-integracao-com-a-ia.md)

## Classificação arquitetural

A Liz Brasil segue uma arquitetura híbrida, composta por:

- frontend web estático com comportamento de aplicação rica
- orquestração cliente em JavaScript
- funções serverless para operações seguras e processamento assíncrono
- personas especializadas executadas por bridge no navegador

Essa topologia não é um monólito puro nem um conjunto clássico de microsserviços. A melhor definição para o estado atual do sistema é:

**Frontend Web + Bridge de Personas + Camada Serverless**

## Camadas principais

### 1. Camada de experiência

Responsável pela interface que o usuário vê e utiliza no navegador.

Arquivos centrais:

- `index.html`
- `app.html`
- `css/`
- `components/`

### 2. Camada de orquestração

Responsável por sessão, eventos da interface, envio de mensagens, atualização de estado e integração com os recursos da Liz.

Arquivo central:

- `js/script.js`

### 3. Camada de personas

Responsável por encapsular comportamentos específicos da Liz, como persona principal, modo compacto e recursos visuais.

Arquivos centrais:

- `bin/liz-sdk.js`
- `bin/liz/liz2.0.html`
- `bin/liz/liz mini.html`
- `bin/liz/Liz imagina.html`

### 4. Camada serverless

Responsável por aplicar regras de segurança, validação, controle de abuso e operações assíncronas.

Arquivos centrais:

- `supabase/functions/chat-worker/index.ts`
- `supabase/functions/image-proxy/index.ts`
- `supabase/functions/database-proxy/index.ts`
- `supabase/functions/_shared/security.ts`

## Características arquiteturais

### Modularidade

A aplicação é separada por domínio funcional. Chat, imagens, comunidade, autenticação e assinaturas possuem blocos próprios de código e interface.

### Escalabilidade operacional

As rotas serverless permitem crescer por função, reduzindo acoplamento entre a interface e tarefas mais sensíveis.

### Evolução incremental

O sistema permite introduzir melhorias sem reescrever toda a base, o que favorece manutenção contínua.

## Resumo técnico

A Liz foi estruturada para equilibrar:

- experiência direta no navegador
- flexibilidade de personas
- processamento remoto controlado
- proteção operacional para recursos mais sensíveis

## Navegação

[Próximo: Integração com a IA](./03-integracao-com-a-ia.md)
