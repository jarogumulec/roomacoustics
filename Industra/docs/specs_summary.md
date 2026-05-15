# Specifikace repro (jen důležité)

Oficiální zdroje datasheetů:

- JBL EON715 Spec Sheet: https://jblpro.com/el/site_elements/eon715-spec-sheet
- JBL PRX818XLF Spec Sheet (PDF): https://www.jbl.com/on/demandware.static/-/Sites-masterCatalog_Harman/default/dw99912afa/pdfs/JBL_PRX818XLF_SpecSheet.pdf

## JBL PRX818XLF (sub)

- Max SPL: 134 dB peak
- Frekvenční rozsah (-10 dB): 30-103 Hz
- Frekvenční odezva (+/-3 dB): 35-87 Hz
- Vestavěný LPF/crossover: 80 Hz, Linkwitz-Riley 24 dB/oct
- DSP: limiter, EQ, polarity

Praktický dopad pro ladění:
- Sub je nejsilnější do cca 80-90 Hz, proto dává smysl dělení kolem 80 Hz jako výchozí bod.
- Pod cca 35 Hz je potřeba opatrnost, aby se zbytečně nebudilo room mode pásmo.

## JBL EON715 (top)

- Max SPL: 128 dB
- Frekvenční rozsah (-10 dB): 45 Hz-20 kHz
- Frekvenční rozsah (-3 dB): 55 Hz-20 kHz
- Pokrytí: 90° x 60°
- DSP: PEQ, delay (až 100 ms), ochrany

Praktický dopad pro ladění:
- Top je vhodné držet nad crossoverem (typicky 80 Hz+), aby nehrál zbytečně hluboký bas.
- Topy se používají hlavně pro čitelnost pásma nad kickem a pro atak/definici.

## Limity, které je dobré respektovat

- Čísla z datasheetu neřeší akustiku místnosti; finální výsledek vždy určí měření v prostoru.
- Největší problém v Industře není výkon beden, ale průběh místnosti v basech a dlouhý dozvuk.
