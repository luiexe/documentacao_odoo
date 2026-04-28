# Reset View Architecture Wizard — `reset.view.arch.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `reset_mode` **(selection)** — Reset Mode ⚠️ obrigatório
  > Opções: `soft` (Restore previous version (soft reset).), `hard` (Reset to file version (hard reset).), `other_view` (Reset to another view.)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `view_id` **(many2one)** — View → `ir.ui.view`
- `compare_view_id` **(many2one)** — Compare To View → `ir.ui.view`

## Campos Calculados (readonly)

- `view_name` **(char)** — View Name 🔒 readonly
- `has_diff` **(boolean)** — Has Diff 🔒 readonly
- `arch_diff` **(html)** — Architecture Diff 🔒 readonly
- `arch_to_compare` **(text)** — Arch To Compare To 🔒 readonly
