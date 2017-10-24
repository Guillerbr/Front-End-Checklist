# Front-End Checklist

[![Participe do chat em https://gitter.im/Front-End-Checklist/Lobby](https://badges.gitter.im/Front-End-Checklist/Lobby.svg)](https://gitter.im/Front-End-Checklist/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
[![Contributors](https://img.shields.io/github/contributors/thedaviddias/Front-End-Checklist.svg)](https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors)
[![StackShare](https://img.shields.io/badge/tech-stack-0690fa.svg?style=flat)](https://stackshare.io/thedaviddias/front-end-checklist)
[![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

A **Front-End Checklist** é uma lista exaustiva de todos elementos que você precisa ter / testar antes de lançar seu site / página HTML em produção.

Ela é baseada em anos de experiência de desenvolvedores Front-End, com as adições provenientes de outras checklists open-source.

## Índice

1. **[Head](#head)**
2. **[HTML](#html)**
3. **[Webfonts](#webfonts)**
4. **[CSS](#css)**
5. **[Imagens](#imagens)**
6. **[JavaScript](#javascript)**
7. **[Segurança](#segurança)**
8. **[Performance](#performance)**
9. **[Acessibilidade](#acessibilidade)**
10. **[SEO](#seo)**

## Como usar?

Todos itens na **Front-End Checklist** são necesários na maioria dos projetos, mas alguns elementos podem ser omitidos ou não são tão essenciais (no caso da administração de um aplicativo web, você pode não precisar de um feed RSS por exemplo). Nós escolhemos três níveis de flexibilidade:

* ![Baixa][low_img] significa que o item é **recomendado** mas pode ser omitido em algumas situações em particular.
* ![Média][medium_img] significa que o item é **altamente recomendado** e pode eventualmente ser omitido em alguns casos realmente particulares. Alguns elementos, se omitidos, podem ter más repercussões em termos de performance ou SEO.
* ![Alta][high_img] significa que o item **não pode ser omitido** por qualquer razão. Você pode causar uma disfunção na sua página ou ter problemas com acessibilidade ou SEO. A prioridade dos testes precisa estar nestes elementos primeiro.

Alguns recursos possuem um emoticon para ajudar você a entender qual tipo de conteúdo / ajuda você pode encontrar na checklist:

* 📖: documentação ou artigo
* 🛠: ferramenta online / ferramenta de teste
* 📹: mídia ou conteúdo em vídeo

---

## Head

> **Notas:** Você pode acessar [uma lista com tudo](https://github.com/joshbuchea/HEAD) que poderia ser encontrado na `<head>` de um document HTML.

### Meta tag

* [ ] **Doctype:** ![Alta][high_img] O Doctype é HTML5 e está no topo de todas as suas páginas HTML.

```html
<!-- Doctype HTML5 -->
<!doctype html>
```

> 📖 [Determinando o encoding de caracteres - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

*A próximas 3 meta tags (Charset, X-UA Compatible e Viewport) precisam vir primeiro no head.*

* [ ] **Charset:** ![Alta][high_img] O charset declarado (UTF-8) é corretamente declarado.

```html
<!-- Determine o encoding de caracteres para o document -->
<meta charset="utf-8">
```

* [ ] **X-UA-Compatible:** ![Média][medium_img] A meta tag X-UA-Compatible está presente.

```html
<!-- Instrua o Internet Explorer a usar seu mais recente engine de renderização -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
```

> 📖 [Especificando modos legados de document (Internet Explorer)](https://msdn.microsoft.com/en-us/library/jj676915(v=vs.85).aspx)

* [ ] **Viewport:** ![Alta][high_img] A viewport é corretamente declarada.

```html
<!-- Viewport para web design responsivo -->
<meta name="viewport" content="width=device-width, initial-scale=1">
```

* [ ] **Title:** ![Alta][high_img] Um título é usado em todas páginas (SEO: Google calcula a largura em píxel dos caracteres usados no título, cortados entre 472 e 482 píxels. O limite médio de caracteres seria em torno de 55-caracteres).

```html
<!-- Título do Document -->
<title>Título de Página menor que 65 caracteres</title>
```

> 📖 [Título - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)

* [ ] **Descrição:** ![Alta][high_img] Uma meta decrição é providenciada, é única e não possui mais de 150 caracteres.

```html
<!-- Meta Descrição -->
<meta name="description" content="Descrição da página com menos de 150 caracteres">
```

* [ ] **Favicons:** ![Média][medium_img] Cada favicon foi criado e é exibido corretamente. Se você tem apenas um `favicon.ico`, ponha-o na raiz do seu site. Normalmente você não precisa usar nenhum markup. Entretanto, ainda é uma boa prática linkar ele usando o exemplo abaixo. Atualmente, **o formato PNG é recomendado** ao invés do formato `.ico` (dimensões: 32x32px).

```html
<!-- Standard favicon -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- Recommended favicon format -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
```

> * 🛠 [Favicon Generator](https://www.favicon-generator.org/)
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
> * 📖 [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet)
> * 📖 [Favicons, Touch Icons, Tile Icons, etc. Qual Você Precisa? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
> * 📖 [PNG favicons - caniuse](https://caniuse.com/#feat=link-icon-png)

* [ ] **Apple Touch Icon:** ![Baixa][low_img] Apple touch favicon `apple-mobile-web-app-capable` está presente. *(Crie seu arquivo Apple Icon com pelo menos dimensão 200x200px para dar suporte a todas dimensões que você pode precisar)*

```html
<!-- Apple Touch Icon -->
<link rel="apple-touch-icon" href="/custom-icon.png">
```

> 📖 [Configurando Aplicações Web](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

- [ ] **Windows Tiles:**![Baixa][low_img] Windows tiles estão presentes e linkadas.

```html
<!-- Microsoft Tiles -->
<meta name="msapplication-config" content="browserconfig.xml" />
```

O markup xml mínimo necessário para o arquivo browserconfig.xml é como segue:

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

> 📖 [Referência de configuração de schema do browser](https://msdn.microsoft.com/en-us/library/dn320426(v=vs.85).aspx)

* [ ] **Canonical:** ![Média][medium_img] Use `rel="canonical"` para evitar conteúdo duplicado.

```html
<!-- Ajuda a evitar problemas com conteúdo duplicado -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-red.html">
```

### Tags HTML

* [ ] **Language tag:** ![Alta][high_img] A tag de idioma do seu website é especificada e relacionada ao idioma atual da página.

```html
<!-- Indicamos o idioma definido para a página atual -->
<html lang="pt-br">
```

* [ ] **Direction tag:** ![Média][medium_img] A direção de leitura é especificada na tag body (Pode ser usada em outra tag HTML).

```html
<!-- Indicamos a direção de leitura (rtl é sigla para right to left, isto é, da direita para a esquerda) -->
<html dir="rtl">
```

> 📖 [dir - HTML - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **Idioma alternativo:** ![Baixa][low_img] A tag de idioma do seu website é especificada e relacionada ao idioma atual da página.

```html
<!-- Indicamos o idioma definido para a página atual -->
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

* [ ] **Comentários condicionais:** ![Baixa][low_img] Comentários condicionais são presentes para o IE se necessário.

> 📖 [Sobre comentários condicionais (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)

* [ ] **RSS feed:** ![Baixa][low_img] Se seu projeto é um blog ou possui artigos, foi providenciado o link do RSS.

* [ ] **CSS Crítico:** ![Média][medium_img] O CSS crítico (ou "above the fold") coleta todo CSS usado para renderizar a porção visível da página. Ele é embutido antes da chamada CSS principal e entre `<style></style>` numa linha única (minificado).

> 🛠 [Critical por Addy Osmani no Github](https://github.com/addyosmani/critical)

* [ ] **Ordem CSS:** ![Alta][high_img] Todos os arquivos CSS são carregados antes de quaisquer arquivos JavaScript files no `<head>`. (Exceto o caso onde, algumas vezes, arquivos JS são carregados assíncronamente no topo da página).

### Social meta

***Facebook OG*** e ***Twitter Cards*** são, para qualquer website, altamente recomendados. As outras tags de mídia social podem ser consideradas se seu público-alvo tem uma presença em particular nelas, e você quer se assegurar de exibí-las.

* [ ] **Facebook Open Graph:** ![Baixa][low_img] Todos os Facebook Open Graph (OG) são testados e nenhum está faltando ou com informações falsas. Imagens precisam ter no mínimo 600 x 315 píxels, 1200 x 630 píxels recomendados.

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
```

> * 📖 [A Guide to Sharing for Webmasters](https://developers.facebook.com/docs/sharing/webmasters/)
> * 🛠 Teste sua página com o [Facebook OG testing](https://developers.facebook.com/tools/debug/)

* [ ] **Twitter Card:** ![Baixa][low_img]

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Descrição de conteúdo com menos de caracteres">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

> * 📖 [Getting started with cards — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
> * 🛠 Teste sua página com o [Twitter card validator](https://cards-dev.twitter.com/validator)

**[⬆ voltar ao topo](#índice)**

---

## HTML

### Melhores práticas

* [ ] **HTML5 Semantic Elements:** ![Alta][high_img] HTML5 Semantic Elements são usados apropriadamente (header, section, footer, main...).

> 📖 [HTML Reference](http://htmlreference.io/)

* [ ] **Páginas de erro:** ![Alta][high_img] Páginas para Error 404 e 5xx existem. Lembre-se de que páginas de erro 5xx precisam ter seu CSS integrado (sem chamadas externas no servidor atual).

* [ ] **Noopener:** ![Média][medium_img] Caso você esteja usando links externos com `target="_blank"`, seu link deveria ter um atributo `rel="noopener"` para prevenir tab nabbing. Se você precisa suportar versões mais antigas do Firefox, use `rel="noopener noreferrer"`.

> 📖 [Sobre rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

* [ ] **Retirando comentários:** ![Baixa][low_img] Código desnecessário precisa ser removido antes de enviar a página para produção.

### HTML testing

* [ ] **W3C compliant:** ![Alta][high_img] Todas as páginas precisam ser testadas com o validador W3C para identificar possíveis problemas no código HTML.

> 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** ![Alta][high_img] Eu uso ferramentas para me ajudar a analisar quaisquer problemas que eu poderia ter com meu código HTML.

> 🛠 [Dirty markup](https://dirtymarkup.com/)

* [ ] **Navegadores Desktop:** ![Alta][high_img] Todas as páginas foram testadas em todos navegadores desktop atuais (Safari, Firefox, Chrome, Internet Explorer, EDGE...).
* [ ] **Navegadores Mobile:**  ![Alta][high_img] Todas as páginas foram testadas em todos navegadores mobile atuais (Native browser, Chrome, Safari...).

* [ ] **Verificador de Link:** ![Alta][high_img] Não há links quebrados na minha página, verifique que você não tem nenhum erro 404.

> 🛠 [W3C Link Checker](https://validator.w3.org/checklink)

* [ ] **Teste Adblockers:** ![Média][medium_img] Seu website mostra o conteúdo corretamente com adblockers habilitados (Você pode providenciar uma mensagem encorajando os usuários a desabilitar o adblocker).

- [ ] **Pixel perfect:** ![Alta][high_img] Páginas estão alinhadas com o que foi desenhado. Dependendo da quantidade de profisionais criativos, pode não ser 100% exato, mas sua página precisa estar próxima ao seu template.

> [Pixel Perfect - Extensão Chrome](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

**[⬆ voltar ao topo](#índice)**

---

## Webfonts

* [ ] **Formato de webfont:** ![Alta][high_img] WOFF, WOFF2 e TTF são suportados por todos os navegadores modernos.

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff).
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType e OpenType font support](https://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Tamanho de webfont:** ![Alta][high_img] Tamanhos de webfont não excedem 2 MB (todas variantes incluídas).

**[⬆ voltar ao topo](#índice)**

---

## CSS

> **Notas:** Dê uma olhada em [Guidelines CSS](https://cssguidelin.es/) e [Guidelines Sass](https://sass-guidelin.es/) seguidas pela maioria dos desenvolvedores Front-End. Se você tem alguma dúvida sobre propriedades CSS, você pode visitar a [CSS Reference](http://cssreference.io/).

* [ ] **Web Design Responsivo:** ![Alta][high_img] O website está usando web design responsivo.
* [ ] **CSS Print:** ![Média][medium_img] Uma stylesheet de impressão correta é providenciada em cada página.
* [ ] **Preprocessors:** ![Média][medium_img] Sua página está usando um preprocessor CSS (preferencialmente [Sass](http://sass-lang.com/)).
* [ ] **Unique ID:** ![Alta][high_img] Se IDs são usados, eles são únicos à página.
* [ ] **Reset CSS:** ![Alta][high_img] Um CSS reset (reset, normalize ou reboot) está em uso e atualizado. *(Se você está usando um Framework CSS como Bootstrap ou Foundation, o Normalize já está incluído.)*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **JS prefix:** ![Baixa][low_img] Todas as classes (ou id- usados em arquivos) begin with **js-** e are not styled into the CSS files.

```html
<div id="js-slider" class="my-slider">
<!-- ou -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **CSS embed ou line:** ![Alta][high_img] Evite a todo custo o uso de CSS embutido ou inline: apenas utilizado por razões válidas (ex: background-image para slider, CSS critical).
* [ ] **Vendor prefixes:** ![Alta][high_img] CSS vendor prefixes são usados e gerados de acordo com sua compatibilidade e suporte a navegadores.

> 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### Performance

- [ ] **Concatenation:** ![Alta][high_img] Arquivos CSS são concatenados num arquivo único. *(Não para HTTP/2)*
- [ ] **Minification:** ![Alta][high_img] Todos arquivos CSS são minificados.
- [ ] **Non-blocking:** ![Média][medium_img] Arquivos CSS precisam ser non-blocking para prevenir o DOM de tirar tempo para carregar.

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
> * 📖 [Example of preload CSS usando loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **Unused CSS:** ![Baixa][low_img] Remover CSS inutilizado.

> * 🛠 [UnCSS Online](https://uncss-online.com/) 🛠
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [Chrome DevTools Coverage](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)


### CSS testing

* [ ] **Stylelint:** ![Alta][high_img] Todos arquivos CSS ou SCSS estão sem nenhum erros.

> * 🛠 [stylelint, a CSS linter](https://stylelint.io/)
> * 📖 [Sass guidelines](https://sass-guidelin.es/)

* [ ] **Responsive web design:** ![Alta][high_img] Todas as páginas foram testatas nos seguintes breakpoints: 320px, 768px, 1024px (podem ser mais / diferentes de acordo com seu analytics).

* [ ] **CSS Validator:** ![Média][medium_img] O CSS foi testado e erros pertinentes foram corrigidos.

> 🛠 [CSS Validator](https://jigsaw.w3.org/css-validator/)

* [ ] **Reading direction:** ![Alta][high_img] Todas as páginas precisam ser testadas para idiomas LTR e RTL se elas precisarem dar esse suporte.

> * 📖 [Building RTL-Aware Web Apps & Websites: Part 1 - Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
> * 📖 [Building RTL-Aware Web Apps & Websites: Part 2 - Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ voltar ao topo](#índice)**

---

## Imagens

> **Notas:** Para um entendimento completo de otimização de imagem, veja o ebook grátis **[Essential Image Optimization](https://images.guide/)**, do Addy Osmani.

### Melhores práticas

* [ ] **Optimization:** ![Alta][high_img] Todas as imagens são otimizadas para renderização no navegador. Formato WebP poderia ser usado para páginas críticas (como a Homepage).

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Use [ImageOptim](https://imageoptim.com/) to optimise your images for free.

* [ ] **Retina:** ![Baixa][low_img] Você providencia imagens em layout x2 ou 3x, e suporta retina display.
* [ ] **Sprite:** ![Média][medium_img] Imagens pequenas estão num arquivo sprite (no caso de ícones, eles podem estar num sprite SVG).
* [ ] **Width e Height:** ![Alta][high_img] Todas tags `<img>` têm valores para altura e largura (Não especifique em px ou %).

> ***Nota:*** Vários desenvolvedores assumem que altura e largura não são compatíveis com design web responsivo. Absolutamente não é o caso.

* [ ] **Texto alternativo:** ![Alta][high_img] Todas tags `<img>` têm um texto alternativo que as descreve visualmente.
* [ ] **Lazy loading:** ![Média][medium_img] Imagens são lazyloaded (Um noscript fallback é sempre providenciado).

**[⬆ voltar ao topo](#índice)**

---

## JavaScript

### Melhores práticas

* [ ] **JavaScript Inline:** ![Alta][high_img] Você não tem nenhum código JavaSScript inline (misturado com seu código HTML, por exemplo).
* [ ] **Concatenation:** ![Alta][high_img] Arquivos JavaScript são concatenados.
* [ ] **Minification:** ![Alta][high_img] Arquivos JavaScript são minificados (você pode adicionar o sufixo `.min`).

> [Minify Resources (HTML, CSS, e JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **JavaScript security:**

> [Guidelines for Developing Secure Applications Utilizing JavaScript](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)*

* [ ] **Non-blocking:** ![Média][medium_img] Arquivos JavaScript são carregados assíncronamente usando atributo `async` ou deferidos usando atributo `defer`.

> 📖 [Remove Render-Blocking JavaScript](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Modernizr:** ![Baixa][low_img] Se você precisa visar features específicas, é possível usar um Modernizr custom para adicionar classes na sua tag `<html>`.

> 🛠 [Customize seu Modernizr](https://modernizr.com/download?setclasses)

### JavaScript testing

* [ ] **ESLint:** ![Alta][high_img] Nenhum erro é visível pelo ESLint (baseando-se nas sua configuração ou regras pré-estabelecidas).

> * 📖 [ESLint - The pluggable linting utility for JavaScript e JSX](https://eslint.org/)

**[⬆ voltar ao topo](#índice)**

---

## Segurança

### Scaneie e cheque seu website

> * [securityheaders.io](https://securityheaders.io/)
> * [Observatory por Mozilla](https://observatory.mozilla.org/)
> * [ASafaWeb - Automated Security Analyser for ASP.NET Websites](https://asafaweb.com/)

### Melhores práticas

* [ ] **HTTPS:** ![Média][medium_img] HTTPS é usado em todas as páginas e para todo conteúdo externo (plugins, imagens...).

> * 🛠 [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
> * 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
> * 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

* [ ] **HTTP Strict Transport Security (HSTS):** ![Média][medium_img] O header HTTP está configurado com 'Strict-Transport-Security'.

> * 🛠 [Check HSTS preload status and eligibility](https://hstspreload.org/)
> * 📖 [HTTP Strict Transport Security Cheat Sheet - OWASP](https://www.owasp.org/index.php/HTTP_Strict_Transport_Security_Cheat_Sheet)
> * 📖 [Transport Layer Protection Cheat Sheet - OWASP](https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet)

* [ ] **Cross Site Request Forgery (CSRF):** ![Alta][high_img] Você está certo de que requests feitas pro seu server-side são legítimas e originadas do seu website / app para prevenir ataques CSRF.

> 📖 [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet)

* [ ] **Cross Site Scripting (XSS):** ![Alta][high_img] Sua página ou website está livre de possíveis problemas com XSS.

> * 📖 [XSS (Cross Site Scripting) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet)
> * 📖 [DOM based XSS Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet)

* [ ] **Content Type Options** ![Média][medium_img] Previne Google Chrome e Internet Explorer de tentar aplicar mime-sniff no content-type de uma response em relação ao que foi declarado no server.

> * 📖 [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

* [ ] **X-Frame-Options (XFO)** ![Média][medium_img] Protege seus visitantes contra ataques clickjacking.

> * 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
> * 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

**[⬆ voltar ao topo](#índice)**

---

## Performance

### Melhores práticas

- [ ] **Weight page:** ![Alta][high_img] O peso de cada página está entre 0 e 500 KB.

> * 🛠 [Website Page Analysis](https://tools.pingdom.com)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Minified:** ![Média][medium_img] Seu HTML está minificado.
> 🛠 [W3C Validator](https://validator.w3.org/)

* [ ] **Lazy loading:** ![Média][medium_img] Imagens, scripts e CSS precisam ser carregados de modo lazy para melhorar o tempo de resposta da página atual (Veja detalhes nas seções respectivas).

* [ ] **Cookie size:** Se você está usando cookies, certifique-se de que cada não excede 4096 bytes e que seu domain name não tem mais de 20 cookies.

> * 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
> * 📖 [Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
> * 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

### Preparando requests encaminhadas

> 📖 [Explicação das técnicas seguintes](https://css-tricks.com/prefetching-preloading-prebrowsing/)

* [ ] **DNS resolution:** ![Baixa][low_img] DNS de serviços de terceiros que podem ser necessários são adiantadamente preparados durante tempo ocioso, usando `dns-prefetch`.

```html
<link rel="dns-prefetch" href="https://example.com">
```

* [ ] **Preconnection:** ![Baixa][low_img] DNS lookup, TCP handshake e negociação TLS com serviços que serão necessários em breve, são ambos feitos adiantadamente durante tempo ocioso, usando `preconnect`.

```html
<link rel="preconnect" href="https://example.com">
```

* [ ] **Prefetching:** ![Baixa][low_img] Recursos que serão necessários em breve (ex.: imagens em lazy loading) são requisitados adiantadamente durante tempo ocioso, usando `prefetch`.

```html
<link rel="prefetch" href="image.png">
```

* [ ] **Preloading:** ![Baixa][low_img] Recursos necessários na página atual (ex.: scripts colocados no fim do `<body>`) adiantadamente usando `preload`.

```html
<link rel="preload" href="app.js">
```

> 📖 [Difference between prefetch e preload](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### Performance testing

* [ ] **Google PageSpeed:** ![Alta][high_img] Todas suas páginas foram testadas (não só a homepage) e têm um score de pelo menos 90/100.

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Teste sua velocidade mobile com Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Teste de Performance e Otimização de Website](https://www.webpagetest.org/)

**[⬆ voltar ao topo](#índice)**

---

## Acessibilidade

> **Notas:** Você pode assistir a playlist [A11ycasts com Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### Melhores práticas

- [ ] **Melhoramento progressivo:** ![Média][medium_img] Funcionalidades extensivas como a navegação principal e busca deveriam funcionar sem JavaScript habilitado.

> 📖 [Habilitar / Desabiloitar JavaScript no Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Contraste de cor:** ![Média][medium_img] Contraste de cores deveria pelo menos passar WCAG AA (AAA para mobile).

> 🛠 [Taxa de contraste](https://leaverou.github.io/contrast-ratio/)

#### Cabeçalhos

* [ ] **H1:** ![Alta][high_img] Todas as páginas têm uma tag H1 que não é o título do website.
* [ ] **Cabeçalhos:** ![Alta][high_img] Cabeçalhos deveriam ser usados apropriadamente, na ordem correta (H1 até H6).

> 📹 [Por que cabeçalhos e landmarks são tão importantes -- A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

#### Landmarks

- [ ] **Role banner:** ![Alta][high_img] `<header>` tem `role="banner"`.
- [ ] **Role navigation:** ![Alta][high_img] `<nav>` tem `role="navigation"`.
- [ ] **Role main:** ![Alta][high_img] `<main>` tem `role="main"`.

> 📖 [Usando landmarks ARIA para identificar regiões de uma página](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page)

### Semantics

- [ ] **Inputs HTML5 específicos são utilizados:** ![Média][medium_img] Isto é *especialmente* importante para **devices mobile**, que mostram keypads e widgets customizados para diferentes tipos de input.

> 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Form

* [ ] **Label:** ![Alta][high_img] Uma label é associada a cada input de um formulário. Caso uma label não possa ser exibida, use `aria-label`.

> 📖 [Usando o atributo aria-label - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### Accessibility testing

* [ ] **Testando padrões de Acessibilidade:** ![Alta][high_img] Use a ferramenta WAVE para testar se sua página respeita os padrões de acessibilidade.

> 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **Navegação por Teclado:** ![Alta][high_img] Teste seu website usando apenas seu teclado numa ordem previsível. Todos elementos interativos são alcançáveis e utilizáveis.
* [ ] **Screen-reader:** ![Média][medium_img] Todas as páginas foram testadas num screen-reader (VoiceOver, ChromeVox, NVDA ou Lynx).
* [ ] **Estilo de Foco:** ![Alta][high_img] Se o foco está desabilitado, ele é substituído por um estado visível em CSS.

> 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ voltar ao topo](#índice)**

---

## SEO

* [ ] **Google Analytics:** ![Alta][high_img] Google Analytics é corretamente instalado e configurado.
* [ ] **Headings logic:** ![Média][medium_img] Texto de cabeçalho ajuda a entender o conteúdo da página atual.
* [ ] **sitemap.xml:** ![Alta][high_img] Um sitemap.xml existe e foi submetido ao Google Search Console (anteriormente Google Webmaster Tools).
* [ ] **robots.txt:** ![Alta][high_img] O robots.txt não está bloqueando webpages.

> * 🛠 Test your robots.txt with [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)

* [ ] **Dados Estruturados:** ![Alta][high_img] Páginas usando dados estruturados são testadas e não possuem erros. Dados estruturados ajudam crawlers a entender o conteúdo da página atual.

> * 📖 [Introdução a Dados Estruturados - Search - Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> * 🛠 Teste sua página com o [Structured Data Testing Tool](https://developers.google.com/structured-data/testing-tool/)

* [ ] **Sitemap HTML:** ![Média][medium_img] Um sitemap HTML é providenciado e acessível via um link no rodapé do seu website.

> * 📖 [Sitemap guidelines - Google Support](https://support.google.com/webmasters/answer/183668?hl=en)
> * 🛠 [Sitemap generator](https://websiteseochecker.com/html-sitemap-generator/)


**[⬆ voltar ao topo](#índice)**

---

## Translation

O Front-End Checklist também está disponível em outros idiomas. Obrigado a todos tradutores por seu incrível trabalho!

* 🇯🇵 Japonês: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)
* 🇪🇸 Espanhol: [eoasakura/Front-End-Checklist-ES](https://github.com/eoasakura/Front-End-Checklist-ES)
* 🇨🇳 Chinês: [JohnsenZhou/Front-End-Checklist](https://github.com/JohnsenZhou/Front-End-Checklist)
* 🇰🇷 Coreano: [kesuskim/Front-End-Checklist](https://github.com/kesuskim/Front-End-Checklist)

---

## Front-End Checklist Badge

Se você quer mostrar que está seguindo as regras do Front-End Checklist, ponha esta badge no seu arquivo README!

➔ [![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)

```md
[![Front‑End_Checklist followed](https://img.shields.io/badge/Front‑End_Checklist-followed-brightgreen.svg)](https://github.com/thedaviddias/Front-End-Checklist/)
```

**[⬆ voltar ao topo](#índice)**

---

## Contribuindo

**Abra uma issue ou uma pull request para sugerir mudanças ou adições.**

### Guia

O [repositório original do **Front-End Checklist**](https://github.com/thedaviddias/Front-End-Checklist) consiste em duas branches:

#### 1. `master`

Esta branch consiste no arquivo `README.md` que é automaticamente refletido no website [Front-End Checklist](http://frontendchecklist.com/).

#### 2. `develop`

Esta branch será usada para fazer algumas mudanças significativas à estrutura, conteúdo se necessário. É preferível usar a branch master para arrumar erros pequenos ou adicionar um novo item.

### Contribuidores

Veja todos os incríveis [contribuidores](https://github.com/thedaviddias/frontendchecklist/graphs/contributors).

## Suporte

Se você tem alguma pergunta ou sugestão, não hesite em usar o Gitter ou Twitter:

* [Chat no Gitter](https://gitter.im/Front-End-Checklist/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)
* [Twitter](https://twitter.com/thedaviddias)

## Autores

**[David Dias](https://github.com/thedaviddias/Front-End-Checklist)**

## Licença

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ voltar ao topo](#índice)**

[low_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png
[medium_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png
[high_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png
