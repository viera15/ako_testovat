Ako testovať upload a sťahovanie súborov



Príklad:

Predstav si firemnú aplikáciu, kde zamestnanci nahrávajú faktúry vo formáte PDF. Účtovníčka stiahne súbor a uloží ho do archívu. Po nasadení novej verzie zistia, že niektoré súbory sa nedajú otvoriť, majú nesprávny názov alebo link na stiahnutie smeruje do iného adresára (napr. na inú tlačovú zostavu). Takéto chyby môžu spôsobiť stratu dôležitých dokumentov, porušenie legislatívy alebo zdržanie práce.

Ako otestovať upload a sťahovanie súborov:

Podporované typy súborov

Over, že aplikácia prijíma len povolené typy (napr. PDF, DOCX, JPG) a odmieta nepovolené (napr. EXE, skripty).

Skontroluj správnu identifikáciu podľa MIME typu aj prípony.

Limity veľkosti

Testuj maximálnu povolenú veľkosť (napr. 10 MB) aj hraničné prípady.

Over správanie pri prázdnom súbore.

Validácia obsahu

Uisti sa, že súbor nie je poškodený po nahratí/stiahnutí.

Over kódovanie pri textových súboroch.

Názvy súborov

Skontroluj, či sa názvy uchovávajú alebo správne generujú.

Otestuj reakciu na rovnaký názov (prepísanie, verzovanie, chyba).

Práva prístupu

Over, že súbor môže stiahnuť len oprávnený používateľ.

Skús priamy prístup cez URL bez prihlásenia alebo s inou rolou.

Správnosť umiestnenia súboru

Over, že link vedie na správny adresár alebo tlačovú zostavu.

Otestuj prípadné presmerovanie a chybové správy.

Šifrovanie a bezpečnosť

Over prenos súborov cez HTTPS.

Ak sa ukladajú na serveri, skontroluj šifrovanie (ak je požiadavka).

Výkon a stabilita

Testuj pri pomalom internete alebo prerušení pripojenia.

Skontroluj správanie pri hromadnom nahrávaní/ťahaní.

Kompatibilita

Over fungovanie vo viacerých prehliadačoch a zariadeniach.

Skontroluj správanie v rôznych OS.



#softwaretesting #qa #testovanie #manualtesting #qualityassurance #upload #download #security #testscenarios



