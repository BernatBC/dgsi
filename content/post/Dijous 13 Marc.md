---
title: "Dijous 13 de Març"
date: 2025-03-13T11:30:03+00:00
description: Dijous 13 de Març
slug: dijous-13-marc
categories:
    - Laboratori
tags:
---

[Enllaç al projecte de Github](https://github.com/DGSI-UPC/llm-chat-rag)

Aquesta hackathon m'ha ensenyat com funcionen els agents de xatbot quan fan cerques a internet. La idea principal és introduir context com a entrada del model. En aquests bots, el context, a part de contenir l'historial del xat i els tokens introduits a la sortida, se li afageix informació rellevant extreta d'internet. 

En el nostre cas aplicat, la informació d'internet ja l'havíem extret a la mini-hackathon del [Dijous 27 Febrer](/dgsi/post/dijous-27-febrer), i introduïda a una base de dades vectorial el [Dijous 6 Març](/dgsi/post/dijous-6-marc). Una vegada l'usuari dona una entrada al xat, el sistema construeix una query per a la base de dades, per recollir informació semànticament semblant. A continuació, se li passa l'entrada de l'usuari, juntament amb els resultats més rellevants obtinguts de la base de dades, al model LLM, que en el nostre cas era ChatGPT-4o-mini, mitjançant l'[API d'OpenAI](https://platform.openai.com/docs/models). A la imatge de continuació hi ha un esquema d'aquest sistema.

![](/dgsi/post/20250315154323.png)