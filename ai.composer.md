# AI model configurations (system prompts) for text drafting. — `ai.composer`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Rule Name ⚠️ obrigatório
  > The identifier for the interface component to agent rule
- `interface_key` **(selection)** — Action ⚠️ obrigatório
  > Opções: `html_field_record` (Write in an HTML field), `mail_composer` (Write an email), `html_field_text_select` (Rewrite content), `chatter_ai_button` (Get help on a record), `html_prompt_shortcut` (Convert a prompt in an email), `systray_ai_button` (Ask AI for help), `voice_transcription_component` (Summary Buttons for Voice Transcription Component), `html_field_knowledge` (Write a new Knowledge article)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `default_prompt` **(text)** — Instructions
- `is_system_default` **(boolean)** — Is the rule a system default or user created 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `focused_models` **(many2many)** — Models → `ir.model`
- `ai_agent` **(many2one)** — Agent → `ai.agent`
- `available_prompts` **(one2many)** — Available User Prompts → `ai.prompt.button`
