---
title: "RAG II"
date: 2025-03-20T11:30:03+00:00
description: Creació d'un Retrieval Augmented Generation (RAG) de la pàgina de la FIB
slug: dijous-20-marc
image: rag.png
categories:
    - Laboratori
tags:
---

## System Prompts
### Introducció a les system prompts
En aquesta hackathon, hem començat aprenent com fer millors prompts als models com ChatGPT. Tot i que alguns d'aquests LLMs generen la seva pròpia [system prompt](https://promptengineering.org/system-prompts-in-large-language-models/), és molt necessari que entengui què li demanes. Per fer-ho, se li ha de proporcionar context rellevant, ser específic, i ser clar en què li demanes.

També he après perquè és important donar un context curt i concís. Abans d'aquesta classe pensava que l'objectiu principal era perquè tingués més taxa d'encert (també), però realment és per reduir els costos d'ús d'aquests models. 

Finalment, em va semblar curiós que el model retorni millors o pitjors respostes segons com creu que la persona que entra el prompt és. Pensant-ho una mica, té lògica que si esculls bé els conceptes, li sigui més fàcil trobar-lo, i donar millors respostes sobre aquest. D'altra banda, si ets vulgar amb l'entrada, és possible que t'ho relacioni amb informació poc valuosa, ja que aquestes paraules vulgars poden fer match amb informació que les contingui.

### Activitat amb Mermaid
#### Enunciat
Per tal de treballar com donar-li un bon prompt a un model, es va plantejar una activitat. Aquesta consistia a generar una línia del temps en [Mermaid](https://mermaid.js.org/) sobre la Universitat de Salamanca, en un sol prompt.

#### La solució
El prompt introduit al [ChatGPT-4o-mini](https://chatgpt.com/?model=gpt-4o-mini) és:

```
Can you generate a timeline in Mermaid about the history of Salamanca \
University? To do so, first find the most relevant events of this \
university, alongside their dates. Then, list them in chronological order, \
and group them by centuries. Finally, obtain more information about each \
one of these events, and generate the time line in MermaidJS.
```

El diagrama obtingut és el següent (podeu prémer sobre el diagrama per visualitzar-lo millor):

[![](https://mermaid.ink/img/pako:eNqNVtuO2zYQ_RVCL30xDF_Xlt-SzQZx20UXubRFsS-0NJbZUKRCSrtxggD9jX5HP6F_0i_pGVKS7dWiqB8WK4mcOTxz5gy_JpnNKdkktSpJK0P3RuBXq1qTeKN8bd1R2L2oDyQ-GPVAzqs6vHkntSylyeS9iXs8ZbWyRkxn9UFck6kbd4xfptP5QmzEa9uYXIY1w4jtZ8rF7ih-UKYQL_TeGm_F9lde_iP9_ZcZi239zx9_emENdTGszsnXoulCKfJCGXHTOFvRuAUwm645g3JY-dYepRZ3Tj0oTQXh_dN0hZOm9iH6PmxxYUvVbRmJvXWl1PooHGW2MOoLR-gZEdILeUJ0HA8omg8omi3nQHInKyR62Wgt9s6W4g5nEFtjbIbFYvszlrwHqlNooXyEC-IYr1PFoRa1FZk1e3Iip8JRZASfrbbFUUiTCy0fmein8Xu-1tMezTUiKRw3IOcSubjtVroaYZ8DBVYID17sG4e0LqDpY3B--lxJ41spKJAdgPtn4w_puxrQt5xMAGMLHrTGqoZxYwFisVQriUAb8fIIEkAYa310Vq4diljShao0yZxrqs4jZiFiIDOG5JNcCm05WyHR9UGqkPlWIhgfO_Nh8QtfO2tseRQ3vpY7rfwBhducnkquQ4shC1EgNVE-CSO7MCPhD_Yxk56x1hdF-I5xPlj9QCEm0PpM4T-1V5nwdZMfe8zLad8caAssQbA7R94PK0s9bB_KFvuj6nZVvGsk0Br2kZ8ZPAQouRA53MSpXdMZwEdjHzXlxYm75alJwa9BFvFS7WBE76Fwr6N6NvjGjeqiVVweehSe67PlLZcxDlDaPjSEgLJXmtA7PYQ1y-gNiv-pgfy42G2AbtfWfGoU20yAEpzj7qC0qsR2i27zqjA4rb80Aw5w-H9Bh2JfDcR-NY1iv6ju9-QbVYtXtAv5B5XrRN6KIm8tobMFlUHgrK3KagDhp7wN5Rvn2Js7jbWZfnJo1Y64qxVr6Fb-joK_JbbHZyCE5i4shwRNLEQYF8wiLkdpSswiBzeloC3KmywUsUUm81IZFhFePhA07Br0JRQ35CwdcLaep-wAtnE7LDhBfG07rZ4X5BcZ2ncLwBXhj8kuDON0EGRvYXAIlLpChXvRtdnaE3ZcrRdLbvmz00U44ZBvyboCIL50ah_6veuWoIjRL4MbhcF4zllMy1Y_eoIzdK7MGh2mJactLBIYHI4GZM4mAzLTCVd7teQvL0wEJ3FRuCZNO9f3ac9X1r5vTSNulKeNIzic-9gh09YUsJkoOJnJnEpYFgavzHrPSpfM4auu39gS2-sKlt5a04S2OMfw4YLDnDIt2UKkOHTbgsYwczzkDym2MVqP6ZQRieIvQ6KmMK4LomaTfiyB3LYsN_3oO4enZWMydtVC2x1fNoDEAO9BVbFC55Wlz5gNBneXyllM_9KfCJTC0GMYW6eM1UH6zmVnk3AVWk_-u3ZPVPekgHH3RQEdKQO5ZV0ReRLUChBlP1fjpIz3t3hp43OV1rN_7XXDwwlolcHGOowJP05GSeFUnmygXholJeESwY_JVz7OfcJzke6TDf7NaS-h6Pvk3nzDNpD8m7VltxMOVhySzV5qj6emwkWUXinJ7PVLuNPdNayuTjaLdQiRbL4mn5PNKh3jhjGZrK5m6TxdLOej5JhsZmk6Xqwmi-U6XS_mq-W3UfIlpJyM16tFit9ylS4Wk0W6GCWUK8jsNt62w32oSL79C5TYBfg?type=png)](https://mermaid.live/edit#pako:eNqNVtuO2zYQ_RVCL30xDF_Xlt-SzQZx20UXubRFsS-0NJbZUKRCSrtxggD9jX5HP6F_0i_pGVKS7dWiqB8WK4mcOTxz5gy_JpnNKdkktSpJK0P3RuBXq1qTeKN8bd1R2L2oDyQ-GPVAzqs6vHkntSylyeS9iXs8ZbWyRkxn9UFck6kbd4xfptP5QmzEa9uYXIY1w4jtZ8rF7ih-UKYQL_TeGm_F9lde_iP9_ZcZi239zx9_emENdTGszsnXoulCKfJCGXHTOFvRuAUwm645g3JY-dYepRZ3Tj0oTQXh_dN0hZOm9iH6PmxxYUvVbRmJvXWl1PooHGW2MOoLR-gZEdILeUJ0HA8omg8omi3nQHInKyR62Wgt9s6W4g5nEFtjbIbFYvszlrwHqlNooXyEC-IYr1PFoRa1FZk1e3Iip8JRZASfrbbFUUiTCy0fmein8Xu-1tMezTUiKRw3IOcSubjtVroaYZ8DBVYID17sG4e0LqDpY3B--lxJ41spKJAdgPtn4w_puxrQt5xMAGMLHrTGqoZxYwFisVQriUAb8fIIEkAYa310Vq4diljShao0yZxrqs4jZiFiIDOG5JNcCm05WyHR9UGqkPlWIhgfO_Nh8QtfO2tseRQ3vpY7rfwBhducnkquQ4shC1EgNVE-CSO7MCPhD_Yxk56x1hdF-I5xPlj9QCEm0PpM4T-1V5nwdZMfe8zLad8caAssQbA7R94PK0s9bB_KFvuj6nZVvGsk0Br2kZ8ZPAQouRA53MSpXdMZwEdjHzXlxYm75alJwa9BFvFS7WBE76Fwr6N6NvjGjeqiVVweehSe67PlLZcxDlDaPjSEgLJXmtA7PYQ1y-gNiv-pgfy42G2AbtfWfGoU20yAEpzj7qC0qsR2i27zqjA4rb80Aw5w-H9Bh2JfDcR-NY1iv6ju9-QbVYtXtAv5B5XrRN6KIm8tobMFlUHgrK3KagDhp7wN5Rvn2Js7jbWZfnJo1Y64qxVr6Fb-joK_JbbHZyCE5i4shwRNLEQYF8wiLkdpSswiBzeloC3KmywUsUUm81IZFhFePhA07Br0JRQ35CwdcLaep-wAtnE7LDhBfG07rZ4X5BcZ2ncLwBXhj8kuDON0EGRvYXAIlLpChXvRtdnaE3ZcrRdLbvmz00U44ZBvyboCIL50ah_6veuWoIjRL4MbhcF4zllMy1Y_eoIzdK7MGh2mJactLBIYHI4GZM4mAzLTCVd7teQvL0wEJ3FRuCZNO9f3ac9X1r5vTSNulKeNIzic-9gh09YUsJkoOJnJnEpYFgavzHrPSpfM4auu39gS2-sKlt5a04S2OMfw4YLDnDIt2UKkOHTbgsYwczzkDym2MVqP6ZQRieIvQ6KmMK4LomaTfiyB3LYsN_3oO4enZWMydtVC2x1fNoDEAO9BVbFC55Wlz5gNBneXyllM_9KfCJTC0GMYW6eM1UH6zmVnk3AVWk_-u3ZPVPekgHH3RQEdKQO5ZV0ReRLUChBlP1fjpIz3t3hp43OV1rN_7XXDwwlolcHGOowJP05GSeFUnmygXholJeESwY_JVz7OfcJzke6TDf7NaS-h6Pvk3nzDNpD8m7VltxMOVhySzV5qj6emwkWUXinJ7PVLuNPdNayuTjaLdQiRbL4mn5PNKh3jhjGZrK5m6TxdLOej5JhsZmk6Xqwmi-U6XS_mq-W3UfIlpJyM16tFit9ylS4Wk0W6GCWUK8jsNt62w32oSL79C5TYBfg)

```
timeline
    title History of the University of Salamanca

    section 12th Century
    1134 : Foundation of the University : Founded by King Alfonso IX of León. It’s one of the oldest universities in Europe.
    1218 : First Royal Privilege : King Alfonso IX grants the first royal privilege, formally recognizing Salamanca as a university.

    section 13th Century
    1253 : Papal Bull from Pope Innocent IV : The university is granted the right to confer degrees in theology and law by Pope Innocent IV.
    1281 : Papal Confirmation under Pope Martin IV : The university receives further confirmation and expansion of its rights under Pope Martin IV.

    section 16th Century
    1500 : Intellectual Center of Spain : By this time, Salamanca becomes one of the leading intellectual centers in Spain and Europe.
    1527 : Chair of Mathematics and Astronomy Established : Establishment of the chair for mathematics and astronomy, showcasing the university's involvement in scientific study.
    1551 : First Printing Press : The university establishes its first printing press, allowing for greater distribution of knowledge.
    1558 : First Spanish Bible Translation : Sponsored by the university, the translation of the Bible into Spanish is completed.
    1580 : Headquarters of the Spanish Inquisition : King Philip II designates Salamanca as the headquarters of the Spanish Inquisition.

    section 17th Century
    1610 : Involvement in Jesuit Debates : The university becomes involved in the theological and political debates surrounding the Jesuit Order.
    1671 : Major Reforms : The university undergoes significant reforms to modernize its educational and administrative structures.

    section 19th Century
    1839 : Bourbon Reforms : Following the Spanish War of Independence, Salamanca undergoes restructuring as part of the Bourbon reforms.
    1845 : Educational Reform and Reorganization : The university is reorganized under Spain’s educational reform law, restructuring its faculties and governance.

    section 20th Century
    1901 : 750th Anniversary Celebration : Salamanca celebrates its 750th anniversary, marking its longstanding academic legacy.
    1955 : Designated as Historic Monument : Salamanca University is declared a historic and artistic monument by the Spanish government.

    section 21st Century
    2000 : International Expansion : Salamanca launches global partnerships and educational exchange programs, marking a new international phase.
    2018 : 800th Anniversary Celebration : The university celebrates its 800th anniversary, reinforcing its prestige as one of Europe’s oldest and most influential institutions.
```

## Hackathon

### Enunciat
L'objectiu d'aquesta hackathon era complementar el RAG ja començat a [RAG I](/dgsi/post/dijous-13-marc). L'objectiu principal era afegir un diccionari de conceptes i acrònims, que ajudés al model a entedre certs conceptes. En el nostre cas, conceptes de la FIB, com podria ser `DGSI`. Per fer-ho, podíem experimentar amb els següents mecanismes:
1. Integrar les definicions dels conceptes als fragments abans de fer l'embedding
2. Integrar les definicions dels conceptes als fragments obtinguts de la query

### La solució
Nosaltres vam optar per seguir el segon mètode (integrar-ho després de la query). Per fer el diccionari, simplement vaig utilitzar el model [Gemini 2.0 flash](https://aistudio.google.com/prompts/new_chat?model=gemini-2.0-flash-exp). Simplement, li vaig demanar en aquest model a Copilot, que generés el diccionari en format JSON a partir del directori de fitxers de Markdown com a context.

En paral·lel, un company va integrar el RAG a una pàgina web, utilitzant [FastAPI](https://fastapi.tiangolo.com/).

Per a més informació sobre el projecte, podeu donar un cop d'ull al [README](https://github.com/DGSI-UPC/llm-chat-rag/blob/main/README.md) del projecte. Al següent enllaç trobareu el codi font del projecte:

[Veure a GitHub](https://github.com/DGSI-UPC/llm-chat-rag)