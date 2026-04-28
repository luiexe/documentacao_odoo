# Html Editor Converter Test — `html_editor.converter.test`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `char` **(char)** — Char
- `integer` **(integer)** — Integer
- `float` **(float)** — Float
- `numeric` **(float)** — Numeric
- `binary` **(binary)** — Binary
- `date` **(date)** — Date
- `datetime` **(datetime)** — Datetime
- `selection_str` **(selection)** — Lorsqu'un pancake prend l'avion à destination de Toronto et qu'il fait une escale technique à St Claude, on dit:
  > Opções: `A` (Qu'il n'est pas arrivé à Toronto), `B` (Qu'il était supposé arriver à Toronto), `C` (Qu'est-ce qu'il fout ce maudit pancake, tabernacle ?), `D` (La réponse D)
- `html` **(html)** — Html
- `text` **(text)** — Text
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `many2one` **(many2one)** — Many2One → `html_editor.converter.test.sub`
