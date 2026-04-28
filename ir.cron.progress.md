# Progress of Scheduled Actions — `ir.cron.progress`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `cron_id` **(many2one)** — Cron ⚠️ obrigatório → `ir.cron`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `remaining` **(integer)** — Remaining
- `done` **(integer)** — Done
- `deactivate` **(boolean)** — Deactivate
- `timed_out_counter` **(integer)** — Timed Out Counter
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
