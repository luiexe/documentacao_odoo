# Module exclusion — `ir.module.module.exclusion`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `module_id` **(many2one)** — Module → `ir.module.module`
- `exclusion_id` **(many2one)** — Exclusion Module 🔒 readonly → `ir.module.module`

## Campos Calculados (readonly)

- `state` **(selection)** — Status 🔒 readonly
  > Opções: `uninstallable` (Uninstallable), `uninstalled` (Not Installed), `installed` (Installed), `to upgrade` (To be upgraded), `to remove` (To be removed), `to install` (To be installed), `unknown` (Unknown)
