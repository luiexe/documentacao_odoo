# Logging — `ir.logging`

**Ordenação padrão:** `id DESC`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `type` **(selection)** — Type ⚠️ obrigatório
  > Opções: `client` (Client), `server` (Server)
- `message` **(text)** — Message ⚠️ obrigatório
- `path` **(char)** — Path ⚠️ obrigatório
- `func` **(char)** — Function ⚠️ obrigatório
- `line` **(char)** — Line ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `dbname` **(char)** — Database Name
- `level` **(char)** — Level
