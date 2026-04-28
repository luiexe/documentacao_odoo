# Account Move Send Batch Wizard — `account.move.send.batch.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `move_ids` **(many2many)** — Move ⚠️ obrigatório → `account.move`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `summary_data` **(json)** — Summary Data 🔒 readonly
- `alerts` **(json)** — Alerts 🔒 readonly
- `send_by_post_stamps` **(integer)** — Send By Post Stamps 🔒 readonly
