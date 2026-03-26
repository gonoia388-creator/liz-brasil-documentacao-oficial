# Guia de Configuração

[Voltar ao índice](./README.md) | [Anterior: Fluxo de Dados](./05-fluxo-de-dados.md) | [Próximo: Conformidade e Ética](./07-conformidade-e-etica.md)

## Requisitos

- navegador moderno
- ambiente local ou de homologação servido por HTTP
- Node.js para módulos auxiliares quando aplicável
- ferramentas internas de execução para os serviços da aplicação

## Observação importante

Para uso correto da sessão e dos recursos autenticados, a aplicação não deve ser aberta por `file://`. O recomendado é servir o projeto por HTTP local ou ambiente de homologação.

## Configuração operacional

Esta documentação pública descreve a configuração apenas em nível geral. Segredos, chaves, endpoints internos e parâmetros privados devem permanecer em documentação operacional restrita.

## Instalação básica

### Servir o frontend

```bash
npx serve .
```

### Serviço auxiliar Node

```bash
cd multi-chat/server
npm install
npm run dev
```

## Checklist inicial

- servir o projeto por HTTP
- validar autenticação no navegador
- validar fluxo principal da interface
- validar recursos conversacionais e visuais
- validar rotinas internas da aplicação no ambiente adequado

## Navegação

[Próximo: Conformidade e Ética](./07-conformidade-e-etica.md)
