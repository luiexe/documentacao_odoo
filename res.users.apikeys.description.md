# API Key Description — `res.users.apikeys.description`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Description ⚠️ obrigatório
- `duration` **(selection)** — Duration ⚠️ obrigatório
  > Opções: `1` (1 Day), `7` (1 Week), `30` (1 Month), `90` (3 Months), `180` (6 Months), `365` (1 Year), `0` (Persistent Key), `-1` (Custom Date)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `expiration_date` **(datetime)** — Expiration Date
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
