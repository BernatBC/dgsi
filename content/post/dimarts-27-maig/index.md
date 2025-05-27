---
title: "Creant Agents"
date: 2025-05-27T00:30:03+00:00
description: Creació d'un agent seguint REACT (Reason Act)
slug: dimarts-27-maig
image: react.webp
categories:
    - Laboratori
tags:
---

## Introducció als agents
Els agents, en el context del desenvolupament de programari, són sistemes dissenyats per executar tasques de manera autònoma o semi-autònoma. És important destacar que un agent **no és una intel·ligència artificial (IA)**, sinó un component de programari que segueix unes regles o instruccions predefinides per interactuar amb l'entorn o amb altres sistemes.

Un agent pot rebre instruccions, processar informació i actuar utilitzant diferents eines o serveis, però no "aprèn" ni "pensa" per si mateix com faria una IA. En molts casos, els agents implementen patrons com el **RE-ACT**:

- **REason**: L'agent genera automàticament instruccions (auto prompting) a partir de la informació rebuda, però no descobreix coneixement nou; simplement aplica tècniques de prompt engineering per decidir què fer.
- **ACT**: L'agent executa accions concretes, com ara fer cerques a internet o utilitzar funcions específiques (function calling), mitjançant eines o serveis externs.

Així, el funcionament típic d'un agent comença amb un prompt inicial: rep un missatge de l'usuari, processa la informació en cicles i guia l'usuari sobre com utilitzar les diferents eines disponibles. Tot plegat, sense ser una IA, sinó un sistema de programari estructurat per resoldre tasques de manera eficient.

## Hackathon

### Enunciat
En aquesta hackathon, havíem de construir una agent sense utilitzar cap mòdul, fent-lo tal qual. Aquest agent ha de seguir RE-ACT, implementant un bucle d'auto prompting, i creant alguna eina que pogués utilitzar.

### La solució
Acompanyat amb els meus companys, hem creat un agent que fa auto prompting en bucle. Respecte a l'"ACT", l'agent es centra en fer embeddings vectorials amb [ChromaDB](https://www.trychroma.com/), com a la hackathon [Embedding amb ChromaDB](/dgsi/post/dijous-6-marc/). Les 3 funcions que crida el nostre agent són:
- `embed_information(content: str, category: str) -> str`: fa l'embedding d'un fragment de text qualsevol
- `query_information(query_text: str, category: str) -> dict`: retorna com a màxim 5 fragments de texts, conjuntament amb les seves metadades.
- `scrape_and_embed_website(url: str) -> list[str]`: fa l'embedding d'una pàgina web, donat un enllaç, similar a les hackathons [Chat with any website I](/dgsi/post/dijous-27-marc/) i [Chat with any website II](/dgsi/post/dijous-10-abril/).

Tot i que es pot executar en local, proporcionem un Dockerfile i un `docker-compose.yml` per a fer l'execució en un contenidor.

[Veure a GitHub](https://github.com/DGSI-UPC/barbones-agent)