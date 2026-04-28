# Link Tracker Code — `link.tracker.code`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `code` **(char)** — Short URL Code ⚠️ obrigatório
- `link_id` **(many2one)** — Link ⚠️ obrigatório → `link.tracker`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
