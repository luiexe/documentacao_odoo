# Storage — `ir.attachment.report`

**Ordenação padrão:** `size desc`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `res_model` **(char)** — Model 🔒 readonly
- `res_id` **(many2one_reference)** — Record 🔒 readonly
- `size` **(integer)** — Total Size

## Campos Calculados (readonly)

- `name` **(char)** — Resource Name 🔒 readonly
