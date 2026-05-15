# Plán měření a cílů korekcí (Industra)

Tento dokument je zjednodušený do sekvenčního postupu: nejdřív robustně přeměřit, potom teprve navrhnout preset.

Aktuální návrh DSP je jen pracovní hypotéza. Finální preset vznikne až po nové sérii měření s timing reference (loopback).

## 1) Cíl měření

- Ověřit a zlepšit timing sub vs top v pásmu cca 70-100 Hz.
- Snížit boom v pásmu 35-45 Hz.
- Zachovat čitelnost a energii v 70-110 Hz.
- Návrh EQ řešit až po odladění timingu.

## 2) Příprava (před prvním sweepem)

1. Zapnout timing reference přes loopback.
2. Zafixovat gain staging a neměnit ho během jedné série.
3. Zafixovat mikrofonní pozice.
4. Zapsat routing, crossover, polaritu a delay výchozího stavu.

## 2.1 Nejdřív ověřit postavení (před timing maticí)

Porovnat dvě instalační varianty a teprve potom řešit detailní delay/polaritu:

1. Varianta A: současné postavení (suby o 0.5 m před topy).
2. Varianta B: topy níž a předozadně zarovnané se suby (minimální hloubkový offset center).

Pro obě varianty změřit minimum:

1. `SUB_ONLY_LR`
2. `TOP_ONLY_LR`
3. `FULL_LR_base`

Do timing série pokračovat jen s lepší variantou postavení.

Praktická zkratka pro delay rozsah:

- Pokud zůstane Varianta A (suby o 0.5 m vpředu), začít širším hledáním (např. 0.0-2.4 ms).
- Pokud vyjde Varianta B (topy a suby zarovnané v hloubce), začít užším hledáním (např. 0.0-1.2 ms).

Loopback minimum:

- Výstup 1: sweep do PA.
- Výstup 2 -> vstup zvukovky: timing reference.
- Mikrofon na samostatném vstupu.

## 3) Gain pravidlo (odpověď na sub 2/3 vs top max)

- Během jedné timing série poměr sub/top neměnit.
- Timing nejdřív odlaď na jednom fixním poměru, který je realistický pro provoz.
- Až po timingu udělej samostatnou tonal sérii s jiným poměrem hlasitosti.

Doporučený postup poměru hlasitosti:

1. Referenční série: ponech současný poměr (sub cca 2/3, top vyšší), ale oba kanály na každé straně stejně.
2. Po timingu udělej ještě dvě srovnávací série:
   - `sub -2 dB vs reference`
   - `sub +2 dB vs reference`
3. Vyber poměr, který je lepší ve 2 ze 3 pozic a zároveň bez limiterů.

Poznámka: trvalé „top na max“ často zhoršuje headroom. Pro měření je lepší mít rezervu a dorovnat úroveň konzistentně v řetězci.

## 4) Sekvenční měřicí plán

### Krok A: Bedny zvlášť (povinné)

Měř a ukládej v tomto pořadí:

1. `SUB_LEFT`
2. `SUB_RIGHT`
3. `TOP_LEFT`
4. `TOP_RIGHT`
5. `SUB_ONLY_LR`
6. `TOP_ONLY_LR`

Smysl: odhalit asymetrie levá/pravá ještě před kombinováním systému.

### Krok B: Bedny spolu (výchozí FULL)

7. `FULL_LR_base` (delay 0.0 ms, normal polarita)

Smysl: mít referenční FULL křivku pro všechny další varianty.

### Krok C: Timing série ve FULL ON

Ve FULL ON (suby+topy současně) měř:

8. `FULL_delay_0.0_normal`
9. `FULL_delay_0.2_normal`
10. `FULL_delay_0.4_normal`
11. `FULL_delay_0.6_normal`
12. `FULL_delay_0.0_invert`
13. `FULL_delay_0.2_invert`
14. `FULL_delay_0.4_invert`
15. `FULL_delay_0.6_invert`

Pokud minimum vychází mezi kroky, doplň jemněji (např. 0.1 ms kolem nejlepší varianty).

### Krok D: Ověření ve více bodech

Pro základní rozhodnutí použij hlavní bod `M1` (sweet spot).

Pokud bude čas, doplň 1-2 vedlejší body cca +/-1 m kvůli kontrole stability.

## 5) Jak vyhodnotit timing

Primární metrika:

- Pásmo 70-100 Hz ve FULL měření (energie + stabilita mezi pozicemi).

Sekundární metriky:

- Pásmo 35-45 Hz (boom)
- Decay/waterfall v basech
- Subjektivní kick čitelnost

Akceptační pravidlo:

- Timing varianta je přijatá, pokud je nejlepší v bodě `M1` a nezhorší se výrazně při rychlé kontrole v okolních bodech.

## 6) Co exportovat a archivovat

- SPL + Phase (1/12 nebo 1/24 smoothing)
- Impulse response
- RT60/T30
- Decay + Waterfall
- Distortion (orientačně)
- Původní `.mdat`

Názvy měření držet konzistentní podle kroků A-D.

## 7) Kdy navrhnout preset

Preset navrhovat až když platí vše:

1. Timing varianta je vybraná podle pravidla 2 ze 3 pozic.
2. Je potvrzený poměr sub/top (reference nebo +/-2 dB série).
3. Měření je bez limitace a s konzistentním gain staging.

Teprve potom řešit PEQ a finální preset.
