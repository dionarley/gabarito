# AGENTS.md — {{name}}

Produto **{{name}}** ({{slug}}), da plataforma Forja. Este arquivo diz como
trabalhar aqui; `product.toml` diz o que o produto é.

## Contexto em cinco linhas

- Produto: {{summary}}
- Prefixo dos itens no PDM: `{{prefix}}` (revisões A, B, C…, nunca tag semver).
- PDM: TeamCraft em {{pdm_url}} — itens, revisões, ECO e arquivos.
- Docs em `docs/` são fonte única; PDF liberado fica em `dist/`.
- A marca do produto vive em `brand/`; a marca pessoal só assina (rodapé, laudo).

## Regras duras

- **Documento controlado**: mudar conteúdo ou front matter = revisão nova +
  ECO. Não edite PDF em `dist/`; gere de novo a partir da fonte.
- **Desenho e modelo** saem de app CAD (SolidCraft/CadCraft), não de SVG à mão.
  Medição sai de `measure`/`eval`, não de estimativa.
- **Números com unidade**; toda afirmação em relatório tem como foi medido.
- **Segredos** em `~/.config/<slug>/credentials.toml` (0600) ou no
  `credentials.txt` do TeamCraft. Nunca no repo, nunca em log.
- Identificadores em inglês, texto em português. Números de item sempre com
  três dígitos: `{{prefix}}-LM-001`.

## Fluxo

```
ideia → docs/PLAN.md (fase e critério de aceite)
      → modelo/desenho (CAD) + ensaio quando couber
      → revisão A no PDM + docs/LOG.md
      → ECO quando muda o que já foi liberado
```

## Comandos

```sh
git status                                   # sempre antes de editar em lote
forja/scripts/service.sh status              # PDM de arquivos no ar?
forja/tools/status.sh                        # as cinco portas da bancada
```

## Antes de dizer “pronto”

- O documento gerado (PDF/STEP/DXF) abre e confere com a fonte.
- `docs/LOG.md` tem a linha da mudança, com data e revisão.
- O item no PDM aponta para o arquivo certo (SHA-256 confere).
- Se mexeu em revisão liberada: existe ECO, e ela foi aprovada.
