# instagram-media

Arquivos de mídia dos posts do Instagram **@adriano.anthony**.

## Por que existe

O Meta busca a imagem por HTTP (`image_url` aponta pra cá), então os JPEGs ficam versionados em vez de soltos no portfólio.

## Especificação

- **1080 × 1350** (4:5 — formato de maior área visível no feed)
- **JPEG** — a Graph API rejeita outros formatos em `image_url`
- `quality=90`, progressivo

## Identidade visual

Mesmos tokens do portfólio (`adrianoanthonymma16-boop/portfolio-adriano`):

| token | valor | uso |
|---|---|---|
| `--fundo` | `#0D1017` | fundo |
| `--acento` | `#777AAD` | acento, eyebrow, URL |
| `--acento-forte` | `#8F91BF` | acento claro |
| `--fundo-suave` | `#171C26` | cartões |
| `--borda` | `#272E3B` | bordas |
| `--texto` | `#EDEEF6` | títulos |
| `--texto-corpo` | `#C4C7D6` | corpo |

Fontes: **Inter** (corpo) + **JetBrains Mono** (eyebrow, números, rodapé).

## Pipeline

```
src/post1.html
  → chrome-headless-shell --window-size=1080,1350 --screenshot=...png
  → PIL → JPEG quality 90
  → posts/001-...jpg
  → raw.githubusercontent.com/... → image_url no Instagram
```

## Estrutura

```
posts/  números de ordem de publicação: 001, 002, ...
src/    HTML-fonte de cada post
```
