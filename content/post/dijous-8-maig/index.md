---
title: "MRP d'impressores 3D II"
date: 2025-05-08T11:30:03+00:00
description: Creació d'un Material Requirements Planning (MRP) per a impressores 3D
slug: dijous-08-maig
image: mrp.png
categories:
    - Laboratori
tags:
---

## Hackathon

### Enunciat
L'objectiu d'aquesta sessió és seguir amb el desenvolupament d'un MRP d'impressores 3D explicat a [MRP d'impresores 3D I](/dgsi/post/dijous-24-abril).

### La solució
Ja que el dia anterior, mitjançant una sola prompt, ja teníem un resultat decent, ens vam centrar en aplicar certes millores al MRP. Concretament vam fer els següents canvis:
1. Afegir la possibilitat d'acceptar una comanda. Això implica afegir un nou estat entre pendent i en producció.
2. Mostrar un gràfic amb la previsió de stock de cadascuna de les peces.
3. Arreglar diversos bugs.

Les tecnologies utilitzades no varien respecte les del primer dia ([MRP d'impresores 3D I](/dgsi/post/dijous-24-abril)).

Per tal d'executar el projecte proporcionem un Dockerfile que crea 3 contenidors [Docker](https://www.docker.com/): un per al frontend, un per al backend, i un tercer amb la base de dades [MongoDB](https://www.mongodb.com/).

Per a més informació sobre el projecte, podeu donar un cop d'ull al [README](https://github.com/DGSI-UPC/3d-printer-mrp/blob/main/README.md) del projecte. Al següent enllaç trobareu el codi font del projecte:

[Veure a GitHub](https://github.com/DGSI-UPC/3d-printer-mrp)