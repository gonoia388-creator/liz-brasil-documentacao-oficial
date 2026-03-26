# Conformidade e Ética

[Voltar ao índice](./README.md) | [Anterior: Guia de Configuração](./06-guia-de-configuracao.md)

## Direção de conformidade

A Liz foi pensada para operar com foco em segurança funcional, proteção do usuário e previsibilidade de comportamento. Nesta edição documental, a conformidade é descrita sob a ótica da aplicação, da experiência e das camadas de proteção observáveis no código.

## Práticas observáveis

### 1. Minimização de exposição

A aplicação separa frontend e operações sensíveis, reduzindo a necessidade de lógica crítica diretamente no navegador.

### 2. Validação de entrada

As funções serverless utilizam validação de payload para rejeitar estruturas inválidas, incompletas ou abusivas.

### 3. Proteção contra abuso

O backend aplica controles de uso para reduzir spam, automação agressiva e consumo indevido de recursos.

### 4. Tratamento seguro de erros

O fluxo busca evitar exposição indevida de detalhes internos, priorizando respostas controladas ao cliente.

## Ética de produto

O comportamento da Liz é orientado para:

- acolhimento
- clareza
- respeito ao contexto do usuário
- linguagem acessível
- foco em ajuda real, sem agressividade ou frieza desnecessária

## Tom de voz

O tom de voz é influenciado pelas personas e pelas instruções contextuais do sistema. Na prática, isso sustenta uma identidade que busca:

- responder de forma humana
- organizar ideias com clareza
- evitar excesso de formalismo quando não for útil
- manter utilidade prática acima de ornamentação

## Conclusão

Esta documentação registra uma Liz orientada por:

- experiência amigável
- proteção funcional
- modularidade técnica
- integração consistente com IA

Ela foi organizada para servir como base oficial de leitura da aplicação sem expor detalhes de infraestrutura fora do escopo solicitado.
