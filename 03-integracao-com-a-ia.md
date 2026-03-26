# Integração com a IA

[Voltar ao índice](./README.md) | [Anterior: Arquitetura do Sistema](./02-arquitetura-do-sistema.md) | [Próximo: Dicionário de Arquivos](./04-dicionario-de-arquivos.md)

## Visão geral

A Liz organiza sua experiência de IA por meio de modos internos, personas e instruções contextuais. O sistema combina identidade da assistente, contexto recente e objetivo da interação para produzir respostas coerentes com a proposta do produto.

## Núcleo de interação

O serviço interno de orquestração atua como um núcleo de coordenação entre a interface principal e os modos internos da Liz. Em termos funcionais, ele:

- seleciona o modo apropriado
- encaminha a mensagem do usuário
- organiza o contexto da interação
- devolve a resposta para a camada visual

## Modos internos da Liz

Os módulos internos encapsulados representam variações da experiência da Liz. Esses módulos permitem separar comportamentos por perfil de uso, profundidade de resposta e recursos especializados.

Exemplos de modos observáveis:

- modo principal
- modo compacto
- modo visual

## Construção do contexto

O comportamento da Liz é composto em camadas:

1. identidade-base da assistente
2. instruções contextuais do fluxo atual
3. histórico recente de conversa
4. ajustes de modo e experiência

Esse modelo favorece consistência sem perder adaptação ao uso real.

## Identidade de resposta

No projeto, a Liz é orientada para responder com:

- clareza
- equilíbrio entre profundidade e objetividade
- foco em utilidade prática
- linguagem acolhedora
- coerência com o português do Brasil

## Processamento complementar

Em fluxos mais longos ou mais sensíveis, a aplicação pode acionar rotinas internas de apoio para manter estabilidade, continuidade e segurança funcional.

## Exemplo conceitual de uso

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
