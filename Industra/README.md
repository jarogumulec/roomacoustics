# Industra

Akce: 2026-04-30, setup JBL 2x sub + 2x top.

## Pouzity system

- Sub: JBL PRX818XLF (2 ks)
- Top: JBL EON715 (2 ks)
- Zapojeni: sub -> out (HPF) -> top
- Mereni: t.bone MM-1 -> Focusrite 2i2 4th Gen -> REW

## Struktura

- `specs/` - originalni datasheety + textovy export
- `measurements/2026-04-30_jbl-mejdan/` - REW data (txt, png, mdat)
- `docs/` - analyza mistnosti, tuning plan a metodika mereni
- `presets/` - navrhy a verze DSP presetu
- `photos/` - fotky setupu

## Co je dulezite

- Jedine mereni v datech je `L+R` celeho systemu.
- Sweep byl bez timing reference, proto absolutni faze neni vhodna pro presne casove zarovnani.
- Pro dalsi iteraci je potreba merit sub a top zvlast.
