# Attachment Chunks Embedding — `ai.embedding`

**Ordenação padrão:** `sequence`

---

## Campos Obrigatórios

- `attachment_id` **(many2one)** — Attachment ⚠️ obrigatório → `ir.attachment`
- `content` **(text)** — Chunk Content ⚠️ obrigatório
- `embedding_model` **(selection)** — Embedding Model ⚠️ obrigatório
  > Opções: `text-embedding-3-small` (OpenAI), `gemini-embedding-001` (Google)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `has_embedding_generation_failed` **(boolean)** — Has Embedding Generation Failed
- `embedding_vector` **(vector)** — Embedding Vector
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `checksum` **(char)** — Checksum/SHA1 🔒 readonly
