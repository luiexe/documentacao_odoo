# Message Translation — `mail.message.translation`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `message_id` **(many2one)** — Message ⚠️ obrigatório → `mail.message`
- `source_lang` **(char)** — Source Language ⚠️ obrigatório
  > Result of the language detection based on its content.
- `target_lang` **(char)** — Target Language ⚠️ obrigatório
  > Shortened language code used as the target for the translation request.
- `body` **(html)** — Translation Body ⚠️ obrigatório
  > String received from the translation request.

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `create_date` **(datetime)** — Create Date
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
