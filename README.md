# Użyteczne linki

* [HTML5 Doctor](http://html5doctor.com/)
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

## Drugi przykład

* [Szablon z „document ready wrapper”](http://jsbin.com/ogufuf/2/edit#javascript,html,live)
