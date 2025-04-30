---
title: "RAG II"
date: 2025-03-20T11:30:03+00:00
description: Creació d'un Retrieval Augmented Generation (RAG) de la pàgina de la FIB
slug: dijous-20-marc
categories:
    - Laboratori
tags:
---

[Enllaç al projecte de Github](https://github.com/DGSI-UPC/llm-chat-rag)

En aquesta hackathon, hem començat aprenent com fer millors prompts als models com ChatGPT. Tot i que alguns d'aquests LLMs generen la seva pròpia [system prompt](https://promptengineering.org/system-prompts-in-large-language-models/), és molt necessari que entengui què li demanes. Per fer-ho, se li ha de proporcionar context rellevant, ser específic, i ser clar en què li demanes.

També he après perquè és important donar un context curt i concís. Abans d'aquesta classe pensava que l'objectiu principal era perquè tingués més taxa d'encert (també), però realment és per reduïr els costos d'ús d'aquests models. 

Finalment, em va semblar curiós que el model retorni millors o pitjors respostes segons com creu que la persona que entra el prompt és. Pensant-ho una mica, té lògica que si esculls bé els conceptes, li sigui més fàcil trobar-lo, i donar millors respostes sobre aquest. D'altra banda, si ets vulgar amb l'entrada, és possible que t'ho relacioni amb informació poc valuosa, ja que aquestes paraules vulgars poden fer match amb informació que les contingui.