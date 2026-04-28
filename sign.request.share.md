# Sign request share wizard — `sign.request.share`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `template_id` **(many2one)** — Template ⚠️ obrigatório → `sign.template`
- `is_shared` **(boolean)** — Is Shared ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `validity` **(date)** — Valid Until
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `sign_request_id` **(many2one)** — Sign Request → `sign.request`

## Campos Calculados (readonly)

- `share_link` **(char)** — Share Link 🔒 readonly
