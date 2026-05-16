# Doporučení 2026-05-16 (Home, BW 685)

Tato doporučení vycházejí z aktuální sady měření `L`, `R`, `L+R` v pozicích `u TV`, `gauč` a `střed obýváku`.

## 1) Hlavní závěr

Největší problém aktuálního domácího setupu není výkon nebo chybějící bas, ale:

- silná módová nerovnoměrnost v basech
- výrazná asymetrie mezi levým a pravým kanálem
- zhoršení v pozici gauče oproti bližšímu bodu `u TV`

Z měření vychází, že kritické pásmo je hlavně cca 40-80 Hz a sekundárně 80-200 Hz.

## 2) Co je pravděpodobná příčina

### Excentrické postavení repro

- pravý repro je velmi blízko boční stěně
- levý repro pracuje v jiném geometrickém vztahu k bočním hranicím prostoru

To znamená:

- jiná boundary gain podpora pro L a R
- jiná síla prvních bočních odrazů
- jiná modal excitace v basech

### Malá vzdálenost od zadní stěny

- zadní mezera skříně je cca 6.5 cm
- při hloubce skříně 331 mm to znamená půdorysný střed skříně cca 23.1 cm od zadní stěny

To pravděpodobně:

- zvyšuje nízkofrekvenční excitaci místnosti
- zhoršuje rovnoměrnost v pásmu lower-bass / upper-bass
- komplikuje rozlišení, zda je problém primárně od polohy beden, nebo poslechového místa

### Gauč je v horším bodě místnosti

- v exportech i PNG grafech je gauč nejproblematičtější bod
- zejména oblast kolem 44-50 Hz je tam výrazněji přítomná a déle doznívá

## 3) Co dělat jako první

### Krok 1: nepoužívat EQ jako první zásah

Dokud nejsou ověřeny aspoň 1-2 rozumné geometrické varianty, EQ by jen maskovalo problém jednoho bodu a mohlo zhoršit jiný.

### Krok 2: brát `u TV` jako referenční bod

Pro další A/B porovnání používat hlavně:

- `u TV` jako hlavní referenci
- `gauč` jako kontrolní bod, jestli se změna nezhoršila v reálném poslechu

### Krok 3: držet střed obýváku jako lehkou orientační referenci

V této sérii je `střed obýváku` jen `L+R` referenční bod. To je v pořádku, pokud jeho role zůstane orientační a hlavní rozhodování poběží přes `u TV` a `gauč`.

## 4) Doporučená fyzická testovací matice

### Varianta A: změna vzdálenosti od zadní stěny

Držet boční postavení stejné a testovat jen hloubku repro:

1. současný stav: 20 cm
2. zadní mezera 20 cm
3. zadní mezera 35-40 cm

Pro každou variantu změřit minimum:

1. `L u TV`
2. `R u TV`
3. `L+R u TV`
4. `L+R gauč`

Cíl:

- zmenšit dominance v 40-80 Hz
- zkrátit decay v 50-100 Hz
- nesrazit příliš 80-200 Hz energii

### Varianta B: zlepšení boční symetrie

Pokud je prostor dovolí, priorita je odsunout pravý repro dál od boční stěny nebo přiblížit levý ke srovnatelnější vazbě.

Nemusí vzniknout perfektní geometrická symetrie, ale i menší zlepšení může pomoct:

- omezit rozdíl L/R v basech
- zlepšit stereo stabilitu
- snížit dominanci pravého kanálu v problematických pásmech

### Varianta C: poslechové místo

Pokud se ukáže, že gauč zůstává výrazně horší i po přesunu repro, je potřeba otestovat menší posun gauče v ose délky místnosti.

Doporučení:

1. posun vpřed nebo vzad po cca 20-30 cm
2. vždy měřit aspoň `L+R`
3. pokud se objeví zlepšení, doplnit i `L` a `R`

## 5) Jak rozhodovat mezi variantami

Nevyhodnocovat jen nejvyšší peak. Rozhodování dělat podle kombinace:

1. průměr 40-80 Hz
2. průměr 80-200 Hz
3. T30/T20 v 50, 80 a 100 Hz
4. L/R podobnost v `u TV`
5. subjektivní čitelnost basu a středu

Praktické pravidlo:

- lepší varianta není ta s největším basem, ale ta s nejmenší nerovnoměrností a kratším dozníváním

## 6) Co zatím nedoporučuji

- finální EQ preset na základě jediné současné geometrie
- rozhodování jen podle `L+R`
- hodnotit kvalitu setupu jen z gauče
- snažit se ručně dorovnávat problém gainem levého/pravého kanálu

## 7) Doporučený další minimální plán

1. udělat jednu A/B sérii s větší vzdáleností repro od zadní stěny
2. pokud to jde, zmenšit boční asymetrii pravého repro
3. opakovat měření `u TV` + `gauč`
4. držet `střed obýváku` jako lehkou `L+R` kontrolní referenci
5. teprve potom řešit, jestli dává smysl jemné EQ

## 8) Event možný test plan

Reálně dává smysl otestovat dvě konkrétní mechanické změny:

1. zadní mezera repro od stěny z cca `6.5 cm` na cca `8 cm`
2. pravý repro od boční stěny z cca `10 cm` na cca `30 cm`

Pracovní očekávání:

- změna `6.5 cm -> 8 cm` je malá a sama o sobě nejspíš neudělá zásadní rozdíl
- změna `10 cm -> 30 cm` u pravého repro je smysluplná a může měřitelně zlepšit L/R asymetrii i boundary gain problém pravého kanálu

Proto doporučený postup:

1. nechat aktuální stav jako baseline
2. udělat hlavně test s posunem pravého repro od boční stěny
3. zadní změnu řešit maximálně jako jemný sekundární krok, ne jako hlavní tuning move

Minimum po změně přeměřit:

1. `L u TV`
2. `R u TV`
3. `L+R u TV`
4. `L+R gauč`

Co porovnávat:

1. přiblížení `R` k `L`
2. menší přebytek v `40-80 Hz`
3. lepší rovnoměrnost v `80-200 Hz`
4. menší problémovost gauče oproti baseline

Rozhodovací pravidlo:

- lepší je varianta s menší asymetrií a klidnějším decay, ne ta s největším basem