# Guia de Configuracao

[Voltar ao indice](./README.md) | [Anterior: Fluxo de Dados](./05-fluxo-de-dados.md) | [Proximo: Conformidade e Etica](./07-conformidade-e-etica.md)

## Requisitos minimos

- Windows, Linux ou macOS
- Python 3.11+
- Node.js 18+
- Navegador moderno

## Estrutura esperada

- `backend/` com dependencias Python instaladas
- `frontend/` com servidor estatico local
- scripts de inicializacao na raiz (`start-liz.cmd`, `local-start.ps1`)

## Variaveis de ambiente (alto nivel)

Configurar no backend:

- ambiente (`APP_ENV`)
- segredo de token da aplicacao
- chave de integracao do provedor de IA
- configuracoes de CORS e hosts confiaveis
- habilitacao de docs em ambiente local

> Importante: nunca commitar credenciais ou segredos.

## Subida local recomendada (Windows)

Na raiz do projeto:

```bat
start-liz.cmd
```

Esse comando dispara `local-start.ps1` e tenta subir:

- Frontend em `http://127.0.0.1:5500`
- Backend em `http://127.0.0.1:8000`

## Subida local manual

### Backend

```bash
cd backend
python -m pip install -r requirements.txt
python -m uvicorn app.main:app --host 127.0.0.1 --port 8000
```

### Frontend

```bash
node frontend/scripts/serve-static.js
```

## Validacao inicial

1. Abrir `http://127.0.0.1:5500`.
2. Verificar health da API em `http://127.0.0.1:8000/health/live`.
3. Testar login/cadastro.
4. Enviar mensagem no chat normal.
5. Testar stream de chat.
6. Abrir historico, perfil, atividade e configuracoes.

## Checklist de nao-regressao

- tema e enfase aplicam sem quebrar layout;
- modais abrem/fecham sem overflow visual;
- historico carrega e troca conversa;
- endpoints protegidos rejeitam token invalido;
- fallback de IA nao quebra a UX.

## Dicas de troubleshooting

- erro 401: token ausente/invalido;
- erro 422: payload invalido;
- erro 502/500: falha em servico interno ou provedor externo;
- front sem conectar: confirmar porta e CORS do backend.

## Navegacao

[Proximo: Conformidade e Etica](./07-conformidade-e-etica.md)
