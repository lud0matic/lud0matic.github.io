---
layout: post
title:  "iMDb to Tumblr"
date:   2023-07-05 02:44:00 -0300
permalink: /imdb-to-tumblr
image: assets/images/2023-07-05-imdb-to-tumblr/imdb-to-tumblr.png
categories: [Dev]
tags: [Python, CLI]
comments: True
---

Después de mucho pensarlo, editarlo, re-editarlo, subirlo, bajarlo y volverlo a subir, hoy acabo de hacer público mi primer [repo](https://github.com/lud0matic/imdb-to-tumblr) en GitHub.

### Un poco de historia

Desde el 2011 tengo la obsesión (una de tantas) de trackear todas las películas que veo. Para ese entonces había pocas apps que hacían esa función y ninguna me parecía que estaba buena. Así es como nació [https://mubiss.tumblr.com](https://mubiss.tumblr.com).

Basicamente es un <span class="smoothscroll badge badge-primary">tumblelog</span> que contiene los posters de todas las películas que alguna vez vi.

Si bien el concepto de trackear películas (más en el 2023) no es nuevo, lo que si es nuevo para mi es en la manera en que realizo las publicaciones.

Anteriormente, buscaba la tapa de la película en un tamaño grande, lo cual, ya de por si era todo un un logro. Los formatos y tamaños de los posters jamás fueron un standard y si bien, el *aspect ratio* debería ser lo más parecido a un 2:3 (1,5:1), la realidad es que 12 años atrás era raro encontrar posters en buena calidad y gran tamaño.

Conforme fueron pasando los años, las apps de trackeo empezaron a aparecer: Desde [Movist](https://ripppleapp.medium.com/serists-and-movist-s-goodbye-23dffb187dc0) que devino en [Ripple](https://ripppleapp.com/), pasando por [JustWatch](https://www.justwatch.com), [Letterboxd](https://letterboxd.com), [Cinema Time](https://cinematime.app) y vaya a saber cuantas otras. [Trakt.tv](https://trakt.tv), para la época, era el mejor lugar para guardar todo el log de las películas. Tenía una API muy buena y eso hacía que varias desarrolladores terminen usándola en sus proyectos. No hace mucho tiempo lanzaron su [propia app](https://apps.apple.com/app/id1514873602) y, esperanzado de que esté buena, la verdad es que no lo es.

Todo esto seguía reafirmando mi idea inicial: la mejor manera de trackear mis películas era publicando los posters an algun blog y ya. Durante muchos años usé Tumblr y estaba familiarizado con sus *usos y costumbres*.

Como casi siempre pasa, todo inicio de proyecto es divertido pero el hecho de tener que publicarlo manualmente, sumado el paso de los años, devino en algo odioso de mantener.

### Pandemia

Como a varios les habrá pasado, la pandemia nos encontró aislados, con medio católogo de **[ingrese aquí su servicio de streaming favorito]** ya visto, alta cantidad de horas callando al cerebro para que [no piense](https://gastonabril.com.ar/2021/02/12/42-365-dead-cells/) y, por decantación (y *loopeo*), aburridos por sobremanera de la rutina insufrible de hacer todos los días lo mismo. Imposible no quedar al borde del psiquiatrico. Esto fue lo que me pasó a mi pero estoy seguro que varios se pueden sentir reflajados con lo que digo.

Entre una de esas tantas noches largas, mi querido [Tomás](https://twitter.com/s0uls/) publica en el grupo que tenemos en Telegram que había un [curso gratis de Python](https://www.reddit.com/r/learnpython/comments/guu0nq/automate_the_boring_stuff_with_python_online).

![Alt text](../assets/images/2023-07-05-imdb-to-tumblr/SCR-20230705-feug.png#shadow)

El curso era [Automate The Boring Stuff With Python](https://automatetheboringstuff.com). Recordaba el libro perfectamente por la gráfica pero jamás lo había leído. El único acercamiento que tuve con libros de programación fue en la secundaria. "Programación en C" de Byron Gottfried para ser más exactos. Cierro los ojos y puedo ver el volumen del libro y sentir el nivel de aburrimento que me generaba. Jamás lo pude terminar. Mi *miedo* era ese, sentir que con este me iba a pasar lo mismo. Con los años, mi span de atención a las cosa que no me generan cierto atractivo es nulo. Y si bien [Al Sweigart](https://mastodon.social/@AlSweigart) lo lanzó en forma de video tutorial, no dejaba de ser "programadores explicando programación en pandemia". No sé si era el mejor de los planes.

Esto sucedió el 04/06/2020 a las 02:34am. Desde ese entonces hasta el día de hoy no paré de leer/aprender cosas relacionadas a Python (nueva obsesión adquirida <i class="fa-solid fa-square-check" style="color: #77bb41;"></i>) y vivo recomendando el curso como puntapie inicial a la programación en Python.

![Alt text](../assets/images/2023-07-05-imdb-to-tumblr/SCR-20230705-fhqo.png)

### Horas culo

El nombre del libro parecía ir perfectamente de la mano con la sensación que tenía con el blog: estaba completamente aburrido/odiado de hacerlo y sentía que era algo que se podía automatizar perfectamente.

Después de varios días de quemarme las pestañas aprendiendo lo básico de Python y mucho ejercicio en [CodeWars](https://www.codewars.com/), creí que estaba listo para automatizar todo esto que tenía en mente. Que manera de fallar miserablmente.

Pasaron varios meses hasta que tuve el *muscle memory* necesiario para no tener que ir cada dos segundo al curso a ver como se hacía un <span class="smoothscroll badge badge-primary">append</span> a una lista, o fijarme como se recorría un diccionario, o conceptos como el <span class="smoothscroll badge badge-primary">scope</span> de las variables, para que sirve los archivos <span class="smoothscroll badge badge-primary">.env</span>. Que son las <span class="smoothscroll badge badge-primary">enviroments</span>, etc, etc. Y si bien, pasaron tres años y no me considero (ni cerca) de ser desarrolador (y eso que tengo más de 13 años DBA en mi haber), siento que hoy tengo el *mindset* adecuado para poder hacer casi cualquier cosa en Python. Nada que una hojeada a la documentación y varias horas de prueba/error no puedan solucionar cualquier problema.

### Script

Por algún motivo, al momento de idear un script, mi cabeza siempre piensa en algo más parecido a un CLI. Algo para consola. Nada de GUI. ¿Será por haber nacido en los 80s? ¿Por la Commodore 64 a los 6 años? ¿Mucho Linux en la adolescencia? ¿Mucho IRC? (irc.ciudad.com.ar, canal #korn), ¿Haber visto Matrix en el cine cuando se estrenó? La verdad es que no lo sé. Algo de todo eso debe tener la culpa pero la realidad es que encuentro cierca comodidad al usar <i class="fa-solid fa-terminal"></i> la [terminal](https://iterm2.com) ¿La rapidez de no usar el mouse? No sé. Sigo pensando y no sé me acurre nada certero, sólo sé que me gusta. Incluso este .md de texto plano horrendo tiene algo de magia que abrir Wordpress y escribir dentro de Gutenberg no tiene. En fin. La idea de pegar el ID de imdb y que el resto del script haga:

1. Busque el nombre de la película en su idioma original.
2. Su versión en ingles.
3. El nombre del director.
4. El poster de película.
5. Le haga el resize al tamaño que necesito.
6. Y que con todo eso haga un post y me devuelva el link al mismo.

![Alt text](https://github.com/lud0matic/imdb-to-tumblr/raw/master/assets/images/SCR-20230703-rluc.png)

Era ideal pero lo que más me gustó fue el tiempo que tardó en ejecutarse: 5 segundos. De casi, 30 minutos por post/poster a copiar y pegar un id, esperar 5 segundos y taram! <i class="fa-solid fa-wand-magic-sparkles"></i> Posteo hecho. Un antes y un después absoluto.

![Alt text](https://github.com/lud0matic/imdb-to-tumblr/raw/master/assets/images/SCR-20230703-rlrn.png)

Y si bien ~~como me gusta decís "y sí bien"~~ comprendo que todo este script satisface únicamente mis necesidades y quizás llamarlo CLI/app/script, o lo que sea, le queda enorme, la satisfacción de haberlo escrito desde cero y que me haga lo que pretendía que haga, es maravillosa. <i class="fa-solid fa-clover"></i>