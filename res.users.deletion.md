# Users Deletion Request — `res.users.deletion`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `state` **(selection)** — State ⚠️ obrigatório
  > Opções: `todo` (To Do), `done` (Done), `fail` (Failed)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `user_id_int` **(integer)** — User Id 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_id` **(many2one)** — User → `res.users`
