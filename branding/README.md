# Branding do Gabarito

Identidade **do template** — não confundir com `template/brand/`, que é o espaço
de marca que cada produto gerado herda e sobrescreve.

| caminho | o que é |
|---|---|
| `branding/` (aqui) | marca do Gabarito, o molde |
| `template/brand/` | marca do **produto** gerado (vazia de identidade, preenchida pelo `init`) |

## Símbolo

Molde e peça: a moldura de aço e o bloco de cobre que cabe dentro dela. Diz o que
o Gabarito faz — dá o contorno, o produto põe o conteúdo.

| arquivo | uso |
|---|---|
| `logo/mark.svg` | avatar, ícone |
| `logo/favicon.svg` | favicon 32 px |
| `logo/wordmark.svg` | rodapé, assinatura |
| `logo/lockup.svg` | cabeçalho de documento e README |

Contornos (texto em caminho): não dependem de fonte instalada.

Regras de uso iguais às da plataforma: respiro de meia altura, mínimo 16 px
(símbolo) e 120 px (lockup), fundo papel ou grafite.

## Paleta e tipografia

As mesmas da Tessera (repo privado `dionarley/tessera`): grafite `#1B1E22`,
papel `#F5F2EC`, aço `#2F6F8F`, cobre `#B4683A`, sinal `#4C9A6A`, mutado
`#8A8F94`; IBM Plex Sans (títulos) e Plex Mono (números e código).

O produto gerado **não** herda este símbolo nem necessariamente estas cores: o
`init` pergunta o acento do produto e escreve `brand/` próprio.
