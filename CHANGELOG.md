# Changelog — site Motobonas

## Out/2026 — auditoria e correções

### Correção do fundo dos cards Oficina/Peças
- As variantes responsivas de `naked` e `carenada` foram geradas em RGB e perdiam o recorte transparente: o fundo virava um retângulo preto sólido sobre o card. Regeradas preservando RGBA (AVIF e WebP) nas três larguras.
- `.build` passou a usar `--bg` (#000) puro, com o brilho laranja num `::before` a 7%. Os dois cards agora têm exatamente o mesmo fundo.

### Medição e conversão
- GA4 preparado (`GA4_ID` no script; vazio até receber o ID real) com eventos `whatsapp_click` e `form_submit`. O código antigo chamava `gtag` com o placeholder `AW-CONVERSION_ID/LEAD_LABEL` e o gtag nunca era carregado — não havia medição.
- Formulário com erro visível por campo, `aria-invalid`, `aria-live` e validação de WhatsApp; `<noscript>` com o contato direto.
- Endereço clicável (Google Maps) e status "aberto/fechado agora" calculado em America/Fortaleza.

### Acessibilidade
- Contraste dos CTAs: texto branco sobre laranja dava 3,35:1; agora texto #0a0a0a sobre laranja = 6,26:1.
- Conteúdo visível sem JavaScript (o reveal só esconde quando `<html>` tem `.js`).
- `aria-label` inválido em `<div>` corrigido (role em `.strip`/`.marquee`, estrelas em `span role="img"`), headings nas avaliações.
- Menu mobile com `aria-expanded`, ESC e contenção de foco. Alvos de toque ampliados.

### Performance
- Payload mobile caiu de ~2.845 KB para ~240 KB: vídeo só em desktop e após `load` (recomprimido de 2.260 KB para 951 KB), imagens em AVIF/WebP com `srcset`, Inter self-hosted (fim dos 1.035 ms de bloqueio do Google Fonts).
- `vercel.json` com cache imutável para `/assets/*` (antes todo asset vinha com `max-age=0`).

### SEO e processo
- canonical, `og:url`, `og:locale`, twitter card, `robots.txt`, `sitemap.xml`, `favicon.ico`.
- JSON-LD `AutoRepair` completo (geo real, horários, `hasMap`, `sameAs`, `foundingDate`) e `FAQPage` sincronizado com a página.
- Rodapé com navegação, CNPJ, "desde 2004" e link para a política de privacidade (`privacidade.html`).
- Removidos 40 MB de arquivos não usados (modelo 3D, textures, vídeos duplicados, imagens órfãs) e adicionado `.gitignore`.

### Documentação
- `design.md` reescrito para refletir o código (antes citava Jost, `#e10600` e um "rail de capítulos" que nunca existiram).
- `tokens.css` sincronizado com as variáveis reais.

## Antes de out/2026
- Remoção do visualizador 3D da BMW S1000RR (`model-viewer` e seção `#s1000rr`).
