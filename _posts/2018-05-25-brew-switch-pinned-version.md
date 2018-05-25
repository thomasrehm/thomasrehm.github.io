---
layout: post
title:  "Switching a pinned version in `brew`"
date:   2018-05-25 08:18:00
categories: Quicktip
author: Thomas Rehm
---

[Brew](https://brew.sh) ist ein toller Package Manager unter MacOS. Punkt. Will man eine Version einer installierten Formula mit einem `brew upgrade` nicht upgraden, sollte man diese spezifische Version `pinnen`. Dies kannst du tun, indem du `brew pin <FORMULA>` ausführst. Nun kannst du auch weiter Versionen installieren, und immer wieder zu deiner Version zurück springen. Die gepinnte Version wird auch beim Cleanup nicht entfernt.

Deine installierten Versionen einer Formula liest du mit `brew info <FORMULA>` aus. Dieser Befehl gibt dir aus, welche Version der Formula gerade aktiv ist, welche gepinnt wurden, und welche sonst noch installiert sind.

Um nun zu einer spezifischen Version zu wechseln reicht es aus `brew switch <FORMULA> <VERSION>` aufzurufen.

Cheers
