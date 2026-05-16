# REW Naming And Exports

Tento soubor je obecná pomocná poznámka pro repo, ne dokument konkrétní místnosti.

## Cíl

Držet jednotné názvosloví a minimální export disciplínu napříč prostory, i když raw názvy z REW zůstanou historicky smíšené.

## Obecný alias formát

Používat tvar:

- `PLACE_position_channel_date`

Příklady:

- `HOME_u_TV_L_2026-05-16`
- `HOME_gauc_LR_2026-05-16`
- `INDUSTRA_M1_FULL_LR_2026-04-30`

## Home mapování na současné exporty

- `HOME_u_TV_L_2026-05-16` -> `L uTV_doma_loopback May 16`
- `HOME_u_TV_R_2026-05-16` -> `R uTV_doma_loopback May 16`
- `HOME_u_TV_LR_2026-05-16` -> `L+R uTV_doma_loopback May 16`
- `HOME_gauc_L_2026-05-16` -> `L sedacka_doma_loopback`
- `HOME_gauc_R_2026-05-16` -> `R sedacka_doma_loopback May 16`
- `HOME_gauc_LR_2026-05-16` -> `L+R sedacka_doma_loopback May 16`
- `HOME_stred_obyvaku_LR_2026-05-16` -> `L+R stred_obyvaku_doma_loopback May 16`

## Doporučený export checklist pro každou session

Vždy uložit:

1. `.mdat`
2. `SPL + Phase` text export
3. `Impulse response` text export
4. `RT60` text export

Doporučené obrázky:

1. `All SPL` overlay
2. `Impulse / ETC`
3. `Waterfall` nebo `Decay`
4. `RT60` PNG pro klíčové kanály / pozice

## Minimální sada měření pro domácí A/B variantu

1. `L u TV`
2. `R u TV`
3. `L+R u TV`
4. `L+R gauč`

Rozšířená sada:

1. `L gauč`
2. `R gauč`
3. `L+R střed obýváku`

## Pravidlo pro další práci

Staré soubory není nutné hromadně přejmenovávat. Stačí:

- držet aliasy v dokumentaci
- nové session pojmenovávat už jednotně
- v reportech vždy uvést mapování mezi aliasem a reálným REW názvem