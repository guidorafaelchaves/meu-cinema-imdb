# Meu Cinema IMDb

Aplicativo pessoal para explorar um catálogo de filmes, marcar títulos assistidos, registrar filmes sem interesse, manter favoritos/watchlist e excluir filmes por expressões encontradas no título, gêneros e principalmente na sinopse.

## Estrutura

- `index.html` — interface do GitHub Pages
- `styles.css` — estilos
- `app.js` — lógica do catálogo e histórico pessoal
- `data/catalogo-filmes.json` — catálogo compacto opcional, carregado automaticamente quando publicado
- `data/README.md` — formato e procedimento para atualizar a base
- `backup/meu_cinema_imdb_v12.html` — referência da versão local estável

## Dados IMDb

O aplicativo não precisa hospedar os datasets brutos do IMDb. O arquivo `title.basics.tsv.gz` é grande demais para ser uma boa dependência de GitHub Pages. A estratégia do projeto é gerar um `data/catalogo-filmes.json` compacto apenas com os campos necessários ao app: IMDb ID, título, ano, gêneros, nota e votos.

Se `data/catalogo-filmes.json` existir, a página tenta carregá-lo automaticamente. Caso contrário, o usuário pode importar `title.basics.tsv.gz` e `title.ratings.tsv.gz` localmente pelo navegador e manter o catálogo em IndexedDB.

## Publicação

O projeto é estático e compatível com GitHub Pages. Publique a branch `main` a partir da raiz (`/`).

> IMDb é marca de seus respectivos proprietários. Este projeto é um catálogo pessoal e não oficial.