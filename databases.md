# Database construeren

In de *startopdracht normaliseren* heb je geleerd hoe
een database in elkaar steekt en hoe je er zelf een moet
bouwen. Dat gaan we nu voor de echte website regelen.

## Van Excel naar CSV

Het is makkelijk om in Excel te beginnen: je kunt er makkelijk
wat toevoegen, schrappen en aanpassen (een stuk makkelijker dan
op de website zelf). Dit is dus de stap waar je het meeste moet
nadenken: doe je het nu goed, dan rolt de rest er vanzelf achteraan.

1) start een nieuw Excel-document. Elk **tabblad** in dit document staat voor een **tabel** op je website.
2) maak op elk tabblad de benodigde **kolommen**. Denk hierbij heel goed na! Zie hieronder voor de regels/eisen aan de kolommen.
3) vul vervolgens op elk tabblad vast de informatie in die je hebt. Zoals de informatie van je **huisjes/medewerkers**.
4) als je **lege** tabbladen hebt, vul je hier vast 2 of 3 kolommen met wat **standaardwaarden**. Vul bij een huurder bijvoorbeeld je eigen informatie vast in. Hiermee kun je straks checken of je je werk goed hebt gedaan.
5) **sla** je Excel-document **op**.
6) sla vervolgens elk tabblad op als **CSV (MS-DOS)**.
7) zoek in Windows Verkenner zo'n CSV-bestand op -> rechtermuisknop -> **Open in Notepad++** en controleer welk teken er tussen de velden staat.

## Van CSV naar database

We gaan nu naar het cpanel om daar de database op de website
aan te maken. Vervolgens kunnen we daar het CSV-bestand
importeren en is je database direct gevuld met informatie.

1) log in op je **cpanel**.
2) open **phpMyAdmin**.
3) klik links op de database die je eerder gemaakt hebt, en voeg hier evenveel **tabellen** toe als je tabbladen hebt in je Excel-bestand. Geef ze ook een nuttige **naam**.
4) ga vervolgens voor elke tabel naar **Structure** en voeg onder elkaar de namen van je kolommen toe, met het **datatype** dat er in die kolom staat. Zie onderstaand overzicht voor de datatypes.
5) noem de eerste kolom **altijd** ID, kies bij Index voor **Primary** en vink **A_I** aan. De andere kolommen maken *geen* gebruik van die twee functies.
6) kies vervolgens voor **Import**, en kies voor elke tabel het goede CSV-bestand. Selecteer het **scheidingsteken**, en vink aan dat je de eerste **query** wilt **overslaan** (de regel met kolomnamen).
7) importeer vervolgens het bestand, en als het goed is gegaan komt er een mooie groene balk; krijg je een **error**, lees dan goed wat er staat en probeer het probleem op te lossen. Vraag de **docent** als het niet lukt.

## Datatypes

De veelgebruikte datatypes zijn:

- integer (heel getal); lengte opgeven is niet nodig
- date (datum); lengte opgeven is niet nodig, ziet eruit als 2021-09-18
- float (kommagetal); lengte opgeven is verplicht: bijvoorbeeld 9,3 voor 9 cijfers waarvan 3 achter de komma
- varchar (weinig letters en cijfers); lengte opgeven is verplicht
- text (veel letters en cijfers); lengte opgeven is niet nodig
