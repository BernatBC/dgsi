---
title: "Embedding amb ChromaDB"
date: 2025-03-06T11:30:03+00:00
description: Creació d'embeddings de la pàgina de la FIB a bases de dades vectorials
slug: dijous-6-marc
image: chromadb.png
categories:
    - Laboratori
tags:
---


[Enllaç al projecte de Github](https://github.com/DGSI-UPC/ChromaDB-Embedding)

Abans de començar la 3a minihackathon, desconeixia completament què era l'embedding a bases de dades vectorials. En explicar en què consistia, em va semblar molt interessant el poder fer cerques per similaritat semàntica en una base de dades que un mateix s'ha muntat.

El responsable en trobar aquestes relacions semàntiques és un model especialitzat en fer embeddings. OpenAI ofereix [models d'embedding](https://platform.openai.com/docs/guides/embeddings#embedding-models) a un preu molt raonable, però també és comú executar models en local. Per fer-ho, molts usuaris utilitzen [Ollama](https://ollama.com/) amb aquests models. Jo ja l'havia utilitzat abans, però sempre amb models LLMs com [Llama3.1](https://ollama.com/library/llama3.1) o [Qwen2.5-Coder](https://ollama.com/library/qwen2.5-coder), però mai amb models d'embedding. Anteriorment, ja havia fet un cop d'ull als models més populars que ofereix Ollama, i sempre veia el model [nomic-embed-text](https://ollama.com/library/nomic-embed-text) com un dels més populars, sense que fos un LLM. Després d'aquesta hackathon ja he entès perquè s'utilitza, perquè és tant popular, i que Ollama ofereix models per a altres usos.

Durant el grau, a l'assignatura de [Projectes de Programació](https://www.fib.upc.edu/ca/estudis/graus/grau-en-enginyeria-informatica/pla-destudis/assignatures/PROP) (PROP), vaig haver de fer un gestor de documents, on havíem de fer cerques de documents per similaritat i rellevància. En aquell projecte vam utilitzar l'algorisme [TF-IDF](https://en.wikipedia.org/wiki/Tf%E2%80%93idf), que compta les vegades que una paraula surt al document, i en tots els documents. Haguéssim pogut fer una cerca més potent, utilitzant l'embedding, après en aquesta mini-hackathon.