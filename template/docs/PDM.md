# PDM — {{name}} no TeamCraft

O PDM é a fonte de verdade de **item, revisão, ECO e arquivo**. O repositório
guarda as fontes; o PDM guarda o que foi liberado e quando.

- URL: {{pdm_url}}
- Projeto: `{{prefix}}`
- Token: `credentials.txt` da instalação ou `~/.config/{{slug}}/credentials.toml`

## Tipos de item

| código | tipo | exemplo |
|---|---|---|
| `PL` | plano / escopo | `{{prefix}}-PL-001` |
| `MD` | modelo 3D (STEP da revisão) | `{{prefix}}-MD-001` |
| `DR` | desenho / prancha | `{{prefix}}-DR-001` |
| `LM` | lista de materiais / componente | `{{prefix}}-LM-001` |
| `LE` | laudo / ensaio | `{{prefix}}-LE-001` |
| `CO` | código / software | `{{prefix}}-CO-001` |
| `CHG` | ECO (ordem de mudança) | `{{prefix}}-CHG-000000` |

## Revisões

- Revisão é **letra**: A, B, C… Não existe tag semver de produto.
- `in_work` → `in_review` → `released` → `obsolete`. Só ECO libera.
- Mudança em revisão liberada = revisão nova + ECO. Nunca edite arquivo de
  revisão liberada.
- Arquivo é referenciado por **SHA-256**; o mesmo conteúdo não é duplicado.

## Fluxo de uma entrega

```
1. cria/atualiza o item (in_work)
2. anexa o arquivo (STEP, PDF, planilha)
3. descreve o que mudou e por quê
4. abre ECO com os itens afetados
5. revisão em revisão por outra pessoa → libera
6. docs/LOG.md ganha a linha com revisão e ECO
```

## Regras

- **Não apague objeto do vault.** O PDM referencia por hash e não há lixeira.
- **Backup antes de migração** de item ou revisão: banco é o índice, vault é o
  conteúdo; um sem o outro não serve.
- Item de outro projeto só aparece se você for membro do grupo — “não
  encontrado” pode ser permissão, não ausência.
