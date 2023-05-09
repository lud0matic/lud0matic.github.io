---
layout: post
title:  "Bundle Exec Jekyll Serve"
date:   2023-05-06 01:21:53 -0300
categories: [Dev]
comments: false
---

Que lindo ese momento cuando ya no tenés que googlear o buscar dentro de 200 pestañas abiertas de Stack Overflow como es que se escribe ese comando del terror que deseas memorizar y no sale. Creo que hoy debo haber ejecutado unas 1000 veces la sentencia
```code
bundle exec jekyll serve
```
de las cuales, 999 fueron haciendo copy/paste o buscando como se escribía.

Y si bien no me fui fácil ni intuitivo hacer funcionar [Ruby](https://www.ruby-lang.org/en/) y [Bundler](https://bundler.io), todo terminó en buen puerto.

El mejor *approach* fue corriendo [rbevn](https://github.com/rbenv/rbenv), instalar la versión 3.2.2 de Ruby y modificar el archivo .zshrc para que [Oh My Zsh](https://ohmyz.sh) me lo levante sin problema. Después también vi que lo podía agregar como plug-in e integrarlo.

```bash
plugins=(
  git
  bundler
  dotenv
  macos
  rake
  rbenv
  ruby
)
```
En fin...otra noche aprendiendo a hacer algo que no tenía idea de como se hacía.

Ahora a recordar esa clase de git que hice en plena pandemia para subir todo esto...


~~Termina usando GitHub Desktop~~