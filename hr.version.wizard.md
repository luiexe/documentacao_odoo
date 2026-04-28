# Contract Template Wizard — `hr.version.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `contract_template_id` **(many2one)** — Contract Template ⚠️ obrigatório → `hr.version`
  > Select a contract template to auto-fill the contract form with predefined values. You can still edit the fields as needed after applying the template.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
