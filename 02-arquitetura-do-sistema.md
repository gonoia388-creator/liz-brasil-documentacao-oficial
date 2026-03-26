# Arquitetura do Sistema

[Voltar ao índice](./README.md) | [Anterior: Visão Geral](./01-visao-geral.md) | [Próximo: Integração com a IA](./03-integracao-com-a-ia.md)

## Classificação arquitetural

A Liz Brasil segue uma arquitetura híbrida e modular, composta por:

- frontend web com experiência de aplicação rica
- camada de orquestração em JavaScript
- serviços internos de apoio à execução
- módulos especializados da Liz para diferentes modos de interação

Essa topologia prioriza separação de responsabilidades, evolução incremental e controle operacional.

## Camadas principais

### 1. Camada de experiência

Responsável pela interface visível ao usuário, navegação, painéis, interações e apresentação do conteúdo.

Arquivos centrais:

- `index.html`
- `app.html`
- `css/`
- `components/`

### 2. Camada de orquestração

Responsável por coordenar sessão, interface, mensagens, modos da Liz e atualização do estado da aplicação.

Arquivo central:

- `js/script.js`

### 3. Camada de núcleo conversacional

Responsável por encapsular modos internos da Liz e adaptar o comportamento da experiência conforme persona, contexto e objetivo.

Arquivos centrais:

- `sdk-interno/core`
- `modos/principal`
- `modos/compacto`
- `modos/visual`

### 4. Camada de serviços internos

Responsável por aplicar regras de execução, segurança funcional, validação e processamento complementar da aplicação.

Arquivos centrais:

- `functions/chat-worker`
- `functions/image-worker`
- `functions/app-gateway`
- `functions/security-core`

## Características arquiteturais

### Modularidade

A aplicação é dividida por domínios de experiência. Conversa, recursos visuais, comunidade, autenticação e assinatura possuem fronteiras próprias dentro do projeto.

### Escalabilidade operacional

As responsabilidades sensíveis e de maior custo operacional ficam desacopladas da interface principal, o que favorece manutenção e evolução do produto.

### Continuidade de produto

O desenho atual permite refinar comportamento, visual e lógica interna sem necessidade de reestruturação completa da aplicação.

## Resumo técnico

A Liz foi estruturada para equilibrar:

- experiência fluida no navegador
- identidade própria da assistente
- organização modular
- proteção operacional nas rotinas mais sensíveis

## Navegação

[Próximo: Integração com a IA](./03-integracao-com-a-ia.md)
