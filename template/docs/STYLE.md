# STYLE — {{name}}

Nomenclatura e estilo deste produto. O resto (Rust, Python, commits) segue o
`docs/STYLE.md` da Forja.

## Nomes

| namespace | regra | exemplo |
|---|---|---|
| repositório | kebab-case, slug da marca | `{{slug}}` |
| item PDM | `<PREFIXO>-<TIPO>-<NNN>`, sempre 3 dígitos | `{{prefix}}-LM-001` |
| ECO | `{{prefix}}-CHG-<6 dígitos>` | `{{prefix}}-CHG-000001` |
| arquivo de modelo | `<item>-<rev>.step` | `{{prefix}}-MD-001-A.step` |
| prancha | `<item>-<rev>.dxf` + pdf | `{{prefix}}-DR-001-A.dxf` |
| documento | `docs/<NOME>.md` (nome EN, conteúdo PT) | `docs/PLAN.md` |
| script | `<função>_<objeto>.py` | `cut_list.py` |

Identificador em inglês, texto em português, unidade SI no nome do parâmetro
(`chord_mm`, `flow_rate_m3_s`).

## Números

- Sempre com unidade, no mono: `127 V`, `4,3 A`, `12,5 mm`, `1,9 kg`.
- Vírgula decimal em texto e tabela; ponto só em código e em nome de arquivo.
- Tolerância explícita: `12,5 ±0,2 mm` — nunca “aproximadamente”.

## Tabelas de documento

Uma grandeza por linha, com **como foi medido** em coluna própria. Se não há
medição, a célula é `—` e o texto diz por que.

## Versionamento

| coisa | esquema |
|---|---|
| produto | revisão A, B, C… + ECO |
| documentos | a mesma revisão do item |
| código (`CO`) | semver no repo, revisão no PDM |
| marca (`brand/`) | versão de tokens (`v1`) |

## Commits

```
tipo: resumo no imperativo

por que, se não for óbvio.
```

`tipo` ∈ `feat`, `fix`, `docs`, `test`, `refactor`, `chore`, `perf`. Português,
sem emoji, sem ponto final no resumo.
