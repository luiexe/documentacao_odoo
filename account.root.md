# Account codes first 2 digits — `account.root`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly

## Relacionamentos

- `parent_id` **(many2one)** — Parent 🔒 readonly → `account.root`

## Campos Calculados (readonly)

- `name` **(char)** — Name 🔒 readonly
