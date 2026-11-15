# Gabarito

<p><img src="branding/logo/lockup.svg" alt="Gabarito — molde · docs · pdm" height="72"></p>

Template de produto da plataforma **Forja**: cria o esqueleto de um produto com
marca, docs, PDM e regras de trabalho já no lugar, e nada mais.

> A Forja é a bancada. O Gabarito é o molde. O produto tem marca própria.

## O que ele é e o que não é

| é | não é |
|---|---|
| um `init` que pergunta o que só você sabe e **detecta** o resto (SO, git, flatpak/podman, TeamCraft) | um app, framework ou boilerplate de código |
| um conjunto de docs e regras que sobrevive à troca de ferramenta | um gerador de site |
| um molde agnóstico: nenhuma marca, nenhum item, nenhum produto hardcoded | o repositório de um produto |

O Gabarito **não** copia código da Forja: o produto usa as ferramentas
(`forja-pdm`, apps de CAD, PDM) por fora, para poder trocar de bancada sem
reescrever o produto — e para que dois produtos não herdem a marca um do outro.

## Uso

```sh
./init                       # interativo; cria ./<slug>/
./init --into ../brasa       # diretório explícito
./init --yes --name "Brasa" --slug brasa --prefix PS-001 --summary "estanhador 550 W" \
       --author "Tessera" --email "voce@exemplo.com" --accent "#B4683A" \
       --remote git@github.com:dionarley/brasa.git
```

Flags: `--into`, `--name`, `--slug`, `--prefix`, `--summary`, `--author`,
`--email`, `--accent`, `--accent-alt`, `--remote`, `--pdm-url`, `--yes`,
`--force` (destino não vazio), `--no-git`. Sem terminal e sem `--yes`, ele para
em vez de esperar entrada.

O `init` escreve:

```
<destino>/
  product.toml          identidade, PDM, ambiente detectado
  AGENTS.md             como se trabalha neste produto
  README.md             o que é este produto
  brand/brand.md        identidade: promessa, paleta, tipografia, voz
  brand/palette.json    tokens em JSON
  brand/tokens.css      tokens em CSS (claro e escuro)
  docs/PLAN.md          fases e critérios de aceite
  docs/LOG.md           registro cronológico (data, revisão, o que mudou)
  docs/PDM.md           itens, revisões e ECO no TeamCraft
  docs/STYLE.md         nomenclatura e estilo deste produto
  .gitignore
```

Depois: `git init` + commit inicial; o remoto é adicionado (não é pushado sem
você pedir).

## Este repositório

| caminho | o que é |
|---|---|
| `init` | o gerador |
| `template/` | o que cada produto herda (docs, marca vazia, AGENTS, product.toml) |
| `branding/` | a marca **do Gabarito** (não do produto) |
| `AGENTS.md` | como trabalhar aqui |

## O que o `init` detecta

| item | como | para quê |
|---|---|---|
| SO e versão | `/etc/os-release` | registrar em `product.toml` e no log |
| git | `git --version` | versionar o produto |
| flatpak | `flatpak --version` | saber se os CAD rodam empacotados |
| podman | `podman --version` | PDM/banco e visualizador em contêiner |
| cargo / python | `cargo --version`, `python3 -V` | build do serviço e dos scripts |
| TeamCraft | `GET http://127.0.0.1:8080/healthz` | confirmar o PDM e gravar a URL |

Nada é instalado: se falta ferramenta, o `init` avisa e segue.

## Contrato dos placeholders

Os arquivos em `template/` usam `{{chave}}`; o `init` substitui uma vez e não
reprocessa o resultado. Chaves:

`name`, `slug`, `summary`, `prefix`, `author`, `email`, `accent`, `accent_alt`,
`date`, `pdm_url`, `remote`, `os`, `git_version`, `flatpak`, `podman`, `cargo`,
`python`.

Se precisar de uma chave nova, ela entra em `template/` **e** no `init` (senão
fica `{{chave}}` no arquivo gerado — o `init` falha se sobrar placeholder).

## Regra

Este repositório é público e **neutro**: nada de cor, item ou nome de produto
real. Se um valor só existe em um produto, ele é pergunta do `init` — não
conteúdo do template.
