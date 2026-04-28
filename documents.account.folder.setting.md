# Journal and Folder settings — `documents.account.folder.setting`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `journal_id` **(many2one)** — Journal ⚠️ obrigatório → `account.journal`
- `folder_id` **(many2one)** — Folder ⚠️ obrigatório → `documents.document`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_account_folder_id` **(many2one)** — Accounting Folder 🔒 readonly → `documents.document`
- `tag_ids` **(many2many)** — Tags → `documents.tag`
