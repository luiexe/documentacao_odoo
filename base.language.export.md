# Language Export — `base.language.export`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `lang` **(selection)** — Language ⚠️ obrigatório
  > Opções: `__new__` (New Language (Empty translation template)), `en_US` (English (US)), `pt_BR` (Portuguese (BR) / Português (BR))
- `format` **(selection)** — File Format ⚠️ obrigatório
  > Opções: `csv` (CSV File), `po` (PO File), `tgz` (TGZ Archive)
- `export_type` **(selection)** — Export Type ⚠️ obrigatório
  > Opções: `module` (Module), `model` (Model)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — File Name 🔒 readonly
- `domain` **(char)** — Model Domain
- `data` **(binary)** — File 🔒 readonly
- `state` **(selection)** — State
  > Opções: `choose` (choose), `get` (get)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `modules` **(many2many)** — Apps To Export → `ir.module.module`
- `model_id` **(many2one)** — Model to Export → `ir.model`

## Campos Calculados (readonly)

- `model_name` **(char)** — Model Name 🔒 readonly
