# Místnost a systém (Home)

## 1) Prostor

- Název prostoru: Home
- Typ prostoru: obytná místnost / obývák
- Rozměry půdorysu:
  - délka ve směru vyzařování repro: 4.90 m
  - šířka místnosti: 7.00 m
- Výška místnosti: 3.30 m
- Přibližný objem: cca 113.2 m3

Praktická poznámka:
- repro nejsou v místnosti symetricky, což je důležité pro interpretaci L/R rozdílů v basech i ve středobasu

První akustický odhad z rozměrů:
- axiální módy v pásmu `20-120 Hz` vycházejí zhruba na `24.5`, `35.0`, `49.0`, `52.0`, `70.0`, `73.5`, `98.0`, `103.9` a `105.0 Hz`
- jde o dobrý první rámec pro interpretaci peaků kolem `44-50 Hz` a `70-75 Hz`

## 2) Rozmístění repro

- systém: stereo pár Bowers & Wilkins 685
- typ: 2-way bass reflex compact speaker
- půdorysný footprint jedné bedny: 198 mm (šířka) × 331 mm (hloubka)
- výška středu repro: 1.00 m
- vzdálenost střed-střed: 2.20 m
- vzdálenost zadní stěny repro od zadní stěny místnosti: 0.065 m
- z toho plyne půdorysný střed skříně cca 0.231 m od zadní stěny místnosti

Boční umístění:
- pravá bočnice pravého repro: 0.10 m od boční stěny místnosti
- střed pravého repro: cca 0.199 m od pravé boční stěny místnosti
- střed levého repro: cca 4.60 m od levé boční stěny místnosti
- levá bočnice levého repro: cca 4.50 m od levé boční stěny místnosti

Praktický dopad:
- velmi malá vzdálenost zadní stěny repro od zadní stěny místnosti i malá mezera pravého repro od boční stěny zvyšují pravděpodobnost silné boundary gain podpory a L/R asymetrie
- pravý a levý kanál tak pracují v jiné vazbě na stěny, takže je očekávatelná L/R asymetrie v odezvě i v decay

## 3) Technické specs modelu

- výrobce: Bowers & Wilkins
- model: 685
- roky výroby: 2007-2014
- ozvučnice: 2-way, 2 driver, bass reflex
- woofer / midbass: 1× 165 mm Kevlar cone
- tweeter: 1× 25 mm aluminium dome
- doporučený výkon zesilovače: 25-100 W
- citlivost: 88 dB (2.83 V / 1 m)
- impedance: 8 ohm, minimum cca 3.7 ohm
- dělící frekvence: 4 kHz
- rozměry jedné bedny: 340 × 198 × 331 mm (V × Š × H)
- hmotnost jedné bedny: cca 7 kg

Poznámka k publikovaným frekvenčním údajům:
- v dostupných podkladech se objevují dvě různé formulace: `49-22 000 Hz (±3 dB)` a širší katalogové `42 Hz-50 kHz`
- pro tuto dokumentaci je důležitější reálné in-room měření než samotný katalogový rozsah

## 4) Měřicí pozice

Společné:
- výška mikrofonu ve všech pozicích: 1.00 m

Pozice:
- `u TV`: bližší pozice u televize, kde se hrají hry s gamepadem; cca 1.80 m od stěny, na které jsou repro; přibližně v ose repro
- `gauč`: cca 4.0 m od repro, v ose repro
- `střed obýváku`: geometrický střed místnosti

## 5) Zvukový řetězec a režim měření

- software: REW
- zvukovka / interface: Scarlett 2i2 4th Gen
- mikrofon: t.bone MM-1
- kalibrace mikrofonu: frekvenční charakteristika odečtena v REW, stejně jako u měření Industra
- zesilovač: Denon PMA-495R
- stav zesilovače: modifikovaný / recapped by CASEA, protokol datovaný `1.4.2025`
- pro měřicí řetězec jsou nejdůležitější tyto úpravy zesilovače:
  - hlavní filtrace `2× EPCOS 10 000 uF / 63 V`
  - `HEXFRED` diody v hlavním napájecím zdroji
  - nové lokální zdroje a vyčištěné / opravené přepínače a relay
- phono a korekční op-ampy byly také měněné, ale při tomto měření je zesilovač používaný v line větvi a v režimu `source direct`
- `source direct` zde obchází `balance`, `bass`, `treble` a `loudness`, takže korekční větev není pro tohle měření v aktivní signálové cestě
- sample rate: 48 kHz
- sweep: 256k log sweep, 2 opakování
- sweep level: -12.2 dBFS
- EQ / tone controls: bez EQ, zesilovač v režimu `source direct`

Gain staging:
- gain mikrofonu a hlasitost zesilovače nebyly kalibrovány na absolutní SPL
- praktické pravidlo bylo: dostatečně hlasitě, ale bez clippingu

To znamená:
- měření jsou vhodná hlavně pro vzájemné porovnání tvaru křivek, decay a L/R rozdílů
- absolutní SPL čísla nebrat jako přesně kalibrovaný referenční level prostoru

## 6) Loopback metoda

Jednotlivé kanály:
- při `L` měření jde výstup L do zesilovače a reference se vrací přes `tape out` do vstupu 2 zvukovky
- při `R` měření stejná logika pro pravý kanál

Současné `L+R` měření:
- protože zvukovka nemá třetí dedikovaný referenční výstup, timing reference je při `L+R` vázaná na jeden kanál

Praktický závěr:
- pro domácí stereo room response je tento postup použitelný
- pro přesné inter-channel timing rozhodování mezi L a R to není ideální laboratorní metoda
- pro tento projekt je důležitější konzistence postupu než absolutní přesnost mezi kanály

## 7) Co je už změřeno

Z exportů jsou aktuálně k dispozici:

- `u TV`: `L`, `R`, `L+R`
- `gauč`: `L`, `R`, `L+R`
- `střed obýváku`: `L+R`

Exportované datové sady:
- `SPL Phase phase/`
- `impulse responses/`
- `RT60/`
- waterfall PNG pro jednotlivé kanály
- SPL PNG overlaye pro `u TV`, `gauč` a přehled `L+R`
- RT60 PNG pro `u TV` a `gauč`

Poznámka:
- `střed obýváku` je v této sérii jen orientační referenční `L+R` bod, ne plná diagnostická pozice s odděleným `L` a `R`

## 8) Ilustrace postavení

![Půdorys Home](illustrace_pudorys_home.svg)