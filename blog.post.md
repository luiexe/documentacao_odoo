# Blog Post — `blog.post`

**Ordenação padrão:** `id DESC`

---

## Campos Obrigatórios

- `name` **(char)** — Title ⚠️ obrigatório
- `blog_id` **(many2one)** — Blog ⚠️ obrigatório → `blog.blog`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `cover_properties` **(text)** — Cover Properties
- `header_visible` **(boolean)** — Header Visible
- `footer_visible` **(boolean)** — Footer Visible
- `website_published` **(boolean)** — Visible on current website
- `is_published` **(boolean)** — Is Published
- `is_seo_optimized` **(boolean)** — SEO optimized 🔒 readonly
- `website_meta_title` **(char)** — Website meta title
- `website_meta_description` **(text)** — Website meta description
- `website_meta_keywords` **(char)** — Website meta keywords
- `website_meta_og_img` **(char)** — Website opengraph image
- `seo_name` **(char)** — Seo name
- `subtitle` **(char)** — Sub Title
- `author_avatar` **(binary)** — Avatar
- `author_name` **(char)** — Author Name
- `active` **(boolean)** — Active
- `content` **(html)** — Content
- `teaser` **(text)** — Teaser
- `teaser_manual` **(text)** — Teaser Content
- `create_date` **(datetime)** — Created on 🔒 readonly
- `published_date` **(datetime)** — Published Date
- `post_date` **(datetime)** — Publishing date
  > The blog post will be visible for your visitors as of this date on the website if it is set as published.
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `visits` **(integer)** — No of Views 🔒 readonly

## Relacionamentos

- `website_id` **(many2one)** — Website 🔒 readonly → `website`
  > Restrict to a specific website.
- `author_id` **(many2one)** — Author → `res.partner`
- `tag_ids` **(many2many)** — Tags → `blog.tag`

## Campos Calculados (readonly)

- `can_publish` **(boolean)** — Can Publish 🔒 readonly
- `website_url` **(char)** — Website URL 🔒 readonly
  > The full relative URL to access the document through the website.
- `website_absolute_url` **(char)** — Website Absolute URL 🔒 readonly
  > The full absolute URL to access the document through the website.
