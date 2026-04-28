# Cryptographic Keys — `certificate.key`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `content` **(binary)** — Key file ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `password` **(char)** — Private key password
- `pem_key` **(binary)** — Key bytes in PEM format 🔒 readonly
- `public` **(boolean)** — Public/Private key 🔒 readonly
- `loading_error` **(text)** — Loading error 🔒 readonly
- `active` **(boolean)** — Active
  > Set active to false to archive the key.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
