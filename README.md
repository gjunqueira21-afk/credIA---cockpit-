# Credia — Cockpit CNAB 400

Site interno da **Credia Soluções** para leitura e análise de arquivos
**CNAB 400 Celcoin** (remessa e retorno) da carteira de crédito consignado.

Funciona 100% no navegador — nenhum arquivo é enviado para servidor; todo o
processamento acontece localmente no dispositivo. Otimizado para **desktop e celular**.

## Acesso

O site é protegido por senha.

- **Senha padrão:** `credia2026`

Após entrar, a sessão fica liberada até fechar a aba ou clicar em **Sair**.

### Trocar a senha

A senha é guardada como hash SHA-256 dentro do `index.html` (não em texto puro).
Para alterar:

1. Abra o console do navegador (F12) no site.
2. Rode: `await sha256('SUA_NOVA_SENHA')`
3. Copie o hash retornado e substitua o valor de `CREDIA_PASS_HASH` em `index.html`.
4. Faça commit e push.

> Observação: por ser uma proteção client-side, ela impede o acesso casual e
> serve como porta de entrada da intranet — não substitui autenticação de
> servidor para dados altamente sensíveis.

## Como usar

1. Acesse o site e informe a senha.
2. Arraste ou selecione um arquivo CNAB 400 Celcoin (`.txt`, `.rem`, `.cnab`).
3. Veja o dashboard: resumo da carteira, cartões por CCB, tabela de parcelas
   com busca, filtros, ordenação e exportação (CSV / JSON).

## Publicação (GitHub Pages)

O workflow `.github/workflows/deploy-pages.yml` publica automaticamente a cada
push na branch `main`.

Para ativar (uma vez): **Settings → Pages → Build and deployment → Source:
GitHub Actions**. A URL pública aparece em Settings → Pages após o primeiro deploy.
