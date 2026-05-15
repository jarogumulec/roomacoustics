# Aktuální stav 2026-04-30 (Industra, JBL)

## 1) Z jakých dat vychází tento report

Zdroj je pouze z měřicí složky:

- `measurements/2026-04-30_jbl-mejdan/text_export/`
- `measurements/2026-04-30_jbl-mejdan/graphs_export/`

Měření: `L+R industra_mejdan Apr 30` (2x EON715 + 2x PRX818XLF), sweep bez timing reference.

## 2) Aktuální stav systému podle dat

- Výrazný peak v subbasu: **90.61 dB @ 39.71 Hz** (pásmo 35-45 Hz).
- Oslabení v oblasti punch/kick: **78.52 dB @ 77.16 Hz** (v pásmu 70-100 Hz).
- Průměr pásma 70-90 Hz: **83.41 dB**.
- Průměr pásma 90-120 Hz: **86.95 dB**.
- Rozdíl průměrů 90-120 vs 70-90 Hz: přibližně **+3.54 dB**.
- T30 (RT60 proxy) je dlouhé hlavně dole:
  - 50-125 Hz: **2.09 s**
  - 160-1000 Hz: **1.85 s**
  - 1250-10000 Hz: **1.08 s**

Interpretace: prostor stále přidává „dunění“ pod 50 Hz a současně maskuje čitelnost kopáku v 70-100 Hz.

## 2.1 Timing a fáze: co už teď víme

- Propad kolem 70-80 Hz může být kombinace room módu a sub/top interference.
- Vzhledem k tomu, že měření je bez timing reference, nelze potvrdit přesný časový offset sub vs top.
- Timing je ale pravděpodobně významný faktor: pásmo kolem crossoveru (cca 70-100 Hz) je přesně tam, kde se nejčastěji projeví špatné časové zarovnání.

Praktický závěr pro tento stav:
- Timing je potřeba brát jako klíčovou hypotézu, ale definitivně ho ověřit až v příští sérii měření s referencí.

## 2.2 Co z postavení a místnosti pravděpodobně kazí výsledek

- Rozměry haly (14.8 x 12.2 x 11.6 m) podporují silné nízkofrekvenční módy; to odpovídá peaku 35-45 Hz i slabší čitelnosti kolem 70-80 Hz.
- Suby jsou o 0.5 m před topy, což vytváří přirozený časový offset mezi pásmy ještě před DSP korekcí.
- Výškový rozdíl center top/sub je 1.45 m, takže v crossover pásmu vzniká výrazná geometrická interference podle místa poslechu.
- Měření v 0.8 m výšce a relativně blízko PA (cca 2.5 m) zvýrazňuje lokální interferenci; pro rozhodnutí je potřeba více pozic a i výška blíže uším publika.
- Natočení cca 45° a velký otevřený prostor mohou dávat asymetrické boční odrazy a nerovnoměrné pokrytí.

Praktický dopad:
- Problém není jen EQ, ale kombinace room mode + geometrie + timing.
- Samotný PEQ bez ověřeného postavení a timingu bude nestabilní mezi body v prostoru.

## 3) Grafy s komentářem

### SPL + fáze

![SPL a fáze](../measurements/2026-04-30_jbl-mejdan/graphs_export/01_SPL.png)

Komentář:
- SPL potvrzuje dominantní nárůst kolem 40 Hz.
- V okolí 75-80 Hz je propad, který je kritický pro punch.
- Fáze je použitelná jen orientačně (měření je bez timing reference).

### Distortion

![Distortion](../measurements/2026-04-30_jbl-mejdan/graphs_export/02_distortion.png)

Komentář:
- Pod 30 Hz je THD velmi vysoké, ale to je mimo hlavní hudební pracovní pásmo setupu.
- V pásmu cca 35-140 Hz je THD převážně nízké až střední, takže hlavní problém je spíš room response než nelinearita měničů.

### Impulse

![Impulse](../measurements/2026-04-30_jbl-mejdan/graphs_export/03_impulse.png)

Komentář:
- Impuls potvrzuje, že systém i místnost mají delší dozvukovou složku.
- Bez timing reference nelze z impulsu bezpečně odvodit finální absolutní delay sub vs top.

### Decay

![Decay](../measurements/2026-04-30_jbl-mejdan/graphs_export/04_decay.png)

Komentář:
- Delší decay v nízkých pásmech odpovídá subjektivnímu „huhňání“.
- Potvrzuje nutnost opatrných zásahů v 35-50 Hz a lepšího odděleného měření sub/top.

### Waterfall

![Waterfall](../measurements/2026-04-30_jbl-mejdan/graphs_export/05_waterfall.png)

Komentář:
- Waterfall ukazuje dlouhé doznívání v basech.
- Při ladění je důležité sledovat nejen SPL, ale i zkrácení doznívání v problémových pásmech.

## 4) Co příště jinak (jen outline)

- Měřit povinně odděleně: `SUB_ONLY_LR`, `TOP_ONLY_LR`, `FULL_LR`.
- Ideálně doplnit `SUB_LEFT`, `SUB_RIGHT`, `TOP_LEFT`, `TOP_RIGHT`.
- Použít timing reference (nebo konzistentní gated postup) pro smysluplné fázové/delay rozhodnutí.
- Udržet stejné gain staging a stejné pozice mikrofonu pro A/B.
- Rozhodovat podle průměru více pozic, ne podle jedné křivky.

### 4.1 Doporučení pro jiné postavení při příštím měření

Testovat minimálně dvě varianty postavení ještě před finálním timing laděním:

- Varianta A (stávající): suby předsazené o 0.5 m před topy.
- Varianta B (snazší alignment): topy níž a zarovnané v hloubce se suby (co nejmenší předozadní offset center).

Pro každou variantu udělat krátké porovnání:

1. `SUB_ONLY_LR`
2. `TOP_ONLY_LR`
3. `FULL_LR_base` (normal, 0.0 ms)

Pak pokračovat s timing maticí jen u lepší varianty postavení.

Poznámka k tvému návrhu:
- Snížit topy a zarovnat je se suby je validní a často prakticky jednodušší než řešit velký geometrický offset jen delayem.