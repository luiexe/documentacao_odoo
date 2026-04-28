# Message subtypes — `mail.message.subtype`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Message Type ⚠️ obrigatório
  > Message subtype gives a more precise type on the message, especially for system notifications. For example, it can be a notification related to a new record (New), or to a stage change in a process (Stage change). Message subtypes allow to precisely tune the notifications the user want to receive on its wall.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `description` **(text)** — Description
  > Description that will be added in the message posted for this subtype. If void, the name will be added instead.
- `internal` **(boolean)** — Internal Only
  > Messages with internal subtypes will be visible only by employees, aka members of base_user group
- `relation_field` **(char)** — Relation field
  > Field used to link the related model to the subtype model when using automatic subscription on a related document. The field is used to compute getattr(related_document.relation_field).
- `res_model` **(char)** — Model
  > Model the subtype applies to. If False, this subtype applies to all models.
- `default` **(boolean)** — Default
  > Activated by default when subscribing.
- `sequence` **(integer)** — Sequence
  > Used to order subtypes.
- `hidden` **(boolean)** — Hidden
  > Hide the subtype in the follower options
- `track_recipients` **(boolean)** — Track Recipients
  > Whether to display all the recipients or only the important ones.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `parent_id` **(many2one)** — Parent → `mail.message.subtype`
  > Parent subtype, used for automatic subscription. This field is not correctly named. For example on a project, the parent_id of project subtypes refers to task-related subtypes.
