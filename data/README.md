# Dados do catálogo

Esta pasta concentra os dados usados pelo Meu Cinema IMDb.

## Arquivo publicado

`catalogo-filmes.json`

Formato aceito:

```json
{
  "generatedAt": "2026-08-10",
  "source": "IMDb public datasets",
  "movies": [
    {
      "id": "tt0111161",
      "title": "The Shawshank Redemption",
      "year": 1994,
      "genres": "Drama",
      "rating": 9.3,
      "votes": 3000000
    }
  ]
}
```

O `index.html` procura automaticamente `./data/catalogo-filmes.json` ao abrir.

## Fonte oficial

Para reconstruir o catálogo, use os datasets públicos do IMDb:

- `title.basics.tsv.gz`
- `title.ratings.tsv.gz`

O aplicativo local também continua aceitando esses dois arquivos diretamente pelo navegador. O objetivo desta pasta é substituir essa etapa por um catálogo compacto hospedado no próprio GitHub Pages.

## Regra

Não versionar o dataset bruto completo se ele exceder os limites normais do GitHub. Gere e publique apenas o catálogo compacto necessário ao aplicativo.