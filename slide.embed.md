# Embedded Slides View Counter — `slide.embed`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `slide_id` **(many2one)** — Presentation ⚠️ obrigatório → `slide.slide`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `url` **(char)** — Third Party Website URL
- `count_views` **(integer)** — # Views
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `website_name` **(char)** — Website 🔒 readonly
