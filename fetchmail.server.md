# Incoming Mail Server — `fetchmail.server`

**Ordenação padrão:** `priority`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `server_type` **(selection)** — Server Type ⚠️ obrigatório
  > Opções: `imap` (IMAP Server), `pop` (POP Server), `local` (Local Server), `gmail` (Gmail OAuth Authentication), `outlook` (Outlook OAuth Authentication)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `microsoft_outlook_refresh_token` **(char)** — Outlook Refresh Token
- `microsoft_outlook_access_token` **(char)** — Outlook Access Token
- `microsoft_outlook_access_token_expiration` **(integer)** — Outlook Access Token Expiration Timestamp
- `google_gmail_refresh_token` **(char)** — Refresh Token
- `google_gmail_access_token` **(char)** — Access Token
- `google_gmail_access_token_expiration` **(integer)** — Access Token Expiration Timestamp
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `draft` (Not Confirmed), `done` (Confirmed)
- `server` **(char)** — Server Name
  > Hostname or IP of the mail server
- `port` **(integer)** — Port
- `is_ssl` **(boolean)** — SSL/TLS
  > Connections are encrypted with SSL/TLS through a dedicated port (default: IMAPS=993, POP3S=995)
- `attach` **(boolean)** — Keep Attachments
  > Whether attachments should be downloaded. If not enabled, incoming emails will be stripped of any attachments before being processed
- `original` **(boolean)** — Keep Original
  > Whether a full original copy of each email should be kept for reference and attached to each processed message. This will usually double the size of your message database.
- `date` **(datetime)** — Last Fetch Date 🔒 readonly
- `error_date` **(datetime)** — Last Error Date 🔒 readonly
  > Date of last failure, reset on success.
- `error_message` **(text)** — Last Error Message 🔒 readonly
- `user` **(char)** — Username
- `password` **(char)** — Password
- `priority` **(integer)** — Server Priority
  > Defines the order of processing, lower values mean higher priority
- `configuration` **(text)** — Configuration 🔒 readonly
- `script` **(char)** — Script 🔒 readonly
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `object_id` **(many2one)** — Create a New Record → `ir.model`
  > Process each incoming mail as part of a conversation corresponding to this document type. This will create new documents for new conversations, or attach follow-up emails to the existing conversations (documents).

## Campos Calculados (readonly)

- `microsoft_outlook_uri` **(char)** — Authentication URI 🔒 readonly
  > The URL to generate the authorization code from Outlook
- `google_gmail_uri` **(char)** — URI 🔒 readonly
  > The URL to generate the authorization code from Google
- `server_type_info` **(text)** — Server Type Info 🔒 readonly
