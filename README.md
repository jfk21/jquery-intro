# Użyteczne linki

* [HTML5 Doctor](http://html5doctor.com/)


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
