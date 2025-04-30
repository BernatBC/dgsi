---
title: "Chat with any website I"
date: 2025-03-27T11:30:03+00:00
description: Xatbot complet on la resposta es basa amb la pàgina web introduïda
slug: dijous-27-marc
categories:
    - Laboratori
tags:
---

[Enllaç al projecte de Github](https://github.com/DGSI-UPC/chat-with-any-website)

En aquesta hackathon seguíem utilitzant el nostre xatbot. En Marc va escriure 4 nivells per a assolir:
1. **Xatbot bàsic:** Assolit el dia [Dijous 13 Març](/dgsi/post/dijous-13-marc)
2. **Xatbot amb capacitat semàntica:** Assolit el dia [Dijous 20 Març](/dgsi/post/dijous-20-marc)
3. **Capacitat de suportar PDFs**
4. **Suport Docker**
A més a més d'aquest nivell, calia afegir-li una interfície gràfica (una pàgina web, per exemple) per tal d'utilitzar-lo.

Ja feia dies que teníem pensat fer una ampliació al xatbot, per tal que en passar-li qualsevol enllaç durant l'execució, automàticament es fer l'scrapping en markdown, fes l'embedding, i generi un diccionari semàntic amb els conceptes rellevants.

Per aquest motiu, vam decidir fer el projecte des de 0, utilitzant [Gemini 2.5 Pro](https://deepmind.google/technologies/gemini/pro/), que havia sortit el dia anterior. Amb un sol prompt, va aconseguir assolir els següents punts:
1. Xatbot bàsic
2. Xatbot amb capacitat semàntica
3. Suport PDF
4. Interfície Web
5. Docker
Per fer l'embedding, s'utilitza [all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) en local, mentres que el LLM utilitzat per al xat, és ChatGPT-4o-mini, mitjançant l'[API d'OpenAI](https://platform.openai.com/docs/models).

