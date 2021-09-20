# Normaliseren

## Theorie

Om een database te creeëren, moet er vooraf bekend zijn hoe de database eruit moet zien. 
Ga je eerst een website schrijven en daarna je database maken, kom je eindeloos veel
problemen tegen. Als je eerst een website maakt, maar er vervolgens achterkomt dat je
te weinig ruimte hebt vrijgelaten voor tekst of in je database wat waarden mist, kun
je weer bijna van vooraf aan beginnen om alles op te schuiven.

We beginnen dus met het maken van een database, volgens de regels van het 
[normaliseren](https://nl.wikipedia.org/wiki/Databasenormalisatie).
Het komt er op neer dat alle informatie die nodig is, minimaal en maximaal één keer
opgeslagen wordt. Als je van 17 miljoen mensen wilt bijhouden of ze wel of niet
gevaccineerd zijn, kun je maar beter geen dubbele informatie bijhouden, want dan wordt
je database veel te groot en traag. Daarnaast moet je geen data bijhouden die gebaseerd
wordt op andere data; bijvoorbeeld: geen leeftijd, maar geboortedatum, want die 
leeftijd kun je dan altijd opnieuw uitrekenen.

De basisregels van normaliseren zijn dus:
- Vermijd dubbele gegevens
- Vermeld geen gegevens die bepaald worden op basis van andere gegevens

En specifiek voor databases in php:
- Splits alle gegevens van één datatype waar mogelijk uit!

## Praktijk

Het simpelste is uiteraard om één hele grote Excelsheet te maken waar je alles bij
elkaar opslaat. We kunnen dan echter niet voldoen aan de basisregel dat gegevens maar
één keer voor mogen komen. Denk bijvoorbeeld aan vaccinatie: als iemand voor de
tweede keer gevaccineerd komt worden, hoeven we niet nogmaals alle gegevens in te
vullen. Het liefst verwijzen we naar één uniek nummer (BSN), waaraan alle gegevens
als naam, adres en woonplaats gekoppeld zijn.

Er zijn dus altijd meerdere tabellen noodzakelijk om een genormaliseerde database
te maken. Grofweg voor elk object dat er in het spel is, maak je een tabel.
Bij het voorbeeld hierboven 1) de persoon, en 2) het vaccin. Of bijvoorbeeld een
autogarage: 1) de persoon, en 2) de auto in onderhoud. Er zijn ook onderwerpen
waarvoor meer dan twee tabellen nodig zijn, zoals bijvoorbeeld 'alle lp-nummers
sinds 2000'; daarbij gebruik je bijvoorbeeld 1) de artiest, 2) de lp-titel, en 
3) de liedjes op de lp.

## Voorbeeld

**Gevaccineerden**
|BSN|Voorletters|Tussenvoegsel|Achternaam |Straatnaam     |Huisnummer|Toevoeging|Postcode|Woonplaats|
|:-:|:----------|:------------|:----------|:--------------|:---------|:---------|:-------|:---------|
|1  |SJ         |             |Boonstoppel|Haverveld      |41        |          |3902EA  |Veenendaal|
|2  |P          |van der      |Berg       |Mulderslaan    |1         |          |3905GA  |Veenendaal|
|3  |MA         |             |Xavier     |Jan Linsestraat|8         |A         |6717JW  |Ede       |

**Vaccinaties**
|ID |BSN|Type   |Datum     |Bijzonderheden                                     |
|:-:|:-:|:------|:---------|:--------------------------------------------------|
|1  |1  |Moderna|21-03-2021|                                                   |
|2  |3  |Janssen|22-03-2021|Flauwgevallen na 5 minuten                         |
|3  |1  |Moderna|08-05-2021|Week lang migraine gehad na eerste prik            |
|4  |2  |Pfizer |10-05-2021|                                                   |
