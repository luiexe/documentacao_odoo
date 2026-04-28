# Website Product Category — `product.public.category`

**Ordenação padrão:** `sequence, name, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `image_1920` **(binary)** — Image
- `image_1024` **(binary)** — Image 1024 🔒 readonly
- `image_512` **(binary)** — Image 512 🔒 readonly
- `image_256` **(binary)** — Image 256 🔒 readonly
- `image_128` **(binary)** — Image 128 🔒 readonly
- `is_seo_optimized` **(boolean)** — SEO optimized 🔒 readonly
- `website_meta_title` **(char)** — Website meta title
- `website_meta_description` **(text)** — Website meta description
- `website_meta_keywords` **(char)** — Website meta keywords
- `website_meta_og_img` **(char)** — Website opengraph image
- `seo_name` **(char)** — Seo name
- `cover_image` **(binary)** — Cover Image
  > Displayed only in the Category List Snippet.
- `sequence` **(integer)** — Sequence
- `parent_path` **(char)** — Parent Path
- `website_description` **(html)** — Description
- `website_footer` **(html)** — Category Footer
- `show_category_title` **(boolean)** — Show Category Title
  > Display the category title on the shop page. Corresponds to the 'Show Title' editor option.
- `show_category_description` **(boolean)** — Show Category Description
  > Display the category description on the shop page. Corresponds to the 'Show Description' editor option.
- `align_category_content` **(boolean)** — Align Category Content
  > Align the category content on the shop page. Corresponds to the 'Center Content' editor option.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `website_id` **(many2one)** — Website → `website`
  > Restrict to a specific website.
- `parent_id` **(many2one)** — Parent → `product.public.category`
- `child_id` **(one2many)** — Children Categories → `product.public.category`
- `parents_and_self` **(many2many)** — Parents And Self 🔒 readonly → `product.public.category`
- `product_tmpl_ids` **(many2many)** — Product Tmpl → `product.template`

## Campos Calculados (readonly)

- `has_published_products` **(boolean)** — Has Published Products 🔒 readonly
