# Meu Cinema IMDb

Aplicativo pessoal para explorar um catálogo de filmes, marcar títulos assistidos, registrar filmes sem interesse, manter favoritos/watchlist e excluir filmes por expressões encontradas no título, gêneros e principalmente na sinopse.

## Estrutura atual

- `index.html` — aplicação publicada no GitHub Pages
- `data/catalogo-filmes.json` — catálogo compacto hospedado, quando preenchido
- `data/README.md` — formato e procedimento de atualização da base
- `.nojekyll` — publicação estática direta

## Arquitetura de dados

### Catálogo

O catálogo público é separado dos dados pessoais. O arquivo `data/catalogo-filmes.json` deve conter apenas dados objetivos: IMDb ID, título, ano, gêneros, nota e votos. Quando existir e tiver conteúdo, o app tenta carregá-lo automaticamente. Caso contrário, ainda é possível importar localmente `title.basics.tsv.gz` e `title.ratings.tsv.gz` e manter o catálogo em IndexedDB.

### Dados pessoais — V14

A V14 introduz uma base IndexedDB dedicada chamada `MeuCinemaUserDB`, com três stores:

- `user_movies` — assistido, sem interesse, favorito, watchlist e nota/comentário por IMDb ID;
- `preferences` — expressões de exclusão, exclusões estruturais, preferências e snapshot de compatibilidade do localStorage;
- `cache` — cache dos dados enriquecidos de filmes.

O sistema mantém compatibilidade com o armazenamento legado e migra os estados pessoais existentes para a nova base.

### Backup

A V14 adiciona `Backup completo` e `Restaurar backup`. O backup JSON reúne `user_movies`, `preferences`, `cache` e o localStorage legado, permitindo recuperação integral dos dados pessoais antes da futura sincronização em nuvem.

## Próximas fases

1. preencher `data/catalogo-filmes.json` com o catálogo compacto;
2. consolidar o cache enriquecido;
3. adicionar sincronização opcional via backend, mantendo o GitHub Pages apenas como frontend estático.

> IMDb é marca de seus respectivos proprietários. Este projeto é um catálogo pessoal e não oficial.