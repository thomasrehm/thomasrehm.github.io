---
layout: post
title:  "Debugging of Node.js in Docker container"
date:   2017-06-21 08:18:00
categories: Quicktip
author: Thomas Rehm
---

Nach langer Zeit ein kleiner Quicktip um Node.js Apps in Docker Containern einfach und schnell zu debuggen. Als Debugger hat sich die IDE [*VS Code*](https://code.visualstudio.com/) bewährt.

Um die App im Container im Debug Mode zu starten, benutze das Flag `--inspect`. Allerdings ist der interne Localhost des Containers nicht von außen erreichbar, wenn dieser nicht nach außen exposed wird.
Das ganze Setup erreichst du mit den folgenden Steps:

* Expose den Port `5858` vom Container, entweder per `docker run -p 5858:5858 IMAGENAME` oder per Eintrag in deinem Docker-Compose File
* Starte die Node.js App mit dem Command `node(mon) --inspect=0.0.0.0:5858 index.js`
* Attache VS Code mit folgender Konfiguration:


      {
        "type": "node",
        "request": "attach",
        "name": "Attach",
        "port": 5858,
        "address": "127.0.0.1",
        "restart": true,
        "protocol": "inspector",
        "localRoot": "${workspaceRoot}/pfadzudeinemProjekt",
        "remoteRoot": "/src/",
      }
      
Jetzt hängt sich der VS Code debugger an den Node Prozess und du solltest debuggen können.

Cheers
