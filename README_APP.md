# App Front-End Checklist

[![Participe do chat em https://gitter.im/Front-End-Checklist/Lobby][gitter-image]][gitter-url] [![Versão npm mais recente][npm-image]][npm-url] [![Build status][travis-image]][travis-url] [![Manutenibilidade][codeclimate-maintainability-image]][codeclimate-maintainability-url] [![Cobertura de Testes][codeclimate-coverage-image]][codeclimate-coverage-url] [![Greenkeeper badge][greenkeeper-img]][greenkeeper-url] [![Front‑End_Checklist followed][frontendchecklist-image]][frontendchecklist-url] [![Backers na Open Collective][opencollective-backers-image]][opencollective-backers-url] [![Patrocinadores na Open Collective][opencollective-sponsors-image]][opencollective-sponsors-url]


[![StackShare](https://img.shields.io/badge/tech-stack-0690fa.svg?style=flat)](https://stackshare.io/thedaviddias/front-end-checklist) [![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier)


## Índice

- [Install](#install)
- [Instalação](#instalação)
- [Adicionar uma nova tradução](#adicionarumanovatradução)
- [Contribua](#contribute)
- [Licensa](#licensa)



## Instalação

Para instalar e rodar, abra um terminal e use os seguintes comandos:

```shell
    npm install
    npm start or gulp dev
```
## Utilização


## Adicionar uma nova tradução

Para adicionar uma nova tradução para o Front-End Checklist, você só precisa traduzir os arquivos JSON originais em Inglês para o seu idioma.

- [ ] Duplique a pasta `data/en` e mude o nome da pasta para:
  * jp para Japonês
  * es para Espanhol
  * cn para Chinês
  * fr para Francês

- [ ] Inicie o modo de desenvolvimento do GULP adicionando a opção `--l` e seu idioma

  ```shell
    gulp dev --l jp
  ```

- [ ] Traduza todos os arquivos JSON iniciando na pasta `project`

> Você precisará parar o modo de desenvolvimento, iniciar manualmente `gulp json-rebuild`, e reiniciar o modo dev para poder observar suas mudanças.

- [ ] Atualize o `views/base/header.pug` com a bandeira e url correta (você pode baixar sua bandeira se ainda não estiver em `src/img/flags` no site http://flag-icon-css.lip.is/)

  ```haml
    li.s-header__lang__item
      a(href="/jp")
        img(src="/img/flags/jp.svg" width="20" height="15" alt="Japanese language")
  ```

## Autor

**[David Dias](https://github.com/thedaviddias)**

## Contribua

## Licensa

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ voltar ao topo](#table-of-contents)**



[npm-image]: https://img.shields.io/npm/v/auto-changelog.svg
[npm-url]: https://www.npmjs.com/package/auto-changelog


[travis-image]: https://travis-ci.org/thedaviddias/Front-End-Checklist.svg
[travis-url]: https://travis-ci.org/thedaviddias/Front-End-Checklist

[greenkeeper-img]: https://badges.greenkeeper.io/thedaviddias/Front-End-Checklist.svg
[greenkeeper-url]: https://greenkeeper.io/

[gitter-image]: https://badges.gitter.im/Front-End-Checklist/Lobby.svg
[gitter-url]: https://gitter.im/Front-End-Checklist/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge

[opencollective-backers-image]: https://opencollective.com/front-end-checklist/backers/badge.svg
[opencollective-backers-url]: #backers

[opencollective-sponsors-image]: https://opencollective.com/front-end-checklist/sponsors/badge.svg
[opencollective-sponsors-url]: #sponsors

[frontendchecklist-image]: https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg
[frontendchecklist-url]: https://github.com/thedaviddias/Front-End-Checklist/

[codeclimate-maintainability-image]: https://api.codeclimate.com/v1/badges/55642648e3348bfe38eb/maintainability
[codeclimate-maintainability-url]: https://codeclimate.com/repos/59f3015dd77fc102a50008ee/maintainability

[codeclimate-coverage-image]: https://api.codeclimate.com/v1/badges/55642648e3348bfe38eb/test_coverage
[codeclimate-coverage-url]: https://codeclimate.com/repos/59f3015dd77fc102a50008ee/test_coverage
