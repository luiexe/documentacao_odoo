# AI Agent Source — `ai.agent.source`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `agent_id` **(many2one)** — Agent ⚠️ obrigatório → `ai.agent`
- `type` **(selection)** — Type ⚠️ obrigatório 🔒 readonly
  > Opções: `url` (URL), `binary` (File), `document` (Document), `knowledge_article` (Knowledge Article)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `status` **(selection)** — Status
  > Opções: `processing` (Processing), `indexed` (Indexed), `failed` (Failed)
- `is_active` **(boolean)** — Active
  > If the source is active, it will be used in the RAG context.
- `error_details` **(text)** — Error Details 🔒 readonly
- `url` **(char)** — URL
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `attachment_id` **(many2one)** — Attachment → `ir.attachment`
- `document_id` **(many2one)** — Source Document → `documents.document`
- `article_id` **(many2one)** — Source Article → `knowledge.article`

## Campos Calculados (readonly)

- `mimetype` **(char)** — Mime Type 🔒 readonly
- `file_size` **(integer)** — File Size 🔒 readonly
- `user_has_access` **(boolean)** — User Has Access 🔒 readonly
