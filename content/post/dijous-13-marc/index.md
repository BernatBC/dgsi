---
title: "RAG I"
date: 2025-03-13T11:30:03+00:00
description: Creació d'un Retrieval Augmented Generation (RAG) de la pàgina de la FIB
slug: dijous-13-marc
image: rag.png
categories:
    - Laboratori
tags:
---

## Introducció de conceptes
### Introducció al Retrieval Augmented Generation
Aquesta hackathon m'ha ensenyat com funcionen els agents de xatbot quan fan cerques a internet. La idea principal és introduir context com a entrada del model. En aquests bots, el context, a part de contenir l'historial del xat i els tokens introduïts a la sortida, se li afegeix informació rellevant extreta d'internet. Explicat d'una manera molt simplificada, això se'n coneix com a Retrieval Augmented Generation (RAG).

### Introducció al Product Requirements Document
Abans de començar aquesta hackathon, en Marc va introduir el Product Requirements Document (PRD). Un PRD és un document formal que descriu el propòsit, les característiques i la funcionalitat d'un producte o una característica específica. Serveix com a guia central per als equips de disseny, enginyeria i altres, assegurant que tothom entengui què s'ha de construir i per què.

Sabent aquest concepte, en aquesta hackathon vam decidir demanar-li a un model que ens generés un PRD seguint les guies donades. Amb aquest document, el Copilot tenia més clar què havia de fer en aquesta hackathon, per tal d'obtenir uns millors resultats, i sobretot, que se cenyeixi més amb la nostra idea de projecte.

## Hackathon

### Enunciat
L'objectiu d'aquesta hackathon era integrar un LLM a la base de dades vectorials desenvolupat a la hackathon d'[Embedding amb ChromaDB](/dgsi/post/dijous-6-marc), per tal de donar context a un xatbot. 

### La solució
Per tal de crear el RAG, en el nostre cas, la informació d'internet ja l'havíem extret a la mini-hackathon del [Dijous 27 Febrer](/dgsi/post/dijous-27-febrer), i introduïda a una base de dades vectorial el [Dijous 6 Març](/dgsi/post/dijous-6-marc). Una vegada l'usuari dona una entrada al xat, el sistema construeix una query per a la base de dades, per recollir informació semànticament semblant. A continuació, introduïm l'entrada de l'usuari, juntament amb el propmt, l'historial i els resultats més rellevants obtinguts de la base de dades, al model LLM, que en el nostre cas era ChatGPT-4o-mini, mitjançant l'[API d'OpenAI](https://platform.openai.com/docs/models). A la imatge de continuació hi ha un esquema d'aquest sistema.

![](/dgsi/post/dijous-13-marc/20250315154323.png)

El funcionament del nostre RAG no té gaire misteri, ja que la font de coneixament (base de dades vectorial) ja la teníem feta. Simplement, fem una query a aquesta base de dades. Si no hi ha cap fragment obtingut per sobre d'un cert llindar de rellevància, el sistema retorna un missatge indicant que no tenim el coneixement per respondre-ho. Altrament, els fragments obtinguts, juntament amb el prompt i l'historial del cat, el passem al model [ChatGPT-4o-mini](https://platform.openai.com/docs/models/gpt-4o-mini) d'OpenAI. La resposta obtinguda per aquest LLM és la que el sistema imprimeix.

Per a més informació sobre el projecte, podeu donar un cop d'ull al [README](https://github.com/DGSI-UPC/llm-chat-rag/blob/main/README.md) del projecte. Només voldria mencionar que la versió del projecte està actualitzada amb els continguts de [RAG II](/dgsi/post/dijous-20-marc). Al següent enllaç trobareu el codi font del projecte:

[Veure a GitHub](https://github.com/DGSI-UPC/llm-chat-rag)