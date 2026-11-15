# LOG — {{name}}

Registro cronológico: uma linha por mudança que importa. O que muda documento
controlado aparece com **revisão** e, se for o caso, **ECO**.

Formato: `data · revisão · o que mudou · quem`

| data | rev | o que mudou | item | autor |
|---|---|---|---|---|
| {{date}} | A | criação do produto: identidade, docs e regras | — | {{author}} |

## Como registrar

- **Uma linha por entrega**, não por sessão de trabalho.
- Cite o item do PDM quando existir (`{{prefix}}-LM-001`).
- Se a mudança altera o que já foi liberado, a linha traz a ECO
  (`CHG-000000`) — sem ECO a mudança não entra em revisão liberada.
- Não reescreva linha antiga: correção vira linha nova com “corrige …”.
