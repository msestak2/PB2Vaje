
# Naloga 2 (analiza učinkovitosti MySQL baze)

V E-R modelu vaše baze iz prve naloge izberite dve tabeli (entiteti) povezani z relacijo 1:M. Vsaka tabela naj ima vsaj 3 stolpca za boljše rezultate. Tabela brez tujega ključa je neodvisna tabela, tabela u tujim ključim pa odvisna.

Za izbrani scenarij je potrebno najprej izvesti merjenja učinkovitosti povpraševanj nad tabelama v normalizirani bazi, in sicer glede na:
- prisotnost omejitve tujega ključa - v primeru brez omejitve je potrebno najprej izvesti ukaz ALTER TABLE....DROP CONSTRAINT, s katerim odstranite tuji ključ, preden začnete testirati povpraševanja
- prisotnost enostavnih in sestavljenih indeksov
- velikost tabel (100.000 ali 1.000.000 vrstic)

Meritve izvajate za isti nabor povpraševanj, in sicer merite čas izvajanja INSERT, UPDATE (vseh ali določenih vrstic), SELECT (osnovno ali napredno filtriranje) in DELETE operacij (vseh ali določenih vrstic). Pri določanju pogojev za filtriranje in indekse uporabite smiseline atribute (ne primarni ključ!).
Sintakso poizvedb pripravite tako, da bodo uporabljale indekse (uskladite stolpce, nad katerimi ustvarite indekse, in stolpce, ki jih uporabljate za filtriranje).

Čas izvajanja posameznih poizvedb zapišite v ustrezno celico v obrazcu _Obrazec_naloga2.xlsx_. Dodatno pri vsaki meritvi z uporabo ukaza EXPLAIN izpišite tudi podrobnosti glede načina izvajanja poizvedbe. Npr: EXPLAIN SELECT ime, priimek FROM oseba WHERE datumRojstva > '2000-01-01';
Tabelo, ki jo dobite kot rezultat EXPLAIN ukaza, posnamete in dodate v zavihek _Posnetki zaslona_ v obrazcu.

V drugem delu naloge je potrebno pripraviti kopijo MySQL baze, v kateri vpeljete denormalizacijo, in sicer 4 primera:
- ponavljajoče skupine
- podvojitev atributov v 1:1 relaciji
- podvojitev atributov v 1:M relaciji
- podvojitev atributov v M:N relaciji

Pripravite denormalizirani E-R model, implementirajte bazo na podlagi tega modela in prilagodite shranjene procedure za polnjenje tabel.

Tukaj merite le čase izvajanja SELECT povpraševanj, tako da je potrebno pripraviti sintakso 4 SELECT povpraševanj, ki so oblikovana na način, da vključujejo filtriranje na podlagi stolpcev, nad katerih ustvarite indekse.
Pri merjenjih primerjate čase izvajanja SELECT poizvedb nad normalizirano (originalno) bazo iz 1. naloge ter denormalizirano bazo.
