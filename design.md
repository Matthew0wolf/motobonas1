# Motobonas — sistema visual

Especificação do que está **realmente** no `index.html`. Se mudar o CSS, atualize aqui.

## Cores

| token | valor | uso |
|---|---|---|
| `--bg` | `#000000` | fundo do site e dos cards |
| `--bg2` | `#0a0a0a` | superfícies elevadas (serviços, avaliações) |
| `--ink` | `#f5f5f5` | texto principal |
| `--dim` | `#999999` | texto secundário (7,37:1 no preto) |
| `--accent` | `#f7550f` | destaque, links, micro-labels (6,26:1 no preto) |
| `--accent-deep` | `#b53c08` | acento sobre fundo claro (5,91:1 no branco) |
| `--line` | `rgba(245,245,245,.13)` | divisores |
| `--line-soft` | `rgba(245,245,245,.07)` | divisores sutis |

## Tipografia

Uma família só: **Inter** (variável, 200–600), self-hosted em `assets/fonts/*.woff2`. Sem Google Fonts e sem segunda família.

- display (`h1`): `clamp(64px, 11.5vw, 180px)` · peso 200 · uppercase · `line-height: .98` · `letter-spacing: .05em`
- seção (`h2`): `clamp(44px, 7vw, 104px)` · peso 200 · uppercase
- corpo: `clamp(15px, 1.5vw, 18px)` · peso 300 · `line-height: 1.75`
- micro-label: 12px · `letter-spacing: .3em` · uppercase · cor `--accent`

## Componentes

- **`.btn` (sólido)**: fundo `--accent`, texto `#0a0a0a` (6,26:1), padding `16px 36px`, raio 2px; hover inverte para `#f5f5f5` com texto preto.
- **`.btn.ghost-btn`**: transparente, borda `--line`; hover com borda/texto laranja.
- **`.build` (oficina / peças)**: fundo `--bg` puro (preto) + brilho radial laranja a 7% num `::before` decorativo. As imagens das motos são recortes com alpha: nunca converter para RGB ao gerar variantes, senão o fundo transparente vira retângulo preto sobre o card.
- **`.svc`, `.rev`, `.rev-head`**: superfície `--bg2`, borda `--line-soft`, hover muda a borda.
- **`.team-card`**: retrato quadrado com nome e função; grade em três colunas no desktop e duas em telas menores.
- **`.marquee`**: track infinito, segunda cópia com `aria-hidden`, pausa no hover.

## Imagens

- Sempre `<picture>` com AVIF + WebP e `srcset` (480 / 800 / 1200 + maior), `sizes` coerente com o layout.
- Fotos: `width`/`height` explícitos, `loading="lazy"`, `decoding="async"`.
- Retratos da equipe ficam em `equipe/`, com `object-fit: cover` para preservar o enquadramento quadrado.
- Recortes de moto: RGBA preservado nos três formatos.

## Movimento

- Reveal por `IntersectionObserver`, apenas quando `<html>` tem a classe `js` — sem JavaScript o conteúdo nunca fica invisível.
- Vídeo do hero: só em telas ≥ 641px, depois do evento `load`, desligado em `prefers-reduced-motion` e em conexão com data-saver.
- `prefers-reduced-motion: reduce` desliga animações e transições.

## Acessibilidade — números medidos

- Texto principal sobre preto: 19,26:1.
- Texto `--dim` sobre preto: 7,37:1.
- Botão sólido (texto preto sobre laranja): 6,26:1.
- Links de contato com alvo de toque ≥ 44px no mobile.
- Menu mobile: `aria-expanded`, fecha com ESC, foco entra no overlay e fica contido.
- Formulário: erro visível por campo, `aria-invalid` e `aria-live`.

## Breakpoints

- `< 640px`: coluna única, hamburger, barra fixa de agendamento.
- `640–1024px`: 2 colunas.
- `> 1024px`: até 4 colunas.
