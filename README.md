# The University Launchpad — site

Site estático de uma página (HTML + CSS + JS num único `index.html`, sem build).
Idiomas: EN / PT / ES / 中文 (seletor no header).

## Estrutura

```
index.html            página completa
img/                  fotos (TODAS PROVISÓRIAS — ver abaixo)
video/                colocar aqui o vídeo de introdução (ver video/LEIA-ME.txt)
favicon.svg / .ico    ícone do site (ponta de seta)
apple-touch-icon.png  ícone para iPhone
icon-192/512.png      ícones do manifest
site.webmanifest
og-image.jpg          imagem de partilha (WhatsApp, LinkedIn, etc.) 1200×630
robots.txt            permite indexação
sitemap.xml           trocar DOMINIO-PENDENTE
vercel.json           cache das imagens/vídeo + URLs limpos
```

## Publicar (GitHub + Vercel)

1. Criar um repositório no GitHub e subir **o conteúdo desta pasta** (o `index.html` tem de ficar na raiz).
2. Vercel → **Add New → Project → Import** o repositório.
3. Framework Preset: **Other** · Build Command: *vazio* · Output Directory: *vazio*.
4. **Deploy**. A partir daí, cada alteração enviada ao GitHub publica sozinha.
5. Domínio: Vercel → **Settings → Domains** → adicionar o domínio e seguir as instruções de DNS.

Pré-visualização rápida sem GitHub: arrastar esta pasta para vercel.com/new.

## Depois de ter o domínio (trocar `DOMINIO-PENDENTE`)

- `index.html` → descomentar `<link rel="canonical">`, `og:url` e `og:image` com URL absoluto
  (as redes sociais só leem a og-image com o endereço completo, ex: `https://dominio.com/og-image.jpg`).
- `sitemap.xml` → trocar o domínio.
- `robots.txt` → descomentar a linha `Sitemap:`.

## ⚠️ Antes de o site ser público

- **Fotos provisórias** em `img/` — trocar pelas reais **mantendo os mesmos nomes de ficheiro**
  (assim não é preciso mexer no HTML):
  - `hero-video-cover.jpg` — capa do vídeo (idealmente um frame do próprio vídeo), horizontal ~1600px
  - `cynthia-placeholder.jpg` — retrato da Cynthia, vertical ~1000px
  - `consulting-desk.jpg` — sessão/ambiente de trabalho, horizontal ~1000px
  - `avatar-1/2/3.jpg` — fotos dos alunos dos depoimentos (quadradas, 256px, com autorização)
  - `final-texture.jpg` — textura do CTA final (pode ficar)
  A foto do hero e o retrato vêm de um projeto público no GitHub (withastro/astro) e podem exigir
  crédito ao autor — servem só para apresentação, não para o site público.
- **Vídeo**: ver `video/LEIA-ME.txt` (H.264 8-bit obrigatório).
- **Conteúdo pendente** (marcado na página com etiquetas amarelas e no código com `PENDENTE`):
  história/experiência/credenciais da Cynthia, depoimentos, respostas do FAQ, email, redes sociais,
  destino do botão "Book a consultation" (Calendly/WhatsApp/formulário), cidades do banner Europa.
- **Traduções** PT / ES / 中文 — rever com falantes nativos.
- **Páginas internas** (/personal-consulting, /membership, /morrisby, /about, /resources, /book…):
  ainda não existem. Os links levam a secções da Home. Quando existirem, no fim do `index.html`
  mudar `const PAGES_LIVE = false;` para `true`.

## Nomes de ficheiros

O servidor da Vercel distingue maiúsculas de minúsculas: `Foto.JPG` ≠ `foto.jpg`.
Usar sempre minúsculas, sem acentos nem espaços.
