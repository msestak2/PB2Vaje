# Naloga 3 (MongoDB)

Prijavite se v oblačno storitev MongoDB Atlas (https://www.mongodb.com/products/platform/atlas-database). Po uspešni prijavi ustvarite nov projekt.

Znotraj ustvarjenega projekta ustvarite novo gručo (opcija _Create Cluster_ oz. _Build a Cluster_).

Konfigurirajte gručo z naslednjimi parametri:
- izberite brezplačno M0 okolje za vzpostavitev MongoDB gruče
- vpišite poljubno ime gruči (parameter _Name_ pod sekcijo _Configurations_)
- kot ponudnika storitve izberite AWS in kot regijo Frankfurt

Po vnosu parametrov izberite _Create Deployment_ in počakajte, da se gruča vzpostavi. Preden se povežete na gručo, potrebno je ustrezno konfigurirati dostop, in sicer v meniju na levi strani:

- pod opcijo _Database Access_ dodajte novega uporabnika, ki se avtenticira s pomočjo uporabniškega imena in gesla ter ima vlogo Atlas administratorja (opcija _Built-in Role_)
- pod opcijo _Network Access_ nastavite gručo na javno (0.0.0.0) ali trenutni IP naslov

Ko je gruča pripravljrna in dosegljiva, se na njo lahko povežete z namiznim orodjem MongoDB Compass. V MongoDB Atlasu pri ustvarjeni gruči izberete opcijo _Connect_ > _Compass_ in prevzamete orodje, če ga nimate predhodno nameščenega, oz. kopirate znakovni niz za povezavo do gruče.
Znakovni niz v obliki "mongodb+srv://<db_username>:<db_password>@<hostname>/" izpolnite z vašimi uporabniškimi podatki in ga vnesete pri ustvarjanju nove povezave v orodju MongoDB Compass.

Ko ste se uspešno povezali na strežnik, lahko ustvarite novo bazo z imenom "pb2 "in kolekcijo "lodging" znotraj te baze (opomba: postopek lahko izvedete tudi v spletnem vmesniku Atlasa). 
Znotraj kolekcije "lodging" izberite opcijo _Add Data > Import JSON or CSV file_ ter izberite pot do lokalne datoteke _lodging.json_, ki vsebuje vnose z opisom namestitev, ki jih imajo gostitelji v različnih mestih ter njihovi ponudbi.

V drugem delu naloge je potrebno zgenerirati podatke za dodatno kolekcijo _employees_, v kateri boste beležili podatke o zaposlenih v prvih 500 namestitev v kolekciji _lodging_. Za vsakega zaposlenega je potrebno beležiti podatke, kot so ime, priimek ter datum rojstva delavca ter seznam njegovih zaposlitev, pri čemer gnezdeni objekt naj vsebuje podatke o plači, časovnem obdobju zaposlitve (nekateri zaposleni naj nimajo trenutnih zaposlitev) ter ID namestitve, v kateri je bil delavec/ka aposlen/a.
Zgenerirano datoteko s podatki tudi uvozite v zasebno kolekcijo _employees_.

Po uspešnem uvozu podatkov je potrebno pripraviti povpraševanja s pomočjo sintakse MongoDB povpraševalnega jezika, s katerimi boste dobili odgovore na naslednja vprašanja:
1. Izpišite seznam vseh gostiteljev, pri čemer izpišite samo njihovo ime, priimek in starost.
2. Izpišite seznam vseh namestitev, sortiranih najprej po ceni, in nato po številu postavk dodatne ponudbe.
3. Izpišite seznam vseh namestitev iz zvezne države Ohio, kjer gostitelj govori slovensko ali pa ima povprečno število točk nad 7,5.
4. Za vsako namestitev izpišite vsako tretjo in vsako nadaljnjo kritiko, ki jo je namestitev dobila. Če je dobila samo dve kritiki ali manj, namesto tega izpišite vse kritike, ki jih je namestitev dobila.
5. Preštejte in sortirajte število namestitev po zveznih državah, pri čemer upoštevajte samo aktivne gostitelje, ki so se registrirali pred marcem 2013.
6. Izpišite vse kombinacije števil točk, ki so bile podeljene namestitvam, in jih sortirajte po številu namestitev, ki so ta števila točk dobile.
7. Izpišite seznam vseh namestitev (lodging), ki so dobile vsaj 3 kritike, pri čemer je večina dobljenih ocen (polovica ali več vseh ocen namestitve) višja od 6.
8. Izpišite podatke o namestitvi, ki ponuja najvišjo povprečno plačo svojim zaposlenim. V rezultatu izpišite tudi znesek povprečne plače.
9. Izpišite podatke o top 5 delavcih, ki so najdlje časa zaposleni v aktivnih namestitvah, sortirano padajoče po času zaposlitve.
10. Izpišite povprečno plačo zaposlenih za namestitev, ki ima največjo povprečno oceno. Rezultat sortirajte naraščajoče po povprečni plači.


Rešitve oddate v obliki Word datoteke, v katero vključite sintakso poizvedbe za posamezno vprašanje ter posnetek zaslona z rezultati povpraševanj.

