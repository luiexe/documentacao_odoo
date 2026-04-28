# Fields that can be used for predictive lead scoring computation — `crm.lead.scoring.frequency.field`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `field_id` **(many2one)** — Field ⚠️ obrigatório → `ir.model.fields`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `color` **(integer)** — Color
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `name` **(char)** — Field Label 🔒 readonly
