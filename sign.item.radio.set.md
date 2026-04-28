# Radio button set for keeping radio button items together — `sign.item.radio.set`

**Ordenação padrão:** `id`

---

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `radio_items` **(one2many)** — Radio Items → `sign.item`

## Campos Calculados (readonly)

- `num_options` **(integer)** — Number of Radio Button options 🔒 readonly
