# Guia de Configuração

[Voltar ao índice](./README.md) | [Anterior: Fluxo de Dados](./05-fluxo-de-dados.md) | [Próximo: Conformidade e Ética](./07-conformidade-e-etica.md)

## Requisitos

- navegador moderno
- ambiente para servir arquivos por `http://localhost` ou domínio real
- Node.js para serviços auxiliares quando aplicável
- Supabase CLI para funções serverless

## Observação importante

Para uso correto da sessão e de recursos autenticados, a aplicação não deve ser aberta por `file://`. O recomendado é servir o projeto por HTTP local ou ambiente de homologação.

## Variáveis de ambiente

As variáveis exatas dependem do ambiente em execução, mas o projeto utiliza grupos como:

- URL pública da aplicação
- chave pública de autenticação do frontend
- segredos server-side de funções
- chaves de recursos de IA
- origens autorizadas para CORS
- chaves de notificação web

## Exemplo de `.env`

```env
SUPABASE_URL=https://seu-projeto.supabase.co
SUPABASE_ANON_KEY=sua_chave_publica
SUPABASE_SERVICE_ROLE_KEY=seu_segredo_server_side
ALLOWED_ORIGINS=https://seu-dominio.com,https://app.seu-dominio.com
LIZ_WORKER_UPSTREAM_URL=https://seu-endpoint-de-processamento
LIZ_WORKER_API_KEY=seu_token_interno
POLLINATIONS_API_KEY=sua_chave_de_imagem
VAPID_PUBLIC_KEY=sua_chave_publica_push
VAPID_PRIVATE_KEY=sua_chave_privada_push
VAPID_CONTACT_EMAIL=mailto:contato@seudominio.com
```

## Instalação básica

### Servir o frontend

```bash
npx serve .
```

### Subir funções locais

```bash
supabase start
supabase functions serve
```

### Serviço auxiliar Node

```bash
cd multi-chat/server
npm install
npm run dev
```

## Checklist inicial

- configurar variáveis de ambiente
- servir o projeto por HTTP
- validar autenticação no navegador
- validar chamadas das funções serverless
- validar fluxo de chat e recursos visuais

## Navegação

[Próximo: Conformidade e Ética](./07-conformidade-e-etica.md)
