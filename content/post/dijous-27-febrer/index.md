---
title: "Web to Markdown"
date: 2025-02-27T11:30:03+00:00
description: Crawling i Scraping d'una web a Markdown
slug: dijous-27-febrer
image: web-to-markdown.png
categories:
    - Laboratori
tags:
---

## Introducció al Markdown
Abans de començar la segona mini-hackathon del curs, en Marc va comentar un parell de coses sobre Markdown, que em van cridar l’atenció. La primera va ser quan va comentar que existia l’aplicació [Obsidian](https://obsidian.md/), una alternativa a [Notion](https://www.notion.com/). En Marc va comentar que Obsidian és de codi obert, però és completament fals. És veritat que Obsidian és gratis, però no és Open Source. No culpo en Marc, perquè és una concepció comuna popular, ja que tot i que Obsidian té una organització a GitHub, però no conté el codi font. Fins i tot, en el [README.md](https://github.com/obsidianmd/obsidian-releases/blob/master/README.md) del repositori [obsidianmd/obsidian-releases](https://github.com/obsidianmd/obsidian-releases), conté la següent frase: _"Obsidian is not open source software and this repo DOES NOT contain the source code of Obsidian."_. El segon comentari que em va cridar l’atenció és que digués que la seva pàgina personal estava feta amb [gohugo](https://gohugo.io/). La meva pàgina web també està feta amb gohugo. De fet, soc mantainer del tema [hugo-toha](https://github.com/hugo-toha), tema que utilitzo per a la meva pàgina web.

## Hackathon
Centrant-nos en la hackathon en si, no és que hagi après gran cosa. Ja coneixia tècniques de crawling i web-scraping, però mai havia fet cap aplicació amb això. L’aplicació creada em sembla útil en 2 casos. El primer és si vols desar-te els continguts de la web en qüestió en local. D’aquesta manera, com que no està estructurat, totes les pàgines desades tenen el mateix “format”. La segona raó, és en el cas que vulguis fer un model que s’entreni amb informació de pàgines web. Eliminant totes les etiquetes d'HTML, estàs reduint la mida d’aquests fitxers, i eliminant soroll que produeixen aquestes etiquetes.

### Enunciat
En aquesta segona hackathon, havíem de construir una eina que permetés obtenir documents Markdown la pàgina de la [FIB](https://fib.upc.edu), mitjançant tècniques de [Crawling](https://en.wikipedia.org/wiki/Web_crawler) i [Web scraping](https://en.wikipedia.org/wiki/Web_scraping). Aquests fitxers Markdown també havíen de tenir les imatges i taules ben formatades. Aquests documents els necessitaríem per a pròximes hackathons.

### La solució
Acompanyat amb els meus companys, hem creat una pàgina web on l'usuari introdueix un enllaç d'una pàgina web. Després d'una estona (varia segons la mida de la pàgina), l'usuari obté un arxiu comprimit amb tots els fitxers Markdown, estructurats segons les subpàgines, amb totes les imatges, arxius PDF i altres. Les taules dels documents, s'han generat seguint l'estàndard de Markdown.

Per fer aquest projecte, hem utilitzat Python com a llenguatge principal. Per al servei API, igual que a la primera hackathon, hem usat [FastAPI](https://fastapi.tiangolo.com/).

Per tal de fer el crawling, hem creat una cua on afegim les pàgines de tots els enllaços trobats a la pàgina introduïda. Hem fet servir la biblioteca [trafilatura](https://trafilatura.readthedocs.io/en/latest/) per a obtenir els fitxers HTML, [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/) i [html2text](https://alir3z4.github.io/html2text/) per a fer el parseig d'HTML a Markdown.

Per tal d'executar el projecte, donem 2 possibilitats. La primera és executar-la en local mitjançant [Uvicorn](https://www.uvicorn.org/), i la segona és mitjançant un contenidor [Docker](https://www.docker.com/) amb el Dockerfile que proporcionem.

Per a més informació sobre el projecte, podeu donar un cop d'ull al [README](https://github.com/DGSI-UPC/Web-to-Markdown/blob/main/README.md) del projecte. Al següent enllaç trobareu el codi font del projecte:

[Veure a GitHub](https://github.com/DGSI-UPC/Web-to-Markdown)