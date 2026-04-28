# Remake the sequence of Journal Entries. — `account.resequence.wizard`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `first_name` **(char)** — First New Sequence ⚠️ obrigatório
- `ordering` **(selection)** — Ordering ⚠️ obrigatório
  > Opções: `keep` (Keep current order), `date` (Reorder by accounting date)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `first_date` **(date)** — First Date
  > Date (inclusive) from which the numbers are resequenced.
- `end_date` **(date)** — End Date
  > Date (inclusive) to which the numbers are resequenced. If not set, all Journal Entries up to the end of the period are resequenced.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `move_ids` **(many2many)** — Move → `account.move`

## Campos Calculados (readonly)

- `sequence_number_reset` **(char)** — Sequence Number Reset 🔒 readonly
- `new_values` **(text)** — New Values 🔒 readonly
- `preview_moves` **(text)** — Preview Moves 🔒 readonly
