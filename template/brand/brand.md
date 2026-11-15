# {{name}} — identidade

**O que é:** {{summary}}

**Promessa:** {{name}} faz o que promete com número para provar; o que não couber
no prazo é dito antes, não depois.

## Nome

- **Nome:** {{name}} · **slug:** `{{slug}}`
- Não use o nome como adjetivo (“solução {{name}}”); ele é o produto.
- A marca pessoal (Dionarley) assina o laudo e a proposta — **não** é logo do
  produto e não aparece no produto.

## Paleta

| token | hex | uso |
|---|---|---|
| `accent` | `{{accent}}` | destaque principal: ação, dado medido, link |
| `accent-alt` | `{{accent_alt}}` | alerta, série secundária, detalhe |
| `graphite` | `#1B1E22` | texto e fundo escuro |
| `paper` | `#F5F2EC` | fundo claro |
| `muted` | `#8A8F94` | texto secundário, réguas, cotas |

Proporção: 90 % neutro, 9 % `accent`, 1 % `accent-alt`. Acento é tempero.

## Tipografia

- **Sans** para texto e títulos; **mono** para número, unidade, código e cota.
- Número sempre com unidade e no mono: `127 V`, `41 ciclos`, `12,5 mm`.

## Voz

Direto, técnico, sem superlativo. “Medi 41 ciclos, 0 falha” vale mais que
“altíssima confiabilidade”. Em documento técnico: sem emoji, sem hype.

## Uso

- Área de respiro: metade da altura do símbolo em todos os lados.
- Fundo sempre `paper` ou `graphite`; nunca sobre foto sem véu.
- Não esticar, inclinar, trocar a cor do acento nem pôr sombra.

Os tokens prontos para código estão em `palette.json` e `tokens.css` — use-os,
não redefina hex.
