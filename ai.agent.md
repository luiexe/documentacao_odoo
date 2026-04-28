# AI Agent — `ai.agent`

**Ordenação padrão:** `name`

---

## Campos Obrigatórios

- `name` **(char)** — Agent Name ⚠️ obrigatório
- `response_style` **(selection)** — Response Style ⚠️ obrigatório
  > Opções: `analytical` (Analytical), `balanced` (Balanced), `creative` (Creative)
- `llm_model` **(selection)** — LLM Model ⚠️ obrigatório
  > Opções: `gpt-3.5-turbo` (GPT-3.5 Turbo), `gpt-4` (GPT-4), `gpt-4o` (GPT-4o), `gpt-4.1` (GPT-4.1), `gpt-4.1-mini` (GPT-4.1 Mini), `gpt-5` (GPT-5), `gpt-5-mini` (GPT-5 Mini), `gemini-2.5-pro` (Gemini 2.5 Pro), `gemini-2.5-flash` (Gemini 2.5 Flash), `gemini-1.5-pro` (Gemini 1.5 Pro), `gemini-1.5-flash` (Gemini 1.5 Flash)
- `partner_id` **(many2one)** — Partner ⚠️ obrigatório → `res.partner`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `subtitle` **(char)** — Description
- `system_prompt` **(text)** — System Prompt
  > Customize to control relevance and formatting.
- `restrict_to_sources` **(boolean)** — Restrict to Sources
  > If checked, the agent will only respond based on the provided sources.
- `image_128` **(binary)** — Image
- `is_system_agent` **(boolean)** — System Agent
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `topic_ids` **(many2many)** — Topics → `ai.topic`
  > A topic includes instructions and tools that guide Odoo AI in helping the user complete their tasks.
- `sources_ids` **(one2many)** — Sources → `ai.agent.source`

## Campos Calculados (readonly)

- `avatar_128` **(binary)** — Avatar 🔒 readonly
- `sources_fully_processed` **(boolean)** — Sources Fully Processed 🔒 readonly
- `is_ask_ai_agent` **(boolean)** — Is Natural Language Query Agent 🔒 readonly
