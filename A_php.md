# Inleiding PHP (origineel: Personal Home Page)

PHP spant samen met HTML en CSS de kroon op websites. Eigenlijk elke dynamische website maakt gebruik van PHP (al zou je soms ook JavaScript kunnen gebruiken).

De officiële handleiding voor alle functies en mogelijkheden is te vinden op http://php.net/manual/en/.
Op deze pagina vind je vooral de *essentials* voor het gebruik op je eigen website.

## Basis

In een html-pagina kun je blokjes php-code plaatsen. Daarna moet
je de pagina opslaan als .php-bestand. Op de meeste webservers
wordt php-code in een .html-bestand niet goed verwerkt. 

Opmerkingen en toelichtingen bij je code zet je achter // . 
Alles wat achter // staat wordt niet uitgevoerd als code. 
Toelichtingen zijn handig als je code wat uitgebreider wordt of 
als je met meerdere mensen samenwerkt aan een project.

```php
<?php                 // dit betekent: begin php-code
echo 'Hello world';   // echo is print() van Python, maar dan weergeven op de pagina
?>                    // dit betekent: einde php-code
```

<kbd>echo</kbd> is één van de meest gebruikte functies. Daarmee stuur 
je tekst etc. naar het scherm. Zet een tekenreeks altijd tussen 
' ' (apostrof). Wil je in de tekenreeks zelf een apostrof 
gebruiken, zet er dan een \ voor. Eindig een regel in php 
altijd met ; (puntkomma), net als in C++ bij de Arduino!

## Met databasegegevens

Als je met MYSQL een databaserecord hebt opgehaald, kun je de 
resultaten op je scherm krijgen met bijv. 

```php
<?php
echo $d['Voornaam'];  // print de variabele die de naam Voornaam heeft in je database
?>
```

Je kunt dit combineren met html-code. Html-code hoef je niet 
per se binnen php-instructies te zetten; erbuiten werkt ook.
Het is een kwestie van persoonlijke voorkeur. Op internet
wordt html vaak in php gestopt, maar stiekem heeft Bns een
voorkeur om php in html te stoppen.

Vergelijk:

```php
<body>
<?php                                       // html binnen php
  echo '<h1>'.$d['Naam'].'</h1>
  <p>'.$d['Adres'].'<br>
  $d['Postcode'].' '.$d['Plaats'].'</p>';?>
</body>
```
met:
```php
<body>                                      // php binnen html
  <h1><?php echo $d['Naam'];?></h1>
  <p><?php echo $d['Adres'];?><br>
  <?php echo $d['Postcode'];?> <?php echo $d['Plaats'];?></p>
</body>
```
Al kun je de laatste versimpelen door wat overzichtelijkheid op te offeren:
```php
<body>                                      // php binnen html
  <h1><?=$d['Naam']?></h1>
  <p><?=$d['Adres']?><br>
  <?=$d['Postcode']?> <?=$d['Plaats']=?></p>
</body>
```

Kies zelf, maar kies wel het liefst bewust voor één methode!
