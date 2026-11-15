# PLAN — {{name}}

Fases curtas, cada uma fechando com número e arquivo. O que não couber, fica
escrito como “fora desta fase” — não como promessa.

## Fase 0 — escopo ({{date}})

- [x] identidade e paleta (`brand/`)
- [x] docs, PDM e regras de trabalho (`docs/`, `AGENTS.md`)
- [ ] item `{{prefix}}-PL-001` criado no TeamCraft com este escopo anexado

**Aceite:** `product.toml` preenchido, repositório com commit inicial, PDM com o
item de escopo na revisão A.

## Fase 1 — projeto

| # | entrega | critério de aceite |
|---|---|---|
| 1 | requisitos e restrições | tabela com grandeza, faixa e por que |
| 2 | arquitetura / princípio de funcionamento | um desenho + um parágrafo |
| 3 | escolha de material e processo | justificada com número (custo, esforço, tolerância) |

**Fora desta fase:** *(preencher no fim da fase 1 — o que foi dito e não entra)*

## Fase 2 — modelo e desenho

- modelo 3D paramétrico no app CAD (fonte da verdade: o arquivo do app)
- STEP exportado e anexado ao item (`{{prefix}}-MD-001`)
- prancha 2D com cotas, tolerâncias e materiais (`{{prefix}}-DR-001`)

**Aceite:** o STEP mede o que o desenho cota (volume, massa, entre-eixos).

## Fase 3 — protótipo e ensaio

| ensaio | grandeza | critério |
|---|---|---|
| elétrico | isolação | ≥ 2 MΩ a 500 V |
| térmico | temperatura em regime | ≤ TODO(°C) — definir na fase 2 |
| mecânico | fixação / torque | sem afrouxar em TODO(ciclos) |

**Aceite:** relatório em `docs/` com condições, instrumento e desvio.

## Fase 4 — liberação

- revisão A liberada por ECO no TeamCraft
- docs e PDFs em `dist/` com SHA-256 registrado no item
- BOM conferida (todo filho liberado ou explicitamente fora)

**Aceite:** ECO liberada; nenhum documento controlado pendente.
