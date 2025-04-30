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

[Enllaç al projecte de Github](https://github.com/DGSI-UPC/Web-to-Markdown)

Abans de començar la segona mini-hackathon del curs, en Marc va comentar un parell de coses sobre Markdown, que em van cridar l’atenció. La primera va ser quan va comentar que existia l’aplicació [Obsidian](https://obsidian.md/), una alternativa a [Notion](https://www.notion.com/). En Marc va comentar que Obsidian és open source, però és completament fals. És veritat que Obsidian és gratis, però no és opensource. No culpo en Marc, perquè és una concepció comuna popular, ja que tot i que Obsidian té un compte de Github, no hi ha el codi. Fins i tot, en el [README.md](https://github.com/obsidianmd/obsidian-releases/blob/master/README.md) del repositori [obsidianmd/obsidian-releases](https://github.com/obsidianmd/obsidian-releases), conté la següent frase: _"Obsidian is not open source software and this repo DOES NOT contain the source code of Obsidian."_. El segon comentari que em va cridar l’atenció és que digués que la seva pàgina personal estava feta amb [gohugo](https://gohugo.io/). La meva pàgina web també està feta amb gohugo. De fet, sóc mantainer del tema [hugo-toha](https://github.com/hugo-toha), tema que utilitzo per a la meva pàgina web.

Centrant-nos en la hackathon en sí, no és que hagi après gran cosa. Ja coneixia tècniques de crawling i web-scraping, però mai havia fet cap aplicació amb això. L’aplicació creada em sembla útil en 2 casos. El primer és si vols desar-te els continguts de la web en qüestió en local. D’aquesta manera, al no estar estructurat, totes les pàgines desades tenen el mateix “format”. La segona raó, és en el cas que vulguis fer un model que s’entreni amb informació de pàgines web. Eliminant totes les etiquetes d’html, estàs reduint la mida d’aquests fitxers, i eliminant soroll que produeixen aquestes etiquetes.