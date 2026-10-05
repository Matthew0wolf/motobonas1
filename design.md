---
version: "1.0"
name: "Motobonas"
description: "Oficina de motos em Fortaleza — identidade visual"
colors:
  bg: "#000000"
  bg-elevated: "#0a0a0a"
  text: "#f5f5f5"
  text-dim: "#999999"
  primary: "#e10600"
  primary-deep: "#8f0400"
  divider: "rgba(245,245,245,.14)"
  divider-soft: "rgba(245,245,255,.07)"
typography:
  heading-display:
    fontFamily: "Jost"
    fontWeight: 200
    fontSize: clamp(60px, 11.5vw, 180px)
    lineHeight: 0.96
    letterSpacing: 0.05em
    textTransform: uppercase
  heading-section:
    fontFamily: "Jost"
    fontWeight: 300
    fontSize: clamp(46px, 7.5vw, 110px)
    marginBottom: 28px
    letterSpacing: 0.02em
  body:
    fontFamily: "Inter"
    fontSize: clamp(15px, 1.5vw, 18px)
    lineHeight: 1.75
    fontWeight: 400
  mono-label:
    fontFamily: "Jost"
    fontSize: 12px
    letterSpacing: 0.22em
    textTransform: uppercase
spacing:
  xs: clamp(4px, 0.8vw, 8px)
  sm: clamp(8px, 1.5vw, 16px)
  md: clamp(16px, 3vw, 32px)
  lg: clamp(28px, 4.5vw, 56px)
  xl: clamp(50px, 7vw, 80px)
  xxl: clamp(100px, 14vh, 170px)
components:
  button-primary:
    backgroundColor: "{colors.bg}"
    borderColor: "{colors.primary}"
    color: "{colors.text}"
    fontFamily: "{typography.mono-label.fontFamily}"
    fontSize: "{typography.mono-label.fontSize}"
    padding: "16px 34px"
    borderRadius: 2px
    transition: 0.3s
  button-primary-hover:
    backgroundColor: "{colors.primary}"
    color: "#fff"
  button-solid:
    backgroundColor: "{colors.primary}"
    borderColor: "{colors.primary}"
    color: "#fff"
  button-solid-hover:
    backgroundColor: "#f5f5f5"
    borderColor: "#f5f5f5"
    color: "#000"
---

## Visão geral

Motobonas é uma oficina especializada em motos de média e alta cilindrada em Fortaleza/CE. O site é uma landing page estática com foco em conversão via WhatsApp.

## Cores

- **Preto (`#000000`)**: background principal
- **Cinza escuro (`#0a0a0a`)**: background de cards/elevations
- **Branco (`#f5f5f5`)**: texto principal
- **Cinza médio (`#999999`)**: texto secundário/dim
- **Vermelho (`#e10600`)**: cor de destaque, botões, acentos

## Tipografia

- **Jost**: fonte para headings, labels, botões (peso 200-500)
- **Inter**: fonte para corpo de texto (peso 400-500)

## Layout

Estrutura baseada em grid com breakpoints:
- Mobile (<640px): colunas únicas, navegação hamburger
- Tablet (640px-1024px): 2 colunas
- Desktop (>1024px): até 4 colunas

## Componentes

- **Botões primários**: borda vermelha, preenchimento transparente, hover preenchido vermelho
- **Botões sólidos**: fundo vermelho, hover branco
- **Card de serviço**: hover com elevação sutil
- **Rail de capítulos**: fixed right, scrollspy

## Acessibilidade

- Contraste texto/preto: 15.8:1 (AAA)
- Contraste texto/branco: 12.6:1 (AAA)
- Contraste vermelho/branco: 4.5:1 (AA)
- `:focus-visible` com ring visível
- `prefers-reduced-motion` suportado