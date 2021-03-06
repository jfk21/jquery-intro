# Użyteczne linki

* [HTML5 Doctor](http://html5doctor.com/),
  [HTML5 Element Index](http://html5doctor.com/element-index/)
* [jQuery Selectors](http://refcardz.dzone.com/refcardz/jquery-selectors)
* [jQuery Fundamentals](http://jqfundamentals.com/book/index.html)
* [Learning jQuery](http://www.learningjquery.com/) – Tips, Techniques, Tutorials
  ([learn.jquery.com web site](https://github.com/jquery/learn.jquery.com))
* [Tutorials:Getting Started with jQuery](http://docs.jquery.com/Tutorials:Getting_Started_with_jQuery)


## Zaczynamy

* Szablon strony – [jQury Intro](http://jsbin.com/ogufuf/edit#javascript,html,live)

HTML:
```html
<p>ala ma kota</p>
```
JS1:
```js
$(function() {
  $('p').html('ola ma psa');
});
```

JS2 == JS1:
```js
$(document).ready(function() {
  $('p').html('ola ma psa');
});
```

JS2+
```js
$('p').css('color', '#f00');
```

JS3:
```js
$(function() {
  $('p').html('ola ma psa').css('color', '#f00');
});
```

CSS:
```css
.info { color: #00C; }
```

JS4:
```js
$(function() {
  $('p').addClass('info');
});
```

Ekperymenty:

* dopisać kilka akapitów


## Uwaga

Od teraz będę pomijał „document ready wrapper”:
```js
$(function() {
  // kod JS
});
```

## Drugi przykład – *selectors*, *DOM traversal*

* [Szablon z „document ready wrapper”](http://jsbin.com/ogufuf/2/edit#javascript,html,live)

Źródło danych: [Comparison of web application frameworks](http://en.wikipedia.org/wiki/Comparison_of_web_application_frameworks).

HTML:
```html
<ul id="web-frameworks">
<li>Ruby
  <ul>
  <li>Ruby on Rails
  <li>Sinatra
  </ul>
<li>Python
  <ul>
  <li>Django
  <li>CherryPy
  </ul>
<li>PHP
  <ul>
  <li>CodeIgniter
  <li>CakePHP
  <li>Symphony
  </ul>
</ul>
```

CSS:
```css
.horizontal {
  float: left;
  list-style: none;
  margin: 1em;
}
```

JS1:
```js
$("#web-frameworks > li")
  .addClass("horizontal");
```

CSS:
```css
.sub-list {
  color: #a00;
}
```

JS1+
```js
$("#web-frameworks li:not(.horizontal)")
  .addClass("sub-list");
```

CSS:
```css
.highlight {
  font-weight: bold;
  color: #f00;
}
```

JS1+
```js
$("li:contains(Rails)")
  .first()
  .addClass("highlight");
```

Cały przykład → [jsbin](http://jsbin.com/ogufuf/5/edit)


## Trzeci przykład – *chaining*

HTML
```html
<table id="web-frameworks">
<tr>
  <td>Ruby on Rails
  <td>Ruby
  <td>3.2.3
<tr>
  <td>Sinatra
  <td>Ruby
  <td>1.3.1
<tr>
  <td>Django
  <td>Python
  <td>1.4
<tr>
  <td>CherryPy
  <td>Python
  <td>3.2.2
</table>
```

CSS:
```CSS
td {
  padding: 0.25em 1em;
}
.highlight {
  font-weight: bold;
  color: #f00;
}
```

JS:
```js
$("td:contains(Ruby)")
  .parent()
  .find("td:eq(0)")
  .addClass("highlight")
  .end()
  .find("td:eq(2)")
  .addClass("highlight");
```

Cały przykład → [jsbin](http://jsbin.com/ogufuf/7/edit)


## Przykład czwarty – *events*

* jquery API – [Events](http://api.jquery.com/category/events/)

HTML:
```html
<!doctype html>
<html lang=pl>
<head>
  <meta charset=utf-8>
  <title>jQuery Intro</title>
  <script src="http://code.jquery.com/jquery.min.js">
  </script>
  <style>
  body { font-size: 20px; }
  .button {
    width: 150px; height: 150px;
    background: goldenrod;
    margin: 25px;
  }
  .container {
    width: 200px;
    margin: 25px;
    background: crimson;
  }
  .bgcolor {
    background: sienna;
  }
  </style>
</head>
<body>

<div class=container>
  <div class=button></div>
  <div class=button></div>
  <div class=button></div>
</div>

</body>
</html>
```

JS1:
```js
$(".button").on("click", function() {
  $(this).toggleClass("bgcolor");
});
```

JS2:
```js
var handler = function() {
  $(this).toggleClass("bgcolor");
};
$(".button").on("click", handler);
```

JS3:
```js
$(".button").on({
  mouseenter: function() {
    $(this).addClass("bgcolor");
  },
  mouseleave: function() {
    $(this).removeClass("bgcolor");
  }
});
```

Do elementu *.container* dodajemy funkcję obsługi zdarzenia *click*:

JS4:
```js
var handler = function() {
  $(this).toggleClass("bgcolor");
};
$(".container").on("click", handler);
```

Teraz klikanie zmienia kolor „drabinki”, a nie jak poprzednio kolor kwadratów.

Zmieniamy kod, tak aby klikanie zmieniało kolor kwadratów.
W tym celu podmieniamy ostatni wiersz w kodzie powyżej na:

JS5:
```js
$(".container").on("click", ".button", handler);
```

Dodaliśmy jedną funkcję obsługi zdarzenia.
Poprzednio (JS1–JS3) dodawaliśmy trzy te same funkcje.

Cały przykład → [jsbin](http://jsbin.com/ogufuf/11/edit)
