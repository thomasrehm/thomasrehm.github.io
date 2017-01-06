---
layout: post
title:  "TeX Remove dots after section numbers"
date:   2017-01-06 14:18:00
categories: Allgemein
author: Thomas Rehm
---

Mal wieder ein kleiner LaTeX Trick: Um die Punkte hinter der Section Nummerierung zu entfernen, also 4.1.1 statt 4.1.1., benutze das Attribut ```numbers=noenddot``` in der Preambel zu deinem Dokument:

	\documentclass[
	    english,
	    a4paper,
	    numbers=noenddot,
	    ...
	]{scrreprt}


Ich habe die Lösung im folgenden Thread auf [tex.stackexchange.com](http://tex.stackexchange.com/questions/27250/remove-dot-after-number-in-figure-captions-while-keeping-the-dot-in-chapter-sect) gefunden.

Happy TeXing!
