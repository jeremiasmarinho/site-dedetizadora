# Design System Master — Dedetizadora Araguaína

> **LÓGICA:** ao construir uma página específica, verifique antes
> `design-system/dedetizadora-araguaina/pages/[pagina].md`. Se existir, ele
> sobrepõe este Master. Se não, siga estritamente as regras abaixo.

---

**Projeto:** Dedetizadora Araguaína (Joabson Alves França-ME) — Araguaína/TO
**Atualizado:** 2026-08-18
**Direção visual:** "Placa de fachada do cerrado" — identidade extraída do
cartão real da empresa. Traço grosso, cor chapada, sombra dura, tom local e
direto. **Esta é a fonte de verdade** — a recomendação genérica anterior
(navy "Trust & Authority") foi descartada por decisão de manter a identidade
autêntica da marca.

---

## Paleta (amostrada do cartão da empresa)

| Papel | Hex | Variável CSS |
|---|---|---|
| Amarelo (marca/fundo hero) | `#ffc800` | `--amarelo` |
| Amarelo claro | `#ffdb57` | `--amarelo-cl` |
| Vermelho (destaque) | `#d62518` | `--vermelho` |
| Vermelho tinta (texto/botão, AA) | `#a81c12` | `--vermelho-tinta` |
| Preto (contorno/fundos) | `#141210` | `--preto` |
| Verde | `#5e9b3f` | `--verde` |
| Verde folha (hero) | `#a8d98a` | `--verde-folha` |
| Verde escuro (form) | `#2f5a22` | `--verde-escuro` |
| Creme (fundo página) | `#fff7e4` | `--creme` |
| Papel (cartões) | `#ffffff` | `--papel` |
| Tinta (texto) | `#141210` | `--tinta` |
| Tinta fraca (texto secundário) | `#5a534a` | `--tinta-fraca` |
| Linha (divisores) | `#e6ddc9` | `--linha` |
| WhatsApp (botão) | `#128c4a` | — |

Regras de contraste: texto corrido usa `--tinta`/`--tinta-fraca` sobre creme
ou papel; vermelho em texto/botão é sempre `--vermelho-tinta` (AA), nunca
`--vermelho` puro.

## Forma ("placa esmaltada")

- Raio: `--raio: 14px`
- Contorno: `--contorno: 3px solid var(--preto)` em todo cartão/botão
- Sombra dura (sem blur): `--sombra: 6px 6px 0 var(--preto)`; versão
  pequena `4px 4px 0`
- Hover de botões/cartões: translate(-2px,-2px) + sombra maior; active
  translate(2px,2px) + sombra 1px — simula pressionar a placa

## Tipografia

- **Display (h1–h3):** Anton, uppercase, weight 400, line-height ~1.02–1.14
- **Corpo:** Barlow 400–700, 17px/1.62
- **Rótulos/eyebrows/tags:** Barlow Condensed 600–700, uppercase,
  letter-spacing .06–.14em
- Fallbacks: "Arial Narrow", Impact, system-ui
- Destaque em títulos: `<em>` sem itálico, cor `--vermelho`

## Componentes canônicos (ver index.html)

- `.btn` (variantes: `btn-tel` vermelho-tinta, `btn-wa` verde WhatsApp,
  `btn-amr` amarelo, `btn-preto` preto/amarelo) — min-height 58px
- `.selo` — selos de confiança ilustrados no hero
- `.painel`, `.casa-box` — raio-x interativo da casa (elemento-assinatura)
- `.praga`, `.seg`, `.passos` — cartões de conteúdo
- `.faixa` — tarja preta com texto condensado amarelo
- `.barra` — barra fixa mobile (ligar/WhatsApp), some ≥900px
- Ilustrações: SVG próprio inline (sprite em `<defs>`), traço grosso, cor
  chapada — **nunca** emoji, nunca ícone raster, nunca stock genérico

## Acessibilidade e movimento

- `:focus-visible` com outline 3px vermelho
- `prefers-reduced-motion`: desliga animações, revela `.reveal`
- Alvos de toque ≥ 54px; formulário com labels visíveis e honeypot
- Contraste mínimo AA em todo texto

## Evitar (anti-padrões)

- Paletas corporativas genéricas (navy/azul SaaS) — descaracteriza a marca
- Sombras difusas/glassmorphism — a linguagem é sombra dura de placa
- Esconder telefone/WhatsApp; omitir licença ambiental 109/2023 ou RT
  CRMV-TO 00395
- Publicar depoimento, nota ou número que não seja verdadeiro
