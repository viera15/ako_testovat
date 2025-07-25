# Ako testovať SQL injection a XSS útoky<br><br>

SQL-injekcia a XSS (Cross-Site Scripting) sú dva najčastejšie útoky, ktoré zneužívajú špeciálne znaky v používateľskom vstupe:<br><br>

## SQL-injekcia<br>
Útok, pri ktorom útočník vloží do vstupu časť SQL príkazu tak, aby zmenil vykonávanú databázovú operáciu.<br><br>

**Kľúčové znaky:**<br>
Single quote ' – používa sa na uzavretie reťazcov v SQL.<br>
Semikolon ; – oddeluje viaceré SQL príkazy.<br>

Príklad zraniteľného kódu (PHP):<br>
```

$q = "SELECT * FROM users WHERE username = '$userInput'";

$result = $db->query($q);

Ak userInput = ' OR '1'='1, výsledný SQL je

SELECT * FROM users WHERE username = '' OR '1'='1'
```

a vráti všetkých používateľov.<br><br>

**Ako testovať:**<br>
Do povinného poľa (napr. meno) vložte 
' OR '1'='1; 
očakávajte buď chybu, alebo žiadne neoprávnené údaje.
Vložte 
'; DROP TABLE users; -- 
a sledujte, či sa niečo vymaže.
Overte, že aplikácia nikdy nevracia surový SQL ani stack trace.<br><br>

**Ochrana:**<br>
Používať prepared statements / parameterizované dotazy (napr. PDO s väzbou parametrov).<br>
Na serveri vždy validovať a sanitizovať vstupy.<br>

## XSS (Cross-Site Scripting)<br>
Útok, pri ktorom útočník doplní škodlivý JavaScript do vstupu, ktorý sa neskôr zobrazí iným používateľom.<br><br>

**Kľúčové znaky:**<br>
Angle brackets < > – pre tagy (napr. ).<br>
Single a double quotes ' " – na uzatváranie atribútov.<br>
Môže sa miešať aj so znakom ; v JavaScripte.<br>

Príklad zraniteľného kódu (JS templating):<br>

```
<div>Vitaj, {{username}}</div>
```
<br>
Ak 

```
username = <script>alert('XSS')
```

, prehliadač vykoná kód.<br><br>

**Ako testovať:**<br>

Vložte do textového poľa <br>

```
alert('XSS')
```

; ak sa zobrazí alert, je zraniteľné.<br><br>

**Vyskúšajte varianty:**<br>
Vkladanie do atribútov: `">![](x)`<br>
HTML entity escaping: `<script>`…<br>
Testujte aj v URL parametroch a lebels, ktoré sa dynamicky vkladajú do stránky.<br><br>

**Ochrana:**<br>
Escapovať výstup: nikdy nenechať neohliadnutý vstup priamo v HTML.<br>
Používať bezpečné knižnice (napr. OWASP ESAPI) alebo frameworky s automatickým escapingom (React, Angular…).<br>
Nastaviť Content Security Policy (CSP) na obmedzenie spúšťania neautorizovaných skriptov.<br><br>

Tým, že simuluješ zadanie týchto špeciálnych znakov a overíš, že sa namiesto nich pred odoslaním či zobrazovaním správne escapujú alebo viažu (parameterizujú), zabezpečíš formulár proti týmto typom útokov.<br>
