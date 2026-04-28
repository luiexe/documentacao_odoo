# Account merge wizard line — `account.merge.wizard.line`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `wizard_id` **(many2one)** — Wizard ⚠️ obrigatório → `account.merge.wizard`
- `display_type` **(selection)** — Display Type ⚠️ obrigatório
  > Opções: `line_section` (Section), `line_subsection` (Subsection), `account` (Account)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `grouping_key` **(char)** — Grouping Key
- `sequence` **(integer)** — Sequence
- `is_selected` **(boolean)** — Is Selected
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `account_id` **(many2one)** — Account 🔒 readonly → `account.account`
- `company_ids` **(many2many)** — Companies 🔒 readonly → `res.company`

## Campos Calculados (readonly)

- `info` **(char)** — Info 🔒 readonly
  > Contains either the section name or error message, depending on the line type.
- `account_has_hashed_entries` **(boolean)** — Account Has Hashed Entries 🔒 readonly
