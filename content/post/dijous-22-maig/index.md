---
title: "Model Context Protocol I"
date: 2025-05-22T00:30:03+00:00
description: Experimentant amb Model Context Protocol de Claude
slug: dijous-22-maig
image: claude.png
categories:
    - Laboratori
tags:
---

## Introducció al Model Context Protocol
Els [Model Context Protocols (MCP)](https://modelcontextprotocol.io/introduction) són especificacions que defineixen com els models d'intel·ligència artificial poden gestionar, compartir i utilitzar el context durant una conversa o procés. Permeten que diferents aplicacions i serveis intercanviïn informació contextual de manera estructurada, millorant la coherència i la personalització de les respostes dels models. Això facilita la integració de models en entorns complexos i multiusuari, assegurant una experiència més rica i adaptada a cada situació.

## Experimentant amb Claude Desktop
Una vegada presentat el Model Context Protocol, hem experimentat amb els MCPs utilitzant [Claude Desktop](https://claude.ai/download). Malauradament, no hi ha l'opció d'instal·lar-ho a Linux, però he trobat un [repositori](https://github.com/bsneed/claude-desktop-fedora) per instal·lar-ho a Fedora, la distribució que utilitzo. Tot i això, m'ha sortit un error de compatibilitat de GTK, i he hagut d'instal·lar-ho a Windows.

Aquesta [issue](https://github.com/bsneed/claude-desktop-fedora/issues/21) oberta descriu aquest problema, i l'endemà va quedar resposta. A Fedora 42, es pot iniciar Claude Desktop directament amb:

```bash
claude-desktop --gtk-version=3
```

### Filesystem MCP Server
El primer MCP que hem utilitzat, és el [Filesystem MCP Server](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem), que ja ve incorporat al Claude Desktop. Després de reiniciar Windows, ha sigut possible utilitzar-ho. Tal com indica el seu nom, aquest MCP dona accés al sistema d'arxius, concretament als directoris especificats al fitxer de configuració. Un dels exemples explicats per en Marc, que també he aconseguit funcionar és el de llistar els fitxers d'un repositori.

### Desktop Comander
El següent MCP és el [Desktop Commander](https://desktopcommander.app/). Aquest dona al model l'accés a la terminal. L'exemple fet, que també m'ha funcionat, és el d'indicar al model que mati un procés. Hem aconseguit matar el procés del Word, i fins i tot el de l'aplicació de Claude Desktop.

### Playwright MCP Server
Finalment, hem provat [Playwright MCP](https://github.com/microsoft/playwright-mcp). Aquest permet fer l'ús d'aplicacions, com el navegador. Hem provat l'exemple de navegar a la pàgina web de l'UPC i buscar el telèfon d'en Marc, però jo no ho he aconseguit. Playwright utilitza molts tokens, i amb la versió gratis de Claude em sortia un error dient que m'havia passat del límit.