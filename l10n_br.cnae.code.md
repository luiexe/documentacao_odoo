# CNAE Code — `l10n_br.cnae.code`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `code` **(char)** — Code ⚠️ obrigatório
- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `sanitized_code` **(char)** — Sanitized Code 🔒 readonly
  > Technical field that contains the code without special characters, as expected by the Avalara API.
