# Discussion Channel — `discuss.channel`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `channel_type` **(selection)** — Channel Type ⚠️ obrigatório 🔒 readonly
  > Chat is private and unique between 2 persons. Group is private among invited persons. Channel can be freely joined (depending on its configuration).
  > Opções: `chat` (Chat), `channel` (Channel), `group` (Group), `ai_chat` (AI chat), `whatsapp` (WhatsApp Conversation)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
  > Set active to false to hide the channel without removing it.
- `default_display_mode` **(selection)** — Default Display Mode
  > Determines how the channel will be displayed by default when opening it from its invitation link. No value means display text (no voice/video).
  > Opções: `video_full_screen` (Full screen video)
- `description` **(text)** — Description
- `image_128` **(binary)** — Image
- `sfu_channel_uuid` **(char)** — Sfu Channel Uuid
- `sfu_server_url` **(char)** — Sfu Server Url
- `last_interest_dt` **(datetime)** — Last Interest
  > Contains the date and time of the last interesting event that happened in this channel. This updates itself when new message posted.
- `uuid` **(char)** — UUID
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `ai_env_context` **(json)** — Context for AI agent
- `whatsapp_number` **(char)** — Phone Number

## Relacionamentos

- `channel_partner_ids` **(many2many)** — Partners → `res.partner`
- `channel_member_ids` **(one2many)** — Members → `discuss.channel.member`
- `parent_channel_id` **(many2one)** — Parent Channel 🔒 readonly → `discuss.channel`
  > Parent channel
- `sub_channel_ids` **(one2many)** — Sub Channels 🔒 readonly → `discuss.channel`
- `from_message_id` **(many2one)** — From Message 🔒 readonly → `mail.message`
  > The message the channel was created from.
- `pinned_message_ids` **(one2many)** — Pinned Messages → `mail.message`
- `rtc_session_ids` **(one2many)** — Rtc Session → `discuss.channel.rtc.session`
- `call_history_ids` **(one2many)** — Call History → `discuss.call.history`
- `self_member_id` **(many2one)** — Self Member 🔒 readonly → `discuss.channel.member`
- `invited_member_ids` **(one2many)** — Invited Member 🔒 readonly → `discuss.channel.member`
- `group_ids` **(many2many)** — Auto Subscription → `res.groups`
  > Members of those groups will automatically added as followers. Note that they will be able to manage their subscription manually if necessary.
- `group_public_id` **(many2one)** — Authorized Group → `res.groups`
- `channel_name_member_ids` **(one2many)** — Channel Name Member 🔒 readonly → `discuss.channel.member`
  > Members from which the channel name is computed when the name field is empty.
- `calendar_event_ids` **(one2many)** — Calendar Event → `calendar.event`
- `last_wa_mail_message_id` **(many2one)** — Last WA Partner Mail Message → `mail.message`
- `whatsapp_partner_id` **(many2one)** — WhatsApp Partner → `res.partner`
- `wa_account_id` **(many2one)** — WhatsApp Business Account → `whatsapp.account`
- `subscription_department_ids` **(many2many)** — HR Departments → `hr.department`
  > Automatically subscribe members of those departments to the channel.

## Campos Calculados (readonly)

- `is_editable` **(boolean)** — Is Editable 🔒 readonly
- `avatar_128` **(binary)** — Avatar 🔒 readonly
- `avatar_cache_key` **(char)** — Avatar Cache Key 🔒 readonly
- `is_member` **(boolean)** — Is Member 🔒 readonly
- `member_count` **(integer)** — Member Count 🔒 readonly
- `message_count` **(integer)** — # Messages 🔒 readonly
- `invitation_url` **(char)** — Invitation URL 🔒 readonly
- `whatsapp_channel_valid_until` **(datetime)** — WhatsApp Channel Valid Until Datetime 🔒 readonly
- `whatsapp_channel_active` **(boolean)** — Is Whatsapp Channel Active 🔒 readonly
