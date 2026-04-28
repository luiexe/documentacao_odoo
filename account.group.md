# Account Group — `account.group`

**Ordenação padrão:** `code_prefix_start`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `code_prefix_start` **(char)** — Code Prefix Start
- `code_prefix_end` **(char)** — Code Prefix End
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `parent_id` **(many2one)** — Parent 🔒 readonly → `account.group`
