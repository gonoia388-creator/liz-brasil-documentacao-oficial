# Dicionário de Arquivos

[Voltar ao índice](./README.md) | [Anterior: Integração com a IA](./03-integracao-com-a-ia.md) | [Próximo: Fluxo de Dados](./05-fluxo-de-dados.md)

## Critério desta seção

Esta tabela cobre os arquivos mais relevantes da aplicação em nível seguro de documentação pública. Nomes técnicos internos são preservados apenas quando ajudam a localizar o módulo no repositório.

| Nome do Arquivo | Responsabilidade Principal | Dependências Chave |
|---|---|---|
| `index.html` | Entrada principal da aplicação no navegador | `js/script.js`, `js/config.js`, `components/`, `css/` |
| `app.html` | Variante operacional da interface principal | `js/script.js`, `js/config.js`, `css/` |
| `convite.html` | Experiência de convite e aquisição | scripts de interface, componentes visuais |
| `sw.js` | Service worker para suporte operacional e notificações | APIs do navegador |
| `js/config.js` | Configurações públicas da aplicação | módulos do frontend |
| `js/script.js` | Orquestração principal da aplicação | `window.liz`, módulos auxiliares, interface |
| `js/images.js` | Fluxo dos recursos visuais e galeria | UI de imagens, camada de aplicação |
| `components/sidebar.html` | Estrutura da navegação lateral | estilos e scripts da interface |
| `components/input-area.html` | Área de entrada da mensagem | eventos de UI |
| `components/persona.html` | Estrutura visual de seleção de modo | scripts da interface |
| `css/staly.css` | Estilo global principal | layout base da aplicação |
| `css/sidebar.css` | Estilo da barra lateral e atalhos | componentes da sidebar |
| `css/images.css` | Estilo dos recursos visuais | galeria e painéis visuais |
| `css/settings.css` | Estilo da área de configurações | painel de ajustes |
| `css/modes.css` | Estilo dos modos da Liz | cartões e seletores de modo |
| `Liz Comunidade/community.html` | Interface da comunidade | `community.js`, estilos |
| `Liz Comunidade/community.js` | Lógica de interação da comunidade | módulos da comunidade |
| `Liz Comunidade/banco de dados/comunidade.js` | Camada interna de suporte da comunidade | rotinas protegidas da aplicação |
| `loguin/index.html` | Tela de acesso do usuário | scripts de login |
| `loguin/login.js` | Lógica de autenticação no cliente | camada de autenticação da aplicação |
| `loguin/register.html` | Tela de cadastro | interface e scripts de acesso |
| `loguin/register.js` | Fluxo de criação de conta no cliente | autenticação e perfil do usuário |
| `assinaturas/assinaturas.js` | Fluxo visual do painel de assinatura | interface, sessão e estado do usuário |
| `functions/chat-worker` | Processamento complementar de mensagens | validação, autenticação, rotinas internas |
| `functions/image-worker` | Processamento complementar visual | validação, controle de uso, rotinas internas |
| `functions/app-gateway` | Operações fechadas da aplicação | validação, regras de acesso |
| `functions/security-core` | Utilitários compartilhados de segurança | autenticação, origem permitida, controle de abuso |

## Leitura recomendada

Para entender a aplicação de ponta a ponta, a sequência mais eficiente é:

1. `index.html`
2. `js/script.js`
3. `functions/`

## Navegação

[Próximo: Fluxo de Dados](./05-fluxo-de-dados.md)
