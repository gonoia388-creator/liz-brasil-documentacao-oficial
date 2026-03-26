# Dicionário de Arquivos

[Voltar ao índice](./README.md) | [Anterior: Integração com a IA](./03-integracao-com-a-ia.md) | [Próximo: Fluxo de Dados](./05-fluxo-de-dados.md)

## Critério desta seção

Esta tabela cobre os arquivos mais relevantes da aplicação e omite detalhes de implementação ligados a infraestrutura sensível fora do escopo desta edição.

| Nome do Arquivo | Responsabilidade Principal | Dependências Chave |
|---|---|---|
| `index.html` | Entrada principal da aplicação no navegador | `js/script.js`, `js/config.js`, `components/`, `css/` |
| `app.html` | Variante operacional da interface principal | `js/script.js`, `js/config.js`, `css/` |
| `convite.html` | Experiência de convite e aquisição | scripts de interface, componentes visuais |
| `sw.js` | Service worker para suporte operacional e notificações | APIs do navegador |
| `js/config.js` | Configuração pública necessária ao frontend | cliente Supabase no navegador |
| `js/script.js` | Orquestração principal da aplicação | Supabase JS, `window.liz`, módulos auxiliares |
| `js/images.js` | Fluxo de recursos visuais e galeria | UI de imagens, chamadas seguras do app |
| `js/turso.js` | Bridge cliente para operações seguras do app | `database-proxy`, Supabase Functions |
| `bin/liz-sdk.js` | SDK que conecta app e personas | `postMessage`, iframes, runtime web |
| `bin/liz/liz2.0.html` | Persona principal da Liz | fetch, bridge do SDK |
| `bin/liz/liz mini.html` | Persona compacta | fetch, bridge do SDK |
| `bin/liz/Liz imagina.html` | Persona visual para recursos de imagem | runtime web, image worker |
| `components/sidebar.html` | Estrutura da navegação lateral | estilos e scripts da interface |
| `components/input-area.html` | Área de entrada da mensagem | eventos de UI |
| `components/persona.html` | Estrutura visual de seleção de persona | scripts da interface |
| `css/staly.css` | Estilo global principal | layout base da aplicação |
| `css/sidebar.css` | Estilo da barra lateral e atalhos | componentes da sidebar |
| `css/images.css` | Estilo dos recursos de imagem | galeria e painéis visuais |
| `css/settings.css` | Estilo da área de configurações | painel de ajustes |
| `css/modes.css` | Estilo dos modos e personas | cartões e seletores de modo |
| `Liz Comunidade/community.html` | Interface da comunidade | `community.js`, estilos |
| `Liz Comunidade/community.js` | Lógica de interação da comunidade | cliente seguro da comunidade |
| `Liz Comunidade/banco de dados/comunidade.js` | Camada de operações seguras da comunidade | `window.secureTurso` |
| `loguin/index.html` | Tela de acesso do usuário | Supabase Auth, scripts de login |
| `loguin/login.js` | Lógica de autenticação no cliente | Supabase Auth |
| `loguin/register.html` | Tela de cadastro | Supabase Auth, UI |
| `loguin/register.js` | Fluxo de criação de conta no cliente | Supabase Auth, perfil do usuário |
| `assinaturas/assinaturas.js` | Fluxo visual do painel de assinatura | UI, sessão e plano do usuário |
| `supabase/functions/chat-worker/index.ts` | Processamento assíncrono de mensagens | Deno, validação de payload, autenticação |
| `supabase/functions/image-proxy/index.ts` | Operações seguras de imagem | Deno, validação de payload, controle de uso |
| `supabase/functions/database-proxy/index.ts` | Operações fechadas do app | Deno, validação de payload, regras de acesso |
| `supabase/functions/_shared/security.ts` | Utilitários compartilhados de segurança | autenticação, CORS, rate limit |

## Leitura recomendada

Para entender a aplicação de ponta a ponta, a sequência mais eficiente é:

1. `index.html`
2. `js/script.js`
3. `bin/liz-sdk.js`
4. `bin/liz/*.html`
5. `supabase/functions/*`

## Navegação

[Próximo: Fluxo de Dados](./05-fluxo-de-dados.md)
