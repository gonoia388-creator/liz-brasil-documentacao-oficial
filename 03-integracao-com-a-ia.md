# Integração com a IA

[Voltar ao índice](./README.md) | [Anterior: Arquitetura do Sistema](./02-arquitetura-do-sistema.md) | [Próximo: Dicionário de Arquivos](./04-dicionario-de-arquivos.md)

## Visão geral

A Liz integra a camada de IA por meio de personas especializadas e de uma camada serverless voltada a operações controladas. O sistema trabalha com instruções de identidade, contexto da conversa, modo ativo e histórico recente.

## Caminho principal de integração

### Bridge no navegador

O arquivo `bin/liz-sdk.js` funciona como um coordenador entre a aplicação principal e as personas. Ele:

- instancia a persona adequada
- envia mensagens e contexto
- recebe eventos de resposta
- devolve o resultado para a interface principal

### Personas especializadas

As personas HTML em `bin/liz/` carregam identidade, comportamento e parâmetros próprios. Elas representam modos especializados da Liz, como:

- Liz principal
- Liz Mini
- Liz Imagina

## Configuração do comportamento

O comportamento da IA é montado em camadas:

1. identidade-base da persona
2. instruções adicionadas pela aplicação
3. histórico recente da conversa
4. ajustes de modo, plano e contexto de uso

Essa composição permite que a Liz responda com consistência sem perder adaptação ao cenário atual do usuário.

## Prompting e identidade

No código, a identidade da Liz é orientada por regras como:

- clareza
- profundidade equilibrada
- objetividade
- foco em resolver a necessidade do usuário
- manutenção de tom humano e acolhedor

## Processamento assíncrono

Quando necessário, a aplicação utiliza uma função serverless de processamento para tarefas de resposta em segundo plano. Isso ajuda a manter a experiência estável mesmo em operações mais demoradas.

## Base de conhecimento

Nesta versão documental, a Liz é descrita como uma aplicação orientada por personas, contexto e memória recente de conversa.

Não há, neste material, detalhamento de mecanismos internos de armazenamento ou de plataformas externas específicas. O foco está na experiência funcional da IA e em como a aplicação organiza a interação com o usuário.

## Exemplo conceitual de chamada

```js
const reply = await window.liz.chat({
  message: userMessage,
  persona: activePersona,
  customPrompt: currentInstructions,
  history: conversationHistory
})
```

## Navegação

[Próximo: Dicionário de Arquivos](./04-dicionario-de-arquivos.md)
