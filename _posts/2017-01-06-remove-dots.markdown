---
layout: post
title:  "TeX Remove dots after section numbers"
date:   2017-01-06 14:18:00
categories: Allgemein
author: Thomas Rehm
---


Die Arbeit mit Latex macht mir auf der einen Seite Spaß – andererseits treibt sie mich manchmal etwas in den Wahnsinn. So auch wieder beim Setzen eines Wissenschaftlichen Papers…

Wie bekomme ich das Wort "Literatur" bzw. "References", das per Babel mittels ```\refname``` als Section-Titel automatisch eingefügt werden soll, komplett in UpperCase Buchstaben gesetzt? "Nimmste ```\uppercase{…}```", dachte ich mir, aber das ist wohl doch nicht so einfach. Die einfachen ```\uppercase{…}``` bzw. ```\lowercase{…}``` Anweisungen bringen mir nicht den gewünschten Output. Nach einigem Suchen komme ich also auf die Idee das Package [textcase](http://ctan.org/pkg/textcase) einzubinden um mit dessen Hilfe den Befehl ```\MakeUppercase{…}``` verwenden zu können. Klappt natürlich auch nicht, da sich die Anweisung nicht in Verbindung mit dem ```hyperref``` Package in einer Referenz (also dem Section-Titel) nutzen lässt.

Nach einigem Suchen, hier nun die Lösung:

Weise Latex an, den String ```\MakeUppercase{…}``` für hyperref und die PDF Generierung zu entfernen:

	\def\texorpdf #1#2{\texorpdfstring{#1{#2}}{#2}}

Und dieser Befehl wird dann wie folgt eingesetzt:

	\section{\texorpdf\MakeUppercase{\refname}}

Eine Erklärung zu ```\texorpdfstring``` findet sich im [hyperref Manual](https://www.tug.org/applications/hyperref/manual.html#x1-170004.1.2).

Ich habe die Lösung im folgenden Thread auf [Google Groups](https://groups.google.com/forum/#!topic/comp.text.tex/pRnh24H1XJI) gefunden.

Happy TeXing!
