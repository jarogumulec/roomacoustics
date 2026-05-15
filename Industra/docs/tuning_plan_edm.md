# Tuning Plan EDM (Industra)

Tento dokument je postavený na datech z měření 2026-04-30 (`text_export/*.txt`).

## 1) Co říkají aktuální data a z čeho přesně vycházejí

Použité zdroje:

- `export_measurement_SPL_phase.txt` (SPL + fáze)
- `measurement.txt` (SPL + fáze, stejný měřicí běh)
- `rt60.txt` (decay/T30)
- `distortion.txt` (THD orientačně)

Klíčová čísla z těchto dat:

- Peak: **90.61 dB @ 39.71 Hz** (35-45 Hz)
- Minimum: **78.52 dB @ 77.16 Hz** (70-100 Hz)
- Průměr 70-90 Hz: **83.41 dB**
- Průměr 90-120 Hz: **86.95 dB**
- T30 průměr:
  - 50-125 Hz: **2.09 s**
  - 160-1000 Hz: **1.85 s**
  - 1250-10000 Hz: **1.08 s**

Interpretace:
- V 35-45 Hz je přebytek energie (boom/dunění).
- V 70-100 Hz je oslabení (slabší punch kopáku).
- Delší dozvuk v basech maskuje čitelnost rytmu.

## 2) Cíle presetu

- Omezit boom v 35-45 Hz.
- Zlepšit punch a čitelnost v 70-110 Hz.
- Nenechat výšky agresivní, ale zachovat detail.

## 3) Start preset v DSP (v1)

### Suby PRX818XLF

- LPF/crossover: 80 Hz, Linkwitz-Riley 24 dB/oct
- PEQ1: -4 dB @ 40 Hz, Q 1.0
- PEQ2: +2 dB @ 92 Hz, Q 0.8
- Polarity: normal + připravit A/B variantu `sub-invert`
- Delay: start 0.0 ms, ladit po 0.2 ms

Jak to měřit pro suby:

1. Vypnout topy, měřit `SUB_ONLY_LR`.
2. Pro kontrolu symetrie doplnit `SUB_LEFT` a `SUB_RIGHT`.
3. Teprve potom měřit `FULL_LR` (suby+topy).

### Topy EON715

- HPF: 80 Hz (nebo dle routing logiky přes sub out)
- PEQ1: +1.5 dB @ 4.5 kHz, Q 0.7 (jen pokud je slyšet útlum detailu)
- PEQ2: -1.5 dB @ 3.2 kHz, Q 1.0 (jen pokud je zvuk ostrý)
- Delay: dorovnat k subům podle měření, ne podle pocitu

## 4) Jak preset validovat (co zvlášť a co dohromady)

Krátká odpověď: **oboje**.

Povinné minimum:

1. `SUB_ONLY_LR` (jen suby)
2. `TOP_ONLY_LR` (jen topy)
3. `FULL_LR` (celý systém)

Doporučené rozšíření:

1. `SUB_LEFT`, `SUB_RIGHT`
2. `TOP_LEFT`, `TOP_RIGHT`

Pro každou DSP variantu (např. `v1-normal`, `v1-sub-invert`, `v1-delay+0.6ms`) měřit stejné mikrofonní body a porovnat:

- 35-45 Hz: má klesnout boom.
- 70-100 Hz: má narůst čitelnost punch.
- Decay/waterfall: má se zkrátit doznívání basu.
- Subjektivně: kick definice vs. „huhňání“.

## 5) Důležitá poznámka k fázi (jednoduše)

U měření bez timing reference není absolutní fáze spolehlivá pro finální nastavení delaye mezi subem a topem.

Co to znamená prakticky:

- Tvar fáze můžeš brát orientačně v rámci jednoho běhu.
- Nemůžeš jí ale věřit jako absolutnímu „časovému pravítku“ pro přesné zarovnání sub/top.
- Pro finální delay alignment je potřeba nové měření s timing reference (nebo velmi konzistentní gated postup se separátním měřením sub/top).

## 6) Measurement protocol next time (součást tuning plánu)

### Příprava

- Držet fixní gain staging a zapsat hodnoty.
- Použít stejný sweep level a stejné pozice mikrofonu.
- Vypnout vše, co není součást testované DSP varianty.

### Série měření

- Povinně: `SUB_ONLY_LR`, `TOP_ONLY_LR`, `FULL_LR`
- Ideálně navíc: `SUB_LEFT`, `SUB_RIGHT`, `TOP_LEFT`, `TOP_RIGHT`

### Mikrofonní pozice

- Pozice 1: sweet spot (výška uší)
- Pozice 2 a 3: cca +/- 1 m od sweet spotu
- O presetu rozhodovat podle průměru více pozic

### Co exportovat

- SPL + Phase (1/12 nebo 1/24 smoothing)
- Impulse response
- RT60/T30
- Decay + Waterfall
- Distortion (orientačně)
- Původní `.mdat`

### Pořadí ladění

1. Crossover + polarity (sub/top odděleně + full)
2. Delay sub vs top po malých krocích
3. PEQ pro tonal balance
4. Reálná hlasitá ověřovací zkouška
