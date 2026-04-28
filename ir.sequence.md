# Sequence — `ir.sequence`

**Ordenação padrão:** `name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `implementation` **(selection)** — Implementation ⚠️ obrigatório
  > While assigning a sequence number to a record, the 'no gap' sequence implementation ensures that each previous sequence number has been assigned already. While this sequence implementation will not skip any sequence number upon assignment, there can still be gaps in the sequence if records are deleted. The 'no gap' implementation is slower than the standard one.
  > Opções: `standard` (Standard), `no_gap` (No gap)
- `number_next` **(integer)** — Next Number ⚠️ obrigatório
  > Next number of this sequence
- `number_increment` **(integer)** — Step ⚠️ obrigatório
  > The next number of the sequence will be incremented by this number
- `padding` **(integer)** — Sequence Size ⚠️ obrigatório
  > Odoo will automatically adds some '0' on the left of the 'Next Number' to get the required padding size.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `code` **(char)** — Sequence Code
- `active` **(boolean)** — Active
- `prefix` **(char)** — Prefix
  > Prefix value of the record for the sequence
- `suffix` **(char)** — Suffix
  > Suffix value of the record for the sequence
- `number_next_actual` **(integer)** — Actual Next Number
  > Next number that will be used. This number can be incremented frequently so the displayed value might already be obsolete
- `use_date_range` **(boolean)** — Use subsequences per date_range
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `company_id` **(many2one)** — Company → `res.company`
- `date_range_ids` **(one2many)** — Subsequences → `ir.sequence.date_range`
