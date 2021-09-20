# Informatie over je website

Iedereen heeft een eigen website. Je kunt deze vinden op
**leerlingnummer.ichthuscollege.in**.

In de vierde klas heb je met html en css al eens een eigen website
gebouwd, aan de hand van de template **Eracle**. Voor het gemak gebruiken
we die nu weer opnieuw. Deze keer gaat het er niet om dat je website
tot in de puntjes perfect is en alles 100% accuraat is. Deze periode
ligt de nadruk op het gebruik van en verbinden met de **database**, maar
dat gaat automatisch samen met html en css. Hopelijk blijft html en css
daarna ook voldoende hangen om er later nog wat mee overweg te kunnen.

## FTP en Filezilla

Om je website te publiceren, moet je de html, css en php-bestanden op
een of andere manier op je website te zetten. Dat kan met behulp van
het programma **Filezilla** (geïnstalleerd op de computer).

Als je Filezilla opent, zie je bovenin vier velden: host, username,
password en port. Deze gegevens zijn achtereenvolgend: 
leerlingnummer.ichthuscollege.in, je leerlingnummer, je wachtwoord
dat je via ItsLearning hebt gekregen, en port mag je leeg laten.
Klik vervolgens op **Quickconnect**, en accepteer eventuele meldingen.

Aan de linkerkant zie je halverwege je eigen mappen, en eronder de bestanden
in de geselecteerde map. Aan de rechterkant zie je de mappen en bestanden
die er op je website staan. Als het goed is staat er op je website
een map genaamd *public_html*. Daar komen de bestanden van jouw
website in te staan. 

Download nu eerst Eracle, en **unzip** de map. Ga vervolgens terug naar
Filezilla, zoek links de map Eracle op en open die. Open aan de
rechterkant de map public_html. Selecteer links alle bestanden uit
de map -> rechtermuisknop -> **Upload**. Als dat afgerond is, kun je je
eigen website openen en genieten van het prachtige Up!-plaatje.
**Check** je website dus of het uploaden is gelukt!

## Cpanel en database

De instellingen en database van je website
kun je vinden op het **cpanel**. Jouw cpanel vindt je op
leerlingnummer.ichthuscollege.in:2083; je gebruikersnaam is je
leerlingnummer en je wachtwoord heb je gekregen via ItsLearning.

Om een database aan te maken en te kunnen bewerken moet je 
achtereenvolgend de volgende stappen uitvoeren:

1) log in op je **cpanel**,
2) ga naar **MySQL; Databases**,
3) maak een database aan met de naam Huisjes of Vaccinaties bij **Create New Database**,
4) maak een database-user aan bij **Add New User**,
5) koppel de database-user aan de database bij **Add User To Database** en vink *All privileges* aan.
