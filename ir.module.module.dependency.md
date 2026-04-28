# Module dependency — `ir.module.module.dependency`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `auto_install_required` **(boolean)** — Auto Install Required
  > Whether this dependency blocks automatic installation of the dependent

## Relacionamentos

- `module_id` **(many2one)** — Module → `ir.module.module`
- `depend_id` **(many2one)** — Dependency 🔒 readonly → `ir.module.module`

## Campos Calculados (readonly)

- `state` **(selection)** — Status 🔒 readonly
  > Opções: `uninstallable` (Uninstallable), `uninstalled` (Not Installed), `installed` (Installed), `to upgrade` (To be upgraded), `to remove` (To be removed), `to install` (To be installed), `unknown` (Unknown)
