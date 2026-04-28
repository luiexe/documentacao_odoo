# Product Image — `product.image`

**Ordenação padrão:** `sequence, id`

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
- `sequence` **(integer)** — Sequence
- `video_url` **(char)** — Video URL
  > URL of a video for showcasing your product.
- `can_image_1024_be_zoomed` **(boolean)** — Can Image 1024 be zoomed 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `product_tmpl_id` **(many2one)** — Product Template → `product.template`
- `product_variant_id` **(many2one)** — Product Variant → `product.product`

## Campos Calculados (readonly)

- `embed_code` **(html)** — Embed Code 🔒 readonly
