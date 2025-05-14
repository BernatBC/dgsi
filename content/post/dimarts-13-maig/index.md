---
title: "Introducció a la Ciberseguretat i a les OT"
date: 2025-05-13T11:30:03+00:00
description: Classe de dos exalumnes centrats en la Ciberseguretat de les Tecnologies Operacionals
slug: dimarts-13-maig
image: teams.png
categories:
    - Teoria
tags:
---

Aquesta classe no la va fer en Marc, sinó dos exalumnes que estan ficats a la ciberseguretat. Un d'ells treballa a [Deloitte](https://www.deloitte.com/) en un equip Blue, i l'altre ha format una empresa que es dedica a la part Red.

## Active directory
La classe va començar amb la introducció de l'[Active Directory](https://en.wikipedia.org/wiki/Active_Directory). Tot i que és un producte de Microsoft, l'active directory és el servidor central de l'empresa, que té totes les identitats, permisos, polítiques, usuaris, contrasenyes, etc. Ho podem generalitzar com al servidor de l'empresa encarregat de l'autorització i autentificació.

## Equips a la ciberseguretat
A la ciberseguretat, hi ha principalment 3 rols:
![](/dgsi/post/dimarts-13-maig/teams_main.png)

### Red Team
El [Red Team](https://en.wikipedia.org/wiki/Red_team) és probablement el rol més conegut fora de l'àmbit. És l'equip que es dedica a identificar i a vulnerar falles en els sistemes. Quan un familiar teu pensa en ciberseguretat, pensa en hackers de l'equip vermell. Tot i que sigui el rol més conegut, hi ha molta poca gent que s'hi dedica.

### Blue Team
Si hem dit que el red team hi havia poca gent que s'hi dedicava, el [Blue Team](https://en.wikipedia.org/wiki/Blue_team_(computer_security)) és on es troba la gran majoria dels professionals de ciberseguretat. Bàsicament, el grup de persones que pertany a aquest equip, es dedica a arreglar les falles, i protegir els sistemes per tal de reduir els atacs i amenaces.

### Purple Team
Finalment, tenim el [Purple Team](https://www.crowdstrike.com/en-us/cybersecurity-101/advisory-services/purple-teaming/). Tal com es pot intuir, aquest equip es troba entre els dos grups descrits anteriorment. L'objectiu principal de l'equip Purple és fer de pont entre l'equip blau i vermell, ja que tenen coneixements dels dos equips. Aquest equip permet que hi hagi una coordinació dels dos equips a l'empresa.

## Tecnologies Operacionals
El següent concepte que ens van explicar era les [tecnologies operacionals](https://en.wikipedia.org/wiki/Operational_technology). Aquestes tecnologies són paral·leles a les tecnologies de la informació. Se centren principalment en la interacció amb el món físic, captant informació amb els sensors, i fent accions amb els actuadors.

![](/dgsi/post/dimarts-13-maig/it-ot.webp)

### Relació amb l'apagada
Aquestes tecnologies són molt crítiques per al funcionament de tota la cadena de producció d'un país. Si algun sistema crític de tecnologies operacionals falla, pot causar una catàstrofe.

Ho podem relacionar amb l'[apagada que va viure Espanya](https://en.wikipedia.org/wiki/2025_Iberian_Peninsula_blackout). Els túnels tenen sistemes de ventilació, il·luminació, semàfors, cartells, càmeres, telèfons d'emergència, etc. Sense electricitat, un túnel s'ha de tancar, ja que no és segur circular-hi. Amb una apagada, si no tenen una font d'energia auxiliar, un túnel es tanca. Això causa que algunes regions queden totalment aïllades. En quedar aïllades, no entra menjar a la regió, i els operaris tampoc poden fer res per obrir el túnel, ja que depenen d'altres empreses, que també queden afectades. Tota la cadena de producció pot caure, i hi hauria una gran catàstrofe.

Amb aquesta relació, ens podem adonar que mantenir les tecnologies operacionals és tan crític com el subministrament elèctric.

## Eines de ciberseguretat de l'estat de l'art
Centrant-nos més en l'àmbit del Red Team, un dels exalumnes ha explicat un parell de sistemes que s'utilitzen, que m'han semblat molt interessants.

### Deepfake de la veu
La primera eina exposada és una eina desenvolupada per una spinoff de Telefónica, que feina un deepfake de la veu. Ens van fer una demo d'aquesta eina, gravant la veu d'un dels exalumnes, mentre explicava. Al cap d'uns pocs segons, la intel·ligència artificial era capaç de reproduir amb la veu de l'exalumne qualsevol text. Tot i que el micro utilitzat no era de gaire qualitat, la veu s'hi assemblava bastant.

### Sistema RAG personalitzat
L'altra eina que ens van explicar era un sistema RAG que havia desenvolupat ell mateix, que podia substituir hackers de nivell 1. Era un sistema RAG complex que tenia guies de detecció i mitigació d'atacs, que quan una alerta saltava, la intel·ligència artificial era capaç de detectar si era un fals positiu o si era un atac real. El sistema era molt complex, sent un RAG de RAG de RAG, que es nodrien l'un de l'altre. 

Nosaltres amb les sessions de laboratori ja hem posat en pràctica els RAGs, però eren sistemes de joguina comparats amb el que ens va explicar.