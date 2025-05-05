---
title: "Generador de Subtítols"
date: 2025-02-20T11:30:03+00:00
description: Generador de subtítols SRT amb diarització
slug: dijous-20-febrer
image: subtitles.png
categories:
    - Laboratori
tags:
---

## GitHub Copilot
Amb la primera mini-hackathon del curs m’ha sorprès la facilitat amb què es pot generar codi mitjançant [copilot](https://github.com/features/copilot). Era la primera vegada que l’utilitzava, ja que jo sempre m’he mostrat contrari en fer-lo servir. La raó principal és que en utilitzar-lo, la gent entén menys què està programant, i en la situació actual, prefereixo aprendre i comprendre què estic programant. 

Així i tot, si domines la temàtica del que li preguntes al copilot, considero que pot ser molt útil per a afegir features de manera ràpida, i d’arreglar errors en el codi. Centrant-nos a la mini-hackathon, l’ús de copilot ens ha permès desenvolupar de forma molt ràpida el diaritzador d’àudio, estalviant-nos la recerca i lectura de la documentació de diversos models i biblioteques de Python. Després d’aquesta hackathon, segurament utilitzaré més freqüent copilot (però no a la feina on estic ara, que ens han prohibit la IA).

## Hackathon

### Enunciat
Aquesta primera hackathon consistia en construir una eina que permetés generar subtítols donat un fitxer d'àudio. A més a més, ha d'estar [diaritzat](https://lajavaness.medium.com/speaker-diarization-an-introductory-overview-c070a3bfea70), és a dir, que els subtítols indiquin qui diu la frase en qüestió. Aquests subtítols generats han d'estar en el format estàndard [SRT](https://en.wikipedia.org/wiki/SubRip).

### La solució
Acompanyat amb els meus companys, hem creat una pàgina web que genera automàticament els subtítols. L'usuari escull un fitxer d'àudio (`.wav`, `.mp3`, `.m4a` i `.flac`), i seguidament pot escollir entre els formats [SubRip (SRT)](ttps://en.wikipedia.org/wiki/SubRip) is [WebVTT (VTT)](https://en.wikipedia.org/wiki/WebVTT). Al cap d'uns segons, l'usuari obté el fitxer amb els subtítols diaritzats, en el format triat.

Per fer aquest projecte, hem utilitzat Python com a llenguatge principal. Per al servei API, hem usat [FastAPI](https://fastapi.tiangolo.com/).

Per tal de fer la transcripció i la diarització dels subtítols hem optat per donar 2 possibilitats.
1. La primera no requereix de cap clau API. Aquesta opció, es fan servir els models de [Pyannote](https://www.pyannote.ai/) [Segmentation](https://huggingface.co/pyannote/segmentation) i [Speaker Diarization](https://huggingface.co/pyannote/speaker-diarization).
2. La segona requereix d'una clau d'OpenAI. Amb aquesta opció, els subtítols es generen amb el model [Whisper](https://openai.com/index/whisper/) d'OpenAI.

Per tal d'executar el projecte, donem 2 possibilitats. La primera és executar-la en local mitjançant [Uvicorn](https://www.uvicorn.org/), i la segona és mitjançant un contenidor [Docker](https://www.docker.com/) amb el Dockerfile que proporcionem.

Per a més informació sobre el projecte, podeu donar un cop d'ull al [README](https://github.com/DGSI-UPC/Subtitle-Generator/blob/main/README.md) del projecte. Al següent enllaç trobareu el codi font del projecte:

[Veure a GitHub](https://github.com/DGSI-UPC/Subtitle-Generator)

A continuació podeu veure un vídeo on es mostra un exemple de generació de subtítols amb la nostra eina:

{{< video "subtitle_generator.mp4" >}}