# Create new or use existing Customer on new Quotation — `crm.quotation.partner`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `action` **(selection)** — Quotation Customer ⚠️ obrigatório
  > Opções: `create` (Create a new customer), `exist` (Link to an existing customer), `nothing` (Do not link to a customer)
- `lead_id` **(many2one)** — Associated Lead ⚠️ obrigatório → `crm.lead`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `partner_id` **(many2one)** — Customer → `res.partner`
