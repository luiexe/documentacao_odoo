# Marketing Activity — `marketing.activity`

**Ordenação padrão:** `interval_standardized, id ASC`

---

## Campos Obrigatórios

- `source_id` **(many2one)** — Source ⚠️ obrigatório → `utm.source`
- `activity_type` **(selection)** — Activity Type ⚠️ obrigatório
  > Opções: `email` (Email), `action` (Server Action), `whatsapp` (Whatsapp Message)
- `campaign_id` **(many2one)** — Campaign ⚠️ obrigatório → `marketing.campaign`
- `interval_type` **(selection)** — Delay Type ⚠️ obrigatório
  > Opções: `hours` (Hours), `days` (Days), `weeks` (Weeks), `months` (Months)
- `validity_duration_type` **(selection)** — Validity Duration Type ⚠️ obrigatório
  > Opções: `hours` (Hours), `days` (Days), `weeks` (Weeks), `months` (Months)
- `trigger_type` **(selection)** — Trigger Type ⚠️ obrigatório
  > Opções: `begin` (beginning of workflow), `activity` (another activity), `mail_open` (Mail: opened), `mail_not_open` (Mail: not opened), `mail_reply` (Mail: replied), `mail_not_reply` (Mail: not replied), `mail_click` (Mail: clicked), `mail_not_click` (Mail: not clicked), `mail_bounce` (Mail: bounced), `whatsapp_click` (Whatsapp: click), `whatsapp_not_click` (Whatsapp: not click), `whatsapp_read` (Whatsapp: opened), `whatsapp_not_read` (Whatsapp: not opened), `whatsapp_replied` (Whatsapp: replied), `whatsapp_not_replied` (Whatsapp: not replied), `whatsapp_bounced` (Whatsapp: message bounced)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `mass_mailing_id_mailing_type` **(selection)** — Mailing Type 🔒 readonly
  > Opções: `mail` (Email)
- `interval_number` **(integer)** — Send after
- `interval_standardized` **(integer)** — Send after (in hours) 🔒 readonly
- `validity_duration` **(boolean)** — Validity Duration
  > Check this to make sure your actions are not executed after a specific amount of time after the scheduled date. (e.g. Time-limited offer, Upcoming event, …)
- `validity_duration_number` **(integer)** — Valid during
- `domain` **(char)** — Applied Filter 🔒 readonly
  > Activity will only be performed if record satisfies this domain, obtained from the combination of the activity filter and its inherited filter
- `activity_domain` **(char)** — Activity Filter
  > Domain that applies to this activity and its child activities
- `require_sync` **(boolean)** — Require trace sync
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `whatsapp_error` **(boolean)** — Whatsapp Error 🔒 readonly

## Relacionamentos

- `mass_mailing_id` **(many2one)** — Marketing Template → `mailing.mailing`
- `server_action_id` **(many2one)** — Server Action → `ir.actions.server`
- `utm_campaign_id` **(many2one)** — UTM Campaign 🔒 readonly → `utm.campaign`
- `model_id` **(many2one)** — Model 🔒 readonly → `ir.model`
- `parent_id` **(many2one)** — Activity → `marketing.activity`
- `allowed_parent_ids` **(many2many)** — Allowed parents 🔒 readonly → `marketing.activity`
  > All activities which can be the parent of this one
- `child_ids` **(one2many)** — Child Activities → `marketing.activity`
- `trace_ids` **(one2many)** — Traces → `marketing.trace`
- `whatsapp_template_id` **(many2one)** — Whatsapp Template → `whatsapp.template`

## Campos Calculados (readonly)

- `model_name` **(char)** — Model Name 🔒 readonly
- `trigger_category` **(selection)** — Trigger Category 🔒 readonly
  > Opções: `email` (Mail), `whatsapp` (WhatsApp)
- `processed` **(integer)** — Processed 🔒 readonly
- `rejected` **(integer)** — Rejected 🔒 readonly
- `total_sent` **(integer)** — Total Sent 🔒 readonly
- `total_click` **(integer)** — Total Click 🔒 readonly
- `total_open` **(integer)** — Total Open 🔒 readonly
- `total_reply` **(integer)** — Total Reply 🔒 readonly
- `total_bounce` **(integer)** — Total Bounce 🔒 readonly
- `statistics_graph_data` **(char)** — Statistics Graph Data 🔒 readonly
