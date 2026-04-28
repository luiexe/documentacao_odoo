# Merge Mass Mailing List — `mailing.list.merge`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `merge_options` **(selection)** — Merge Option ⚠️ obrigatório
  > Opções: `new` (Merge into a new mailing list), `existing` (Merge into an existing mailing list)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `new_list_name` **(char)** — New Mailing List Name
- `archive_src_lists` **(boolean)** — Archive source mailing lists
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `src_list_ids` **(many2many)** — Mailing Lists → `mailing.list`
- `dest_list_id` **(many2one)** — Destination Mailing List → `mailing.list`
