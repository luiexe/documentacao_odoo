# History for Loyalty cards and Ewallets — `loyalty.history`

**Ordenação padrão:** `id desc`

---

## Campos Obrigatórios

- `card_id` **(many2one)** — Card ⚠️ obrigatório → `loyalty.card`
- `description` **(text)** — Description ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `issued` **(float)** — Issued
- `used` **(float)** — Used
- `order_model` **(char)** — Order Model 🔒 readonly
- `order_id` **(many2one_reference)** — Order 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
