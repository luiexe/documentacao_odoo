# Document Access Tracking — `documents.access.tracking`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `changes` **(json)** — Changes need to be tracked ⚠️ obrigatório
- `documents` **(json)** — Impacted Document Ids ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly

## Relacionamentos

- `user_id` **(many2one)** — User → `res.users`
