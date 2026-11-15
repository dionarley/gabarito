# AGENTS.md — trabalhando no Gabarito

Repositório do template de produto. Ele é público e **neutro**: nada de marca,
item ou nome de produto real aqui — isso é pergunta do `init`.

## Regras duras

- **Placeholder novo entra em dois lugares**: em `template/<arquivo>` e na lista
  `pairs` do `init`. Se sobrar `{{chave}}`, o `init` falha de propósito.
- **`template/` é o produto gerado.** Não coloque arquivo que só faz sentido no
  Gabarito lá dentro.
- **Sem dependência**: `init` é bash + coreutils + git opcional. Nada de Python
  com pacote, nada de instalar nada na máquina do usuário.
- **`init` só escreve com destino vazio** (ou `--force`) e só roda git no
  destino. Ele nunca mexe em diretório existente por acidente.
- Idioma: documentos em português, nomes de arquivo e chaves em inglês.

## Testar antes de comitar

```sh
bash -n init && shellcheck init
./init --yes --name Teste --slug teste --prefix TS-001 \
       --author Teste --email teste@example.com --into /tmp/opencode/gabarito-teste
grep -rn '{{' /tmp/opencode/gabarito-teste || echo 'sem placeholder solto'
rm -rf /tmp/opencode/gabarito-teste
```

Aceite: nenhum `{{...}}` no resultado, `product.toml` com o ambiente detectado,
commit inicial criado, `brand/`, `docs/` e `AGENTS.md` no lugar.

## Mapa

| caminho | o que é |
|---|---|
| `init` | o gerador: detecção, perguntas, render, git |
| `template/` | o que o produto herda (docs, brand, AGENTS, product.toml) |
| `README.md` | como usar e o que o `init` detecta |
