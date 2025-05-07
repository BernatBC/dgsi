---
title: "Corbes de Nolan i evolució tecnològica"
date: 2025-05-06T11:30:03+00:00
description: Introducció a les corbes de Nolan i evolució de les tecnologies
slug: dimarts-6-maig
image: evolution.webp
categories:
    - Teoria
tags:
---

## OLTP i sistemes ERP
La classe va començar amb un petit repàs sobre els sistemes ERP. Abans, hem d'entendre què són els sistemes OLTP. De manera simplificada, un sistema [OLTP (Online Transaction Processing)](https://en.wikipedia.org/wiki/Online_transaction_processing) és un mecanisme fonamental per la gestió de les bases de dades, on ens permet controlar l'atomicitat de les transaccions SQL. Això és essencial per mantenir la integritat de les dades, especialment en entorns com els sistemes ERP, on les operacions de diferents departaments poden afectar-se mútuament. Tal com es va comentar a [Proposta de valor i MRP](/dgsi/post/dijous-22-abril), els ERP permeten integrar múltiples funcions d'una empresa en una única plataforma. Aquesta integració és clau per poder aplicar estratègies de previsió de stock, que permeten anticipar necessitats de materials i productes, i models de just in time, que busca reduir l'estoc al mínim necessari per operar, estalviant costos i augmentant l’eficiència.

## Corbes de Nolan
Les corbes de Nolan descriuen l’evolució de la informatització dins d’una organització en diverses fases, sovint representada com una gràfica de cost ($) al llarg del temps. Aquesta evolució es divideix en cinc fases (simplifiquem el següent diagrama, eliminant la 3):

![](/dgsi/post/dimarts-6-maig/nolan.jpg)

També cal mencionar que aquestes fases no només passa amb la informàtica, sinó amb totes les tecnologies.

### Fases de les Corbes de Nolan

D'aquestes 5 fases, ens centrem en les 3 primeres:
Fa un gràfic $/temps, en 5 fases:
1. **Fase inicial:** S’introdueixen els primers ordinadors en un departament, habitualment informàtica o comptabilitat. Es produeix un augment espectacular de la productivitat i la capacitat de gestió.
2. **Fase de contagi:** Altres departaments observen els beneficis i també volen informatitzar-se, encara que sigui de manera descoordinada.
3. **Fase d’integració:** Davant del caos i la duplicació de dades, es veu la necessitat d’integrar totes les aplicacions en un sistema comú. Aquesta fase sol ser costosa i complicada.

### Exemple
Un exemple clar del caos abans de la integració és quan el Col·legi d’Enginyers Industrials va voler centralitzar la informació dels col·legiats. El Col·legi d’Enginyers va encarregar a en Marc un sistema que recollís informació sobre els col·legiats. Per fer-ho, necessitaven una taula amb aquesta informació, i es van tornar bojos per a obtenir-la. Ell i els seus empleats van trobar més de 30 versions diferents de la base de dades repartides en diferents màquines.

## Evolució de tecnologies
L’evolució del desenvolupament de programari ha passat per diferents etapes que han anat reduint la complexitat i augmentant la productivitat:

ASM/Binari -> COBOL -> SQL -> RAD -> REPORTS

Cada nova tecnologia ha permès fer en menys línies de codi allò que abans requeria molt més esforç. Contràriament al mite que la tecnologia elimina llocs de treball, el que s’ha vist és que els desenvolupadors han passat a fer tasques més complexes i de més valor afegit.

### De la centralització als ordinadors personals
Inicialment, la informàtica tendia cap a la centralització: grans ordinadors controlats per empreses. Però a Silicon Valley, molts joves hi estaven en contra i van impulsar el moviment Do It Yourself, influenciats pel [Whole Earth Catalog](https://en.wikipedia.org/wiki/Whole_Earth_Catalog), una mena de Wikipedia primitiva. D'aquí en van sortir iniciatives com el [Homebrew Computer Club](https://en.wikipedia.org/wiki/Homebrew_Computer_Club), on els usuaris es muntaven els seus propis ordinadors, i posteriorment, ordinadors personals com l'[Apple II](https://es.wikipedia.org/wiki/Apple_II), l’[IBM PC](https://en.wikipedia.org/wiki/IBM_Personal_Computer).

Aquest canvi va permetre que petits negocis, autònoms i fins i tot grans empreses accedissin als PCs, trencant el monopoli del coneixement centralitzat. Seguint el model d’Adam Smith, a les empreses el coneixement estava tancat dins l’organització, i ningú sabia fer res fora del seu rol. 

Amb l’expansió dels PCs, va sorgir un problema important: la falta d’interoperabilitat entre sistemes. En aquella època, Els sistemes i aplicacions no estaven pensats per comunicar-se entre si, ni a nivell de maquinari ni de programari. El 1993, Microsoft va respondre amb l'[Object Linking and Embedding (OLE)](https://en.wikipedia.org/wiki/Object_Linking_and_Embedding) a [Windows 3.11](https://en.wikipedia.org/wiki/Windows_3.1), permetent copiar i enganxar entre programes i millorant la integració.