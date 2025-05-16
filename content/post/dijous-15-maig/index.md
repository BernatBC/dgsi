---
title: "Agents I: Broswer-use"
date: 2025-05-15T11:30:03+00:00
description: Creació d'un agent al navegador
slug: dijous-15-maig
image: browser-use.png
categories:
    - Laboratori
tags:
---

## Introducció al browser-use
[Browser-use](https://browser-use.com/) és una biblioteca de Python que et permet crear un agent que actua al navegador. Aquesta et permet controlar navegadors web automàticament mitjançant un model de visió per al reconeixement dels elements, i un Large Language Model que fa crides recursives per tal de generar les accions.

## Hackathon

### Enunciat
L'objectiu d'aquesta hackathon era crear un agent amb [Browser-use](https://browser-use.com/), que fos capaç de resoldre un test amb preguntes d'actualitat, preferiblement posteriors a la cutoff date del model utilitzat.

### La idea
La nostra idea consistia a crear una sèrie de preguntes sobre els [bloqueigs de servidors de part de laliga](https://www.3cat.cat/324/matar-mosques-a-canonades-com-lestrategia-de-laliga-contra-la-pirateria-afecta-milers-de-webs/noticia/3350001/) en un document a Google Docs. A continuació, l'agent accediria al document, llegiria les preguntes, faria cerques a internet, i les respondria.

### La solució
Malauradament no vam aconseguir el nostre objectiu. Tot i així, hem pogut superar una sèrie de fites durant el desenvolupament de l'agent.

La primera fita era que l'agent pogués accedir al Google Docs. Des d'un inici, l'agent ja accedia a la pàgina en qüestió, però un compte de Google era necessari. En les primeres iteracions, l'agent intentava accedir amb comptes que es treia de la màniga, i més endavant intentava crear un compte nou. Això ho vam poder resoldre forçant que el Google Chrome mantingués la sessió oberta, i especificant la ruta del binari del navegador.

La segona fita que vam "resoldre" era accedir al document compartit on hi havia les preguntes escrites. Durant els nostres intents, l'agent creava un document nou tota l'estona, i en altres iteracions, remenava la configuració de Google. En veure que no hi havia manera, optàvem per obrir-lo manualment quan l'agent entrava al Docs. L'agent tenia hardcodejat l'enllaç, però així i tot, passava de nosaltres.

La tercera fita proposada era que el model llegís les preguntes del document. L'agent, una vegada tenia el document obert, intentava compartir-lo. Això era perquè li havíem dit que el document estava compartit. En les següents iteracions, semblava que l'agent era capaç de detectar el cos del document, però decidia tancar el navegador.

Per a aquest projecte, vam utilitzar els següents models:
- [GPT-4o](https://platform.openai.com/docs/models/gpt-4o) com a model de visió.
- [GPT-4o mini](https://platform.openai.com/docs/models/gpt-4o-mini) com a model que genera les respostes.
- [sonar-small-32k-online](https://docs.perplexity.ai/models/models/sonar) com a model de [Perplexity.ai](https://www.perplexity.ai/) per a la cerca de respostes a internet.

Al següent enllaç trobareu el codi font del projecte:

[Veure a GitHub](https://github.com/DGSI-UPC/test-solver-agent)