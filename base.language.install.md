# Install Language — `base.language.install`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `lang_ids` **(many2many)** — Languages ⚠️ obrigatório → `res.lang`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `overwrite` **(boolean)** — Overwrite Existing Terms
  > If you check this box, your customized translations will be overwritten and replaced by the official ones.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `first_lang_id` **(many2one)** — First Lang 🔒 readonly → `res.lang`
  > Used when the user only selects one language and is given the option to switch to it
- `website_ids` **(many2many)** — Websites to translate → `website`
