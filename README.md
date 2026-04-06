# Liz Brasil - Documentacao Tecnica Oficial

Este diretorio concentra a documentacao institucional da Liz Brasil em formato Markdown, com leitura sequencial e foco tecnico.

## Resumo executivo (versao curta)

A documentacao descreve a plataforma em 7 capitulos:

1. **Visao geral do produto**: objetivo, principios e estrutura macro.
2. **Arquitetura do sistema**: camadas, responsabilidades e modularidade.
3. **Integracao com IA**: como o contexto e montado e como a resposta e devolvida.
4. **Dicionario de arquivos**: mapa dos arquivos e da funcao de cada modulo.
5. **Fluxo de dados**: caminho completo da mensagem do usuario.
6. **Guia de configuracao**: requisitos e operacao local em alto nivel.
7. **Conformidade e etica**: seguranca funcional, limites e direcao de produto.

Em resumo: o conjunto serve para onboarding tecnico, auditoria funcional e manutencao orientada por responsabilidades.

## Visao detalhada do documento (capitulo por capitulo)

### 01 - Visao Geral
Arquivo: `01-visao-geral.md`

Cobertura:

- proposito da Liz Brasil como produto conversacional;
- direcao de experiencia (clareza, acolhimento e utilidade pratica);
- principios observaveis no codigo;
- estrutura macro do repositorio.

Quando ler: inicio de projeto, alinhamento de produto e entendimento do escopo.

### 02 - Arquitetura do Sistema
Arquivo: `02-arquitetura-do-sistema.md`

Cobertura:

- classificacao arquitetural (hibrida e modular);
- camadas da solucao (experiencia, orquestracao, nucleo conversacional e servicos internos);
- caracteristicas de modularidade, escalabilidade operacional e continuidade de produto.

Quando ler: planejamento tecnico, refatoracao e definicao de fronteiras entre modulos.

### 03 - Integracao com a IA
Arquivo: `03-integracao-com-a-ia.md`

Cobertura:

- fluxo de composicao de contexto;
- selecao de modo/persona;
- identidade de resposta e comportamento esperado da assistente;
- processamento complementar para cenarios mais longos/sensiveis.

Quando ler: ajustes de qualidade da resposta, tuning de prompt e evolucao do comportamento.

### 04 - Dicionario de Arquivos
Arquivo: `04-dicionario-de-arquivos.md`

Cobertura:

- tabela de arquivos/modulos mais relevantes;
- responsabilidade principal de cada item;
- dependencias-chave para manutencao.

Quando ler: navegacao no repositorio, onboarding de dev e analise de impacto.

### 05 - Fluxo de Dados
Arquivo: `05-fluxo-de-dados.md`

Cobertura:

- caminho ponta a ponta da mensagem do usuario;
- etapas de orquestracao e retorno para interface;
- pontos de protecao funcional (validacao, controle de abuso, tratamento de erro);
- fluxo assincrono para operacoes pesadas.

Quando ler: troubleshooting, observabilidade e desenho de novos fluxos.

### 06 - Guia de Configuracao
Arquivo: `06-guia-de-configuracao.md`

Cobertura:

- requisitos minimos de ambiente;
- recomendacoes para execucao local por HTTP;
- checklist inicial de validacao funcional.

Quando ler: setup local, homologacao e preparo de ambiente.

### 07 - Conformidade e Etica
Arquivo: `07-conformidade-e-etica.md`

Cobertura:

- direcao de conformidade da aplicacao;
- praticas de seguranca observaveis;
- principios eticos e tom de voz do produto;
- limites de exposicao tecnica no material publico.

Quando ler: revisao institucional, governanca e alinhamento de comunicacao.

## Indice de navegacao

1. [Visao Geral](./01-visao-geral.md)
2. [Arquitetura do Sistema](./02-arquitetura-do-sistema.md)
3. [Integracao com a IA](./03-integracao-com-a-ia.md)
4. [Dicionario de Arquivos](./04-dicionario-de-arquivos.md)
5. [Fluxo de Dados](./05-fluxo-de-dados.md)
6. [Guia de Configuracao](./06-guia-de-configuracao.md)
7. [Conformidade e Etica](./07-conformidade-e-etica.md)

## Como usar este pacote de documentacao

### Leitura recomendada para dev novo

1. `01-visao-geral.md`
2. `02-arquitetura-do-sistema.md`
3. `04-dicionario-de-arquivos.md`
4. `05-fluxo-de-dados.md`

### Leitura recomendada para revisao de seguranca

1. `05-fluxo-de-dados.md`
2. `06-guia-de-configuracao.md`
3. `07-conformidade-e-etica.md`

### Leitura recomendada para produto/UX

1. `01-visao-geral.md`
2. `03-integracao-com-a-ia.md`
3. `07-conformidade-e-etica.md`

## Limites desta documentacao

Este conjunto e publico-controlado. Portanto, ele **nao** deve incluir:

- segredos operacionais;
- credenciais;
- detalhes internos sensiveis de infraestrutura;
- dados pessoais reais.

## Politica de atualizacao

Ao alterar fluxos relevantes no codigo (auth, chat, imagem, historico, configuracoes):

1. atualizar o capitulo impactado;
2. atualizar este `README.md` se houver mudanca estrutural;
3. revisar consistencia de termos e links;
4. validar se o texto continua sem exposicao sensivel.

---

Se voce quer um ponto de partida rapido, leia `01`, `02` e `05`.
