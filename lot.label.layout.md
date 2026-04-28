# Choose the sheet layout to print lot labels — `lot.label.layout`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `label_quantity` **(selection)** — Quantity to print ⚠️ obrigatório
  > If the UoM of a lot is not 'units', the lot will be considered as a unit and only one label will be printed for this lot.
  > Opções: `lots` (One per lot/SN), `units` (One per unit)
- `print_format` **(selection)** — Format ⚠️ obrigatório
  > Opções: `4x12` (4 x 12), `zpl` (ZPL Labels)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `move_line_ids` **(many2many)** — Move Line → `stock.move.line`
