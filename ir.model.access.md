# Model Access — `ir.model.access`

**Ordenação padrão:** `model_id,group_id,name,id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `model_id` **(many2one)** — Model ⚠️ obrigatório → `ir.model`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
  > If you uncheck the active field, it will disable the ACL without deleting it (if you delete a native ACL, it will be re-created when you reload the module).
- `perm_read` **(boolean)** — Read Access
- `perm_write` **(boolean)** — Write Access
- `perm_create` **(boolean)** — Create Access
- `perm_unlink` **(boolean)** — Delete Access
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `group_id` **(many2one)** — Group → `res.groups`
