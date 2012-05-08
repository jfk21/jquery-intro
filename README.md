# Użyteczne linki

* [HTML5 Doctor](http://html5doctor.com/)


## Zaczynamy

1. Szablon strony – [jQury Intro](http://jsbin.com/ogufuf/edit#javascript,html,live)

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

    $(document).ready(function() {
      $('p').html('ola ma psa');
    });

JS2+

    $('p').css('color', '#f00');

JS3:

    $(function() {
      $('p').html('ola ma psa').css('color', '#f00');
    });

CSS:

    .info { color: #00C; }

JS4:

    $(function() {
      $('p').addClass('info');
    });


Ekperymenty:

* dopisać kilka akapitów


### Uwaga

Od teraz będę pomijał w kodzie Javascript „document ready wrapper”:

    $(function() {
      // kod JS
    });

2. [Szablon z  „document ready wrapper”](http://jsbin.com/ogufuf/2/edit#javascript,html,live)
