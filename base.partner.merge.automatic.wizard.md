# Merge Partner Wizard — `base.partner.merge.automatic.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `state` **(selection)** — State ⚠️ obrigatório 🔒 readonly
  > Opções: `option` (Option), `selection` (Selection), `finished` (Finished)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `group_by_email` **(boolean)** — Email
- `group_by_name` **(boolean)** — Name
- `group_by_is_company` **(boolean)** — Is Company
- `group_by_vat` **(boolean)** — VAT
- `group_by_parent_id` **(boolean)** — Parent Company
- `number_group` **(integer)** — Group of Contacts 🔒 readonly
- `exclude_contact` **(boolean)** — A user associated to the contact
- `exclude_journal_item` **(boolean)** — Journal Items associated to the contact
- `maximum_group` **(integer)** — Maximum of Group of Contacts
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `current_line_id` **(many2one)** — Current Line → `base.partner.merge.line`
- `line_ids` **(one2many)** — Lines → `base.partner.merge.line`
- `partner_ids` **(many2many)** — Contacts → `res.partner`
- `dst_partner_id` **(many2one)** — Destination Contact → `res.partner`
