# Merge Partner Line — `base.partner.merge.line`

**Ordenação padrão:** `min_id asc`

---

## Campos Obrigatórios

- `aggr_ids` **(char)** — Ids ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `min_id` **(integer)** — MinID
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `wizard_id` **(many2one)** — Wizard → `base.partner.merge.automatic.wizard`
