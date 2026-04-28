# Blog — `blog.blog`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `name` **(char)** — Blog Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `cover_properties` **(text)** — Cover Properties
- `is_seo_optimized` **(boolean)** — SEO optimized 🔒 readonly
- `website_meta_title` **(char)** — Website meta title
- `website_meta_description` **(text)** — Website meta description
- `website_meta_keywords` **(char)** — Website meta keywords
- `website_meta_og_img` **(char)** — Website opengraph image
- `seo_name` **(char)** — Seo name
- `sequence` **(integer)** — Sequence
- `subtitle` **(char)** — Blog Subtitle
- `active` **(boolean)** — Active
- `content` **(html)** — Content
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `website_id` **(many2one)** — Website → `website`
  > Restrict to a specific website.
- `blog_post_ids` **(one2many)** — Blog Posts → `blog.post`

## Campos Calculados (readonly)

- `blog_post_count` **(integer)** — Posts 🔒 readonly
