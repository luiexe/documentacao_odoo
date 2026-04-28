# Resource Time Off Detail — `resource.calendar.leaves`

**Ordenação padrão:** `date_from`

---

## Campos Obrigatórios

- `date_from` **(datetime)** — Start Date ⚠️ obrigatório
- `date_to` **(datetime)** — End Date ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Reason
- `time_type` **(selection)** — Time Type
  > Whether this should be computed as a time off or as work time (eg: formation)
  > Opções: `leave` (Time Off), `other` (Other)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company 🔒 readonly → `res.company`
- `calendar_id` **(many2one)** — Working Hours → `resource.calendar`
- `resource_id` **(many2one)** — Resource → `resource.resource`
  > If empty, this is a generic time off for the company. If a resource is set, the time off is only for this resource
