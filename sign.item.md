# Fields to be sign on Document — `sign.item`

**Ordenação padrão:** `page asc, posY asc, posX asc`

---

## Campos Obrigatórios

- `document_id` **(many2one)** — Document Template ⚠️ obrigatório → `sign.document`
- `type_id` **(many2one)** — Type ⚠️ obrigatório → `sign.item.type`
- `page` **(integer)** — Document Page ⚠️ obrigatório
- `posX` **(float)** — Position X ⚠️ obrigatório
- `posY` **(float)** — Position Y ⚠️ obrigatório
- `width` **(float)** — Width ⚠️ obrigatório
- `height` **(float)** — Height ⚠️ obrigatório
- `alignment` **(char)** — Alignment ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `required` **(boolean)** — Required
- `name` **(char)** — Field Name
- `constant` **(boolean)** — Read-only
- `transaction_id` **(integer)** — Transaction
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `template_id` **(many2one)** — Template 🔒 readonly → `sign.template`
- `responsible_id` **(many2one)** — Responsible → `sign.item.role`
- `option_ids` **(many2many)** — Selection options → `sign.item.option`
- `radio_set_id` **(many2one)** — Radio button options → `sign.item.radio.set`

## Campos Calculados (readonly)

- `num_options` **(integer)** — Number of Radio Button options 🔒 readonly
