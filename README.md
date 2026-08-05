# 3contratodos.com — ⚠️ REPOSITÓRIO APOSENTADO (04/08/2026)

> **Este repo não serve mais nenhum site. Não edite nada aqui esperando ver mudança no ar.**
>
> O domínio `3contratodos.com` passou a ser servido pelo repo **`3-contra-todos-game`**, que hoje
> concentra site, conteúdo e o jogo jogável (`/demo/` e `/v2/`). O GitHub Pages **deste** repo foi
> desativado para liberar o domínio.
>
> **A home desta landing não foi descartada** — ela virou a home do site consolidado, com o vídeo
> do Werdum, o selo "Nº 1 App Store BR" e os créditos preservados, mais a navegação do site. O
> arquivo vivo é `3-contra-todos-game/landing/index.html`.
>
> Motivo da consolidação e passo a passo: `3-contra-todos-game/_info/migracao-dominio-3contratodos.md`.
>
> Mantido apenas como histórico.

Landing page promocional do jogo **3 Contra Todos** para download nas lojas iOS e Android.

## Stack

Site estático puro (HTML + CSS, sem build). Hospedado em GitHub Pages com domínio custom `3contratodos.com`.

## Estrutura

```
.
├── index.html           # Landing única
├── CNAME                # 3contratodos.com
├── .nojekyll            # Desliga Jekyll no GH Pages
├── robots.txt
├── sitemap.xml
├── imgs/                # Logo, ícones, fundo, personagens
└── screenshots/         # 3 prints iPhone 6.5
```

## Identidade visual

Reaproveita a identidade do jogo (`werdum-fight`):

- **Fonte display:** `Press Start 2P` (mesma do TitleScene)
- **Fonte corpo:** `Pixelify Sans`
- **Cor primária:** `#f3c204` (amarelo/dourado)
- **Background hero:** `intro-bg.jpg` (mesma arte da tela inicial do jogo)
- **Logo:** `logo-novo.png` (do projeto principal)

## Links

- **App Store (live, R$ 1,90):** https://apps.apple.com/br/app/3-contra-todos/id6761487568
- **Google Play:** "Em breve" (badge desabilitado, ativar quando publicar)

> A versão grátis do navegador (`werdumfight.com`) **não é divulgada** nesta landing — foco é conversão pra app pago.

## Deploy (GitHub Pages)

1. Criar repo no GitHub: `thiagozeni/3contratodos`
2. Configurar remote SSH:
   ```bash
   cd /Users/pro15/Claude/3contratodos
   git init
   git add .
   git commit -m "feat: landing inicial"
   git remote add origin git@github.com:thiagozeni/3contratodos.git
   git branch -M main
   git push -u origin main
   ```
3. No GitHub: **Settings → Pages → Source: main / root**
4. Comprar `3contratodos.com` e configurar DNS:
   - Registros `A` para `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Ou registro `CNAME` `www` apontando para `thiagozeni.github.io`
5. Aguardar SSL (até 15 min após DNS propagar) e habilitar **Enforce HTTPS**

## Quando o Google Play sair

Editar `index.html` — trocar o `<span class="badge disabled">` por:

```html
<a class="badge" href="<URL_PLAY_STORE>" target="_blank" rel="noopener">
  <span class="badge-icon"><!-- mesmo SVG --></span>
  <span class="badge-text">
    <small>BAIXAR NO</small>
    <strong>Google Play</strong>
  </span>
</a>
```
