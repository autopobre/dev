# Auto-Pobre Racing — versão de testes

Este repositório só publica a versão de testes do jogo em **https://dev.autopobre.com.br/**. Ele não tem código: o jogo, os testes e a montagem ficam em [autopobre/autopobre](https://github.com/autopobre/autopobre).

O endereço próprio separa a versão de testes do link principal (https://autopobre.com.br/): saves, preferências e cookies de um não chegam ao outro. É aqui que o login e as novidades são testados antes de chegar aos jogadores.

## Publicar

**Actions → Publicar dev.autopobre.com.br → Run workflow**, escolhendo a versão: `main` (padrão), uma tag (`apr-X.Y`) ou um commit (o hash completo, com 40 caracteres). O fluxo chama [Montar a versão de testes](https://github.com/autopobre/autopobre/blob/main/.github/workflows/montar-dev.yml) do repositório do jogo, que baixa essa versão, roda os testes dela e gera o pacote com o multiplayer, a bancada de som e o editor de traçado. Depois publica o pacote aqui. Enviar algo para o repositório do jogo não muda este endereço: ele só muda quando o fluxo roda.

## Configuração (uma vez)

- **Settings → Pages:** Source **GitHub Actions**, Custom domain `dev.autopobre.com.br`, **Enforce HTTPS** ligado.
- **DNS no Cloudflare:** `dev` como CNAME para `autopobre.github.io`. Comece com a nuvem cinza (sem proxy) até o GitHub emitir o certificado; depois ligue a nuvem laranja (com SSL Full (strict), o proxy antes do certificado dá erro 526).
