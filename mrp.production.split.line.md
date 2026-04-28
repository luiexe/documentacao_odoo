# Split Production Detail — `mrp.production.split.line`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `mrp_production_split_id` **(many2one)** — Split Production ⚠️ obrigatório → `mrp.production.split`
- `quantity` **(float)** — Quantity To Produce ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `date` **(datetime)** — Schedule Date
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_id` **(many2one)** — Responsible → `res.users`
