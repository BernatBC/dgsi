---
title: "Més sistemes i eficiencia"
date: 2025-03-18T11:30:03+00:00
description: Més informació sobre els sistemes, i perquè no cal obtenir una major eficiència
slug: dimarts-18-marc
image: nosql.png
categories:
    - Teoria
tags:
---

## Integritat dels sistemes
La classe va començar amb un petit repàs sobre la missió, visió, objectius, estructura, etc. de les empreses, remarcant l'exemple del bar de la FIB. En aquest repàs, va sortir "Sistemes d'informació" d'una empresa, i és en aquest apartat on ens va parlar sobre els _fluxos d'informació_ i els _magatzems d'informació_ estructurats previs al 2025. Ens va explicar sobre la lentitud de les bases relacionals SQL, causat per la normalització i el manteniment de la integritat. És lent ja que les transaccions han de ser atòmiques, per tal de mantenir-la. Segons els casos, no et queda altra manera de fer-ho. Per exemple, quan compres un bitllet d'avió per internet, t'has d'assegurar que no hi hagi dues persones que comprin un mateix seient a la vegada. Així i tot, quan una aplicació necessita ser ràpida, has de trencar aquesta integritat i normalització. D'aquí van sortir les bases de dades NoSQL, que són ràpides i permet escalar les transferències, desnormalitzant i perdent la integritat. El que realment em va sorprendre, és que puguis obtenir els mateixos resultats utilitzant una base de dades SQL. Desconeixia completament que van sorgir aquestes bases de dades per prevenir el bloqueig mental de les persones quan havien de desnormalitzar aquestes bases de dades.

## Mermaid
La part de la classe on he après un concepte que em serà d'utilitat, és quan en Marc ha comentat l'eina [Mermaid](https://mermaid.js.org/). Aquesta eina et permet fer tota mena de diagrames mitjançant text, en comptes de ser una eina visual utilitzada amb el ratolí. El dia [Dijous 27 Febrer](/dgsi/post/dijous-27-febrer) ja vaig comentar que feia servir [gohugo](https://gohugo.io/) per a la meva pàgina web, i va ser a la [documentació](https://toha-guides.netlify.app/posts/writing-posts/mermaid) del tema que utilitzo d'on vaig sentir per primera vegada sobre mermaid. Tot i així, no n'hi havia fet gaire cas, i no l'he utiltzat mai. Després de la recomanació d'en Marc, segurament el començaré a fer servir, en comptes de [draw.io](https://app.diagrams.net/).

## No sempre cal ser més eficient
La part final de la classe tractava sobre el fet que no sempre cal ser eficient, ja que en alguns casos, buscar la màxima eficiència pot no ser necessària ni beneficiosa. Mentre en Marc ho explicava, tot em feia pensar sobre la manera de fer les coses del meu germà, despreocupant-se de tot. Sobretot en l'exemple d'ordenar el rentavaixella m'hi ha fet pensar. Exemples més enfocats en la vida laboral era el cas d'en Marc, que va perdre una setmana per compilar drivers a Linux d'una targeta de xarxa, quan a l'empresa li sortia més a compte comprar-ne una que tingués suport per Linux. També va sortir l'exemple del Business Intelligence, que va més aplicat a la part de gestió d'una empresa.