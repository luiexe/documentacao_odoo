# Update the probabilities — `crm.lead.pls.update`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `pls_start_date` **(date)** — Pls Start Date ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `pls_fields` **(many2many)** — Pls Fields → `crm.lead.scoring.frequency.field`
