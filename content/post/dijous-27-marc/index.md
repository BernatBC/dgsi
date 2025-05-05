---
title: "Chat with any website I"
date: 2025-03-27T11:30:03+00:00
description: Xatbot complet on la resposta es basa en la pàgina web introduïda
slug: dijous-27-marc
image: chat.png
categories:
    - Laboratori
tags:
---

## Hackathon

### Enunciat
En aquesta hackathon seguíem desenvolupant el nostre xatbot. En Marc va escriure 4 nivells per a assolir:
1. **Xatbot bàsic:** Assolit el dia [Dijous 13 Març](/dgsi/post/dijous-13-marc)
2. **Xatbot amb capacitat semàntica:** Assolit el dia [Dijous 20 Març](/dgsi/post/dijous-20-marc)
3. **Capacitat de suportar PDFs**
4. **Suport Docker**
A més a més d'aquest nivell, calia afegir-li una interfície gràfica (una pàgina web, per exemple) per tal d'utilitzar-lo.

### La solució
Ja feia dies que teníem pensat fer una ampliació al xatbot, per tal que en passar-li qualsevol enllaç durant l'execució, automàticament es fes l'scrapping en Markdown, l'embedding, i generi un diccionari semàntic amb els conceptes rellevants.

Per aquest motiu, vam decidir fer el projecte des de 0, utilitzant [Gemini 2.5 Pro](https://deepmind.google/technologies/gemini/pro/), que havia sortit el dia anterior. Amb un sol prompt, va aconseguir assolir els següents punts:
1. Xatbot bàsic
2. Xatbot amb capacitat semàntica
3. Suport PDF
4. Interfície Web
5. Docker

Per fer l'embedding, es fa servir [all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) en local, mentre que el LLM utilitzat per al xat, és ChatGPT-4o-mini, mitjançant l'[API d'OpenAI](https://platform.openai.com/docs/models).

El prompt introduït és:

``` txt
OBJECTIVE: 

 You will create a python API and website. The goal is to have a functioning website in which a user can introduce an URL of any website and then the contents of the website will be scrapped and indexed and then the user will be able to chat with an LLM that will use the knowledge scraped in the website to answer the questions. Make sure to provide all the code of the diferent files preparated so I can copy and paste and to define a clear file structure. Make sure that the frontend and the bakcend lie in different folders. Everything must be dockerized so it can be easily runned by using docker compose up. To simplify things, everything should be in the same docker container. Do NOT use celery as it complicates things too much. This should support content in English, Spanish and Catalan.

REQUIREMENTS: 

 - Use python 3.11 
 - Use fastapi as api 
 - Use ChromaDB as vdb and db 
 - Use Beautiful soup for web scrapping 
 - Use teseract paired with PyMuPDF for pdf OCR 
 - Generate the embedding locally 
 - Use the gpt-4o-mini-2024-07-18 for the LLM 
 - The frontend must be made using html, vanilla JS and CSS. Serve it from the python backend to avoid using CORS. Keep in mind that the frontend must be in a separated folder from the backend.
 - Make sure to not write the version of the package in the requirements.txt to fetch the latest version.
 
INSTRUCTIONS: 

 - When the user enters a website url, the backend starts scrapping it. Make sure to extract EVERYTING from the whole website, process images and all content from PDFs and index everything in the VDB. While this is happening keep updating in the frontend the number of pages indexed so the user knows how the process goes. Make sure to use good chunking techniques so the model can efectivelly use the contents of the VDB to answer the questions. 
 - Also, while indexing everything, for all the concepts and acronyms that are particular to that specific website, store them in the DB as semantic agumentation. Related concepts based must be related in the DB, as I want you to perfectly implement the rest of the application, use a simple yet functional Regex for achieving this. 
 - When a user asks a question, it will first go through the VDB and all related chunks will be included in the context. Even if no chunks are find or the chunks are not relevant, pass the user question and augment it searching each word in the semantic augmentation. For each word that appears in the search, include the explanation of it as well as what is it related to in the context. After this, with all this context and the user question send it to the LLM. Also, the chat must maintain a history of 5 questions which will also be sent to the model as well as the context of those questions. 
 - The user must be able to create new chats, delete old chats, and retrieve the contents of the chat when clicking on it. 
 - The user must also be able to select which websites that have been scrapped does it want to talk in each chat. 
 - Make sure that while the scrapping is ongoing the user can still talk with the LLM, delete chats and whatever it wants to do. 
 - And make sure the LLM includes the references from which it has obtained the information (URLs), or no references if it has answered without using the VDB knowledge. 

IMPORTANT 

 - Make sure to implement EVERYTHING as described, do NOT cut corners nor simplify the implementation in ANY way.
 - Apply ANY and ALL the improvements that you think of and you will get handsomely rewarded. 
 - If you do not follow the instructions you will be fired.
```

Per a més informació sobre el projecte, podeu donar un cop d'ull al [README](https://github.com/DGSI-UPC/chat-with-any-website/blob/main/README.md) del projecte. Només voldria mencionar que la versió del projecte està actualitzada amb els continguts de [Chat with any website II](/dgsi/post/dijous-10-abril). Al següent enllaç trobareu el codi font del projecte:


[Veure a GitHub](https://github.com/DGSI-UPC/chat-with-any-website)