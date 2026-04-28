# Rule — `ir.rule`

**Ordenação padrão:** `model_id DESC,id`

---

## Campos Obrigatórios

- `model_id` **(many2one)** — Model ⚠️ obrigatório → `ir.model`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `active` **(boolean)** — Active
  > If you uncheck the active field, it will disable the record rule without deleting it (if you delete a native record rule, it may be re-created when you reload the module).
- `domain_force` **(text)** — Domain
- `perm_read` **(boolean)** — Read
- `perm_write` **(boolean)** — Write
- `perm_create` **(boolean)** — Create
- `perm_unlink` **(boolean)** — Delete
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `global` **(boolean)** — Global 🔒 readonly
  > If no group is specified the rule is global and applied to everyone

## Relacionamentos

- `groups` **(many2many)** — Groups → `res.groups`
