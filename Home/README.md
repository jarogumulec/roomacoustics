# Home - Reprosoustava BW 685

## Setup

- **Reprosoustava**: Bowers & Wilkins 685
- **Typ**: 2-way bass reflex compact speaker
- **Základní footprint bedny**: 198 × 331 mm
- **Měniče**: 165 mm Kevlar cone + 25 mm aluminium dome
- **Citlivost / impedance**: 88 dB, 8 ohm
- **Měřicí software**: REW
- **Pozice v dokumentaci**:
	- `u TV` = bližší pozice u televize, kde se hrají hry s gamepadem
	- `gauč` = hlavní vzdálenější poslechová pozice
	- `střed obýváku` = lehká orientační `L+R` reference

Aktuální dokumentace:

- `docs/room_and_system.md` - prostor, geometrie, loopback metoda
- `docs/aktualni_stav_2026-05-16.md` - detailní shrnutí měření a interpretace
- `docs/doporuceni_2026-05-16.md` - konkrétní doporučení dalších kroků
- `../guides/rew_naming_and_exports.md` - obecná helper poznámka pro naming a exporty
- `../home.html` - shareable HTML report v rootu repa

## Struktura

- `specs/` - datasheety a technické podklady aparátu
- `measurements/` - exporty z REW (`.mdat`, `txt`, PNG)
- `docs/` - popis prostoru, setupu a doporučená interpretace
- `presets/` - případné budoucí verze korekcí
- `photos/` - dokumentační fotky setupu

## Loopback nastavení

Použitý postup:

1. V REW: `Edit` > `Preferences` > `Soundcard`
2. měřicí mikrofon na `Input 1`
3. loopback reference z `tape out` zesilovače na `Input 2`
4. při `L` měření použít `SPEAKER L`, při `R` měření `SPEAKER R`
5. sweep level držet konzistentně, aktuálně `-12.2 dBFS`

Poznámka:

- `L+R` měření jsou pro domácí stereo dokumentaci použitelná
- pro detailní diagnostiku je pořád důležitější vyhodnocovat `L` a `R` zvlášť

## Aktuální stav měření

Aktuálně jsou k dispozici exporty pro:

- `u TV`: `L`, `R`, `L+R`
- `gauč`: `L`, `R`, `L+R`
- `střed obýváku`: `L+R`

Exportované typy dat:

- `measurements/SPL Phase phase/`
- `measurements/impulse responses/`
- `measurements/RT60/`
- waterfall PNG
- SPL PNG overlaye
- RT60 PNG

Praktický závěr:

- hlavní problém není nedostatek basu, ale jeho nerovnoměrnost a delší decay v některých pozicích
- kritická pozice je zatím `gauč`
- hlavní referenční bod pro další změny dává smysl držet `u TV`
- `střed obýváku` je zatím jen orientační `L+R` reference, ne plná diagnostická pozice

## Další krok

Nejdřív řešit fyzické postavení repro a poslechového místa, teprve potom případné EQ.
