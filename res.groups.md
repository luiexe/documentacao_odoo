# Access Groups — `res.groups`

**Ordenação padrão:** `privilege_id, sequence, name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `comment` **(text)** — Comment
- `share` **(boolean)** — Share Group
  > Group created to set access rights for sharing data with some users.
- `api_key_duration` **(float)** — API Keys maximum duration days
  > Determines the maximum duration of an api key created by a user belonging to this group.
- `sequence` **(integer)** — Sequence
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_ids` **(many2many)** — User → `res.users`
  > Users explicitly in this group
- `all_user_ids` **(many2many)** — Users and implied users → `res.users`
- `model_access` **(one2many)** — Access Controls → `ir.model.access`
- `rule_groups` **(many2many)** — Rules → `ir.rule`
- `menu_access` **(many2many)** — Access Menu → `ir.ui.menu`
- `view_access` **(many2many)** — Views → `ir.ui.view`
- `privilege_id` **(many2one)** — Privilege → `res.groups.privilege`
- `implied_ids` **(many2many)** — Implied Groups → `res.groups`
  > Users of this group are also implicitly part of those groups
- `all_implied_ids` **(many2many)** — Transitively Implied Groups 🔒 readonly → `res.groups`
  > The group itself with all its implied groups.
- `implied_by_ids` **(many2many)** — Implying Groups → `res.groups`
  > Users in those groups are implicitly part of this group.
- `all_implied_by_ids` **(many2many)** — Transitively Implying Groups 🔒 readonly → `res.groups`
- `disjoint_ids` **(many2many)** — Disjoint Groups 🔒 readonly → `res.groups`
  > A user may not belong to this group and one of those.  For instance, users may not be portal users and internal users.

## Campos Calculados (readonly)

- `all_users_count` **(integer)** — # Users 🔒 readonly
  > Number of users having this group (implicitly or explicitly)
- `full_name` **(char)** — Group Name 🔒 readonly
- `view_group_hierarchy` **(json)** — Technical field for default group setting 🔒 readonly
