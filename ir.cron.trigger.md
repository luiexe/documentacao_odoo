# Triggered actions — `ir.cron.trigger`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `cron_id` **(many2one)** — Cron ⚠️ obrigatório → `ir.cron`
- `call_at` **(datetime)** — Call At ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
