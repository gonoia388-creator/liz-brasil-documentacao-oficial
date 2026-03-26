# Fluxo de Dados

[Voltar ao índice](./README.md) | [Anterior: Dicionário de Arquivos](./04-dicionario-de-arquivos.md) | [Próximo: Guia de Configuração](./06-guia-de-configuracao.md)

## Caminho da mensagem do usuário

### Etapa 1. Entrada no navegador

O usuário digita uma mensagem na interface principal da Liz. O evento é capturado pela camada de interface e encaminhado para a lógica central da aplicação.

### Etapa 2. Orquestração local

`js/script.js` consolida:

- mensagem do usuário
- modo ativo
- persona selecionada
- contexto da sessão
- histórico recente

### Etapa 3. Preparação do contexto

A aplicação organiza o pacote de instruções que será enviado para a Liz:

- identidade base da persona
- instruções adicionais do modo atual
- histórico recente da conversa
- ajustes visuais e comportamentais

### Etapa 4. Encaminhamento para a bridge

O app chama o SDK da Liz, que seleciona a persona adequada e envia a requisição para a camada de IA.

### Etapa 5. Execução da persona

A persona processa o pedido, aplica sua configuração e inicia a obtenção da resposta.

### Etapa 6. Proteções de aplicação

Quando o fluxo passa por funções serverless, entram em cena mecanismos como:

- autenticação do usuário
- validação rígida de payload
- limitação de abuso por quota e rate limit
- checagem de origem permitida
- tratamento seguro de erros

### Etapa 7. Retorno ao frontend

A resposta é devolvida ao SDK e reenviada para a interface principal, que atualiza o chat em tempo real.

### Etapa 8. Atualização visual

O frontend renderiza:

- texto final
- estados de carregamento
- indicadores de modo ou persona
- ajustes de interface conforme o contexto

## Fluxo resumido

```text
Usuário -> Interface -> script.js -> liz-sdk.js -> Persona -> Função segura -> Resposta -> Interface
```

## Fluxo assíncrono

Em tarefas mais longas, a aplicação pode usar processamento assíncrono. Nesse caso:

1. a mensagem é enviada para uma função serverless
2. a função valida a requisição
3. o processamento continua em segundo plano
4. o resultado é devolvido depois para a interface

Esse modelo ajuda a preservar a experiência do usuário mesmo em operações mais pesadas.

## Navegação

[Próximo: Guia de Configuração](./06-guia-de-configuracao.md)
