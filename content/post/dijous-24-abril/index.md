---
title: "MRP d'impressores 3D I"
date: 2025-04-24T11:30:03+00:00
description: Creació d'un Material Requirements Planning (MRP) per a impressores 3D
slug: dijous-24-abril
categories:
    - Laboratori
    - TO ADD THUMBNAIL
tags:
---

## Hackathon

### Enunciat
En aquesta classe en Marc ens va donar l'enunciat de la pròxima hackathon. Aquesta consisteix en fer un MRP per a la fabricació d'impressores 3D, amb una interfície gràfica, que es pugui gestionar mitjançant una API, i que es pugui llançar en Docker. A continuació es troba l'enunciat complet del projecte:

<embed src="project.pdf" width="100%" height="700" type="application/pdf">

### La solució
En aquesta sessió no vaig poder contribuir, ja que malhauradament vaig haver de marxar abans d'hora perquè no em trobava bé. Tot i aixi, el meu grup va poder fer una primera versió completa del projecte, una altra vegada amb un sol prompt a [Gemini 2.5 Pro](https://deepmind.google/technologies/gemini/pro/).

Com a cada hackathon,hem utilitzat Python com a llenguatge principal, i [FastAPI](https://fastapi.tiangolo.com/) per a l'API i la web.

Per a la simulació, hem utilitzat [SimPy](https://simpy.readthedocs.io/en/latest/), tal com s'ha demanat a l'enunciat. [Streamlit](https://streamlit.io/) ens permet fer els dashboards d'una manera senzilla. Com a persistencia, utilitzem fitxers JSON, que els validem amb la biblioteca [Pydantic](https://docs.pydantic.dev/latest/). A més a més, per a gestionar les ordres utilitzem `DataFrame` de [Pandas](https://pandas.pydata.org/), ja que ens permet fer càlculs avançats de forma senzilla, i ens serà més fàcil per poder representar els gràfics amb [Matplotlib](https://matplotlib.org/).

Per tal d'executar el projecte, donem 2 possibilitats. La primera és executar-la en local mitjançant [Uvicorn](https://www.uvicorn.org/), i la segona és mitjançant un contenidor [Docker](https://www.docker.com/) amb el Dockerfile que proporcionem.

Per a més informació sobre el projecte, podeu donar un cop d'ull al [README](https://github.com/DGSI-UPC/3d-printer-mrp/blob/main/README.md) del projecte. Al següent enllaç trobareu el codi font del projecte:

[Veure a GitHub](https://github.com/DGSI-UPC/3d-printer-mrp)