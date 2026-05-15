# roomacoustics

Repo pro systematicke ukladani mereni a ladeni PA v ruznych prostorech.

## Struktura

Kazdy prostor ma vlastni slozku se stejnou interni strukturou:

- `specs/` - datasheety a technicke podklady aparatu
- `measurements/` - exporty z REW (`.mdat`, `txt`, grafy)
- `docs/` - popis prostoru, setupu a doporucena ladeni
- `presets/` - verze presetu (DSP EQ, crossover, delay, polarita)
- `photos/` - dokumentacni fotky setupu

Aktualne:

- `Industra/` - JBL EON715 + PRX818XLF, mereni z 2026-04-30

## Python analyza (uv)

Projekt je pripraveny pro `uv` + `pyproject.toml`.

Zakladni priklady:

```bash
uv sync
uv add numpy pandas matplotlib scipy
uv run python -m pip list
```

Doporuceni:

- Drzet zavislosti minimalni.
- Vsechny analyzy smerovat do samostatnych skriptu/notebooku pod konkretnim prostorem.
