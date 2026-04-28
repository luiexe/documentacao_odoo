# Language Import — `base.language.import`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Language Name ⚠️ obrigatório
- `code` **(char)** — ISO Code ⚠️ obrigatório
  > ISO Language and Country code, e.g. en_US
- `data` **(binary)** — File ⚠️ obrigatório
- `filename` **(char)** — File Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `overwrite` **(boolean)** — Overwrite Existing Terms
  > If you enable this option, existing translations (including custom ones) will be overwritten and replaced by those in this file
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
