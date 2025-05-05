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

## Introducció als Embeddings
Abans de començar la 3a mini-hackathon, desconeixia completament què era l'embedding a bases de dades vectorials. En explicar en què consistia, em va semblar molt interessant poder fer cerques per similitud semàntica en una base de dades que un mateix s'ha muntat.

El responsable en trobar aquestes relacions semàntiques és un model especialitzat a fer embeddings. OpenAI ofereix [models d'embedding](https://platform.openai.com/docs/guides/embeddings#embedding-models) a un preu molt raonable, però també és comú executar models en local. Per fer-ho, molts usuaris utilitzen [Ollama](https://ollama.com/) amb aquests models. Jo ja l'havia fet servir abans, però sempre amb models LLM com [Llama3.1](https://ollama.com/library/llama3.1) o [Qwen2.5-Coder](https://ollama.com/library/qwen2.5-coder), però mai amb models d'embedding. Anteriorment, ja havia donat un cop d'ull als models més populars que ofereix Ollama, i sempre veia el model [nomic-embed-text](https://ollama.com/library/nomic-embed-text) com un dels més populars, sense que fos un LLM. Després d'aquesta hackathon ja he entès per què s'utilitza, perquè és tan popular, i que Ollama ofereix models per a altres usos.

Durant el grau, a l'assignatura de [Projectes de Programació](https://www.fib.upc.edu/ca/estudis/graus/grau-en-enginyeria-informatica/pla-destudis/assignatures/PROP) (PROP), vaig haver de fer un gestor de documents, on havíem de fer cerques de documents per similitud i rellevància. En aquell projecte vam utilitzar l'algorisme [TF-IDF](https://en.wikipedia.org/wiki/Tf%E2%80%93idf), que compta les vegades que una paraula surt al document, i en tots els documents. Hauríem pogut fer una cerca més potent, utilitzant l'embedding, après en aquesta mini-hackathon.

## Hackathon

### Enunciat
L'objectiu d'aquesta hackathon era utilitzar els documents en Markdown generats a la hackathon [Web to Markdown](/dgsi/post/dijous-27-febrer), i fer l'embedding a una base de dades vectorials. Una vegada ja s'ha fet l'embedding, l'aplicació hauria de ser capaç de fer queries a aquesta base de dades, i obtenir fragments dels documents rellevants amb la query feta.

### La solució
Acompanyat amb els meus companys, hem creat una eina CLI que permet indicar un directori on els documents en Markdown es localitzen. A més a més, l'usuari pot indicar la mida dels fragments (per defecte 500 caràcters), i un overlap entre fragments (per defecte 50 caràcters). Una vegada l'embedding ja està enllestit, l'usuari pot fer queries amb paràmetres addicionals. Aquests són: indicar la quantitat de resultats, indicar un subdirectori de fitxers (amb aquesta opció, es fa un embedding al moment), i indicar una base de dades vectorial amb l'embedding fet.

Per fer aquest projecte, hem utilitzat Python com a llenguatge principal. Seguint la recomanació d'en Marc, la base de dades vectorial escollida és [ChromaDB](https://www.trychroma.com/).

Per a indexar els fitxers a la base de dades, els partim en fragments. Tal com s'ha indicat, per defecte tenen una mida de 500 caràcters, amb 50 caràcters corresponent al fragment anterior, i 50 caràcters del fragment posterior. A més a més, indexem una sèrie de metadades, com el path del fitxer del fragment i l'índex de fragment del fitxer.

Per tal de fer l'embedding hem optat per donar 2 possibilitats.
1. La primera no requereix cap clau API. Aquesta opció utilitza les funcions per defecte de ChromaDB, [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2).
2. La segona requereix una clau d'OpenAI. Amb aquesta opció, els embeddings es generen amb el model [text-embedding-3-small](https://platform.openai.com/docs/models/text-embedding-3-small) d'OpenAI.

La part de les queries no té gaire misteri, simplement obtenim els fragments més rellevants de la base de dades.

Per a més informació sobre el projecte, podeu donar un cop d'ull al [README](https://github.com/DGSI-UPC/ChromaDB-Embedding/blob/main/README.md) del projecte. Al següent enllaç trobareu el codi font del projecte:

[Veure a GitHub](https://github.com/DGSI-UPC/ChromaDB-Embedding)