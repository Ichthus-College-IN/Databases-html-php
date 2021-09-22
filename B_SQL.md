# SQL (officieel: Structured Query Language)

Om data op te halen uit je database, aan te passen,
of in te voegen, maken we gebruik van MySQL. Dit is
de meest bekende taal en niet al te moeilijk. Het is
vooral te herkennen aan de commando's die ongeveer 
volledig in <kbd>Caps Lock</kbd> staan.

De officiële toelichting op de functies vind je hier:
https://dev.mysql.com/doc/mysql-getting-started/en/,
maar als je iets zoekt kun je beter gewoon Googelen
op wat je nodig hebt.

Om met MySQL een bewerking te doen op je database
maken we gebruik van een zogenaamde *query* (Nederlands:
vraag of ondervraging).

Er zijn drie grote types:
* SELECT .. FROM
* INSERT INTO
* UPDATE .. SET

Houd je daarbij aan de volgende afspraken:
* schrijf functiewoorden altijd met hoofdletters
* zet tabel- en veldnamen altijd tussen ``
* zet (tekst)gegevens altijd tussen ''

## SELECT .. FROM .. WHERE

Een algemeen voorbeeld om data uit je database uit
te lezen:

```sql
SELECT * FROM `tabelnaam`;
```

Met * wordt bedoel je: selecteer alle velden. * is
eigenlijk een soort joker. We halen in dit voorbeeld dus
de volledige database op.

We kunnen ook specifiek een enkele rij opvragen, met 
behulp van `WHERE`:

```sql
SELECT * FROM `tabelnaam` WHERE `veldnaam` = 'tekst';
```

Als je dan als veldnaam *ID* gebruikt en een specifiek
ID invoert als tekst, krijg je alle info die hoort bij
die ID, zoals een persoon of huisje.

## INSERT INTO

Data invoegen in een database kan ook. Zie volgend
voorbeeld:

```sql
INSERT INTO `tabelnaam` VALUES (NULL, 'waarde1', 'waarde2', 'waarde3')
```

Deze methode gaat er vanuit dat je in elke kolom nieuwe
informatie toevoegt. Is je data bijvoorbeeld incompleet
of wil je expres niet alles invullen, kun je dat ook
opgeven:

```sql
INSERT INTO `tabelnaam` (`ID`, `veldnaam1`, `veldnaam3`) VALUES (NULL, 'waarde1', 'waarde3')
```

Let op: als het goed is, heeft je kolom ID de functie
*auto_increment* aan staan. Om dan automatische
nummering te kunnen gebruiken, moet je in die kolom
<kbd>NULL</kbd> invoegen.

## UPDATE .. SET .. WHERE

De algemene query om waarden in je database te updaten is:

```sql
UPDATE `tabelnaam` SET `veldnaam` = 'tekst' WHERE `ID` = 'voorwaarde'
```

Let op: je kunt alleen specifieke velden updaten, niet
zomaar een hele lijst tegelijkertijd.
