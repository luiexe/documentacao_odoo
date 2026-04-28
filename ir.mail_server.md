# Mail Server — `ir.mail_server`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `smtp_authentication` **(selection)** — Authenticate with ⚠️ obrigatório
  > Opções: `login` (Username), `certificate` (SSL Certificate), `cli` (Command Line Interface), `gmail` (Gmail OAuth Authentication), `outlook` (Outlook OAuth Authentication)
- `smtp_encryption` **(selection)** — Connection Encryption ⚠️ obrigatório
  > Choose the connection encryption scheme: - None: SMTP sessions are done in cleartext. - TLS (STARTTLS): TLS encryption is requested at start of SMTP session (Recommended) - SSL/TLS: SMTP sessions are encrypted with SSL/TLS through a dedicated port (default: 465)  Choose an additionnal variant for SSL or TLS: - encryption and validation: encrypt the data and authentify the server using its SSL certificate (Recommended) - encryption only: encrypt the data but skip server authentication
  > Opções: `none` (None), `starttls_strict` (TLS (STARTTLS), encryption and validation), `starttls` (TLS (STARTTLS), encryption only), `ssl_strict` (SSL/TLS, encryption and validation), `ssl` (SSL/TLS, encryption only)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `microsoft_outlook_refresh_token` **(char)** — Outlook Refresh Token
- `microsoft_outlook_access_token` **(char)** — Outlook Access Token
- `microsoft_outlook_access_token_expiration` **(integer)** — Outlook Access Token Expiration Timestamp
- `google_gmail_refresh_token` **(char)** — Refresh Token
- `google_gmail_access_token` **(char)** — Access Token
- `google_gmail_access_token_expiration` **(integer)** — Access Token Expiration Timestamp
- `from_filter` **(char)** — FROM Filtering
  > Comma-separated list of addresses or domains for which this server can be used. e.g.: "notification@odoo.com" or "odoo.com"
- `smtp_host` **(char)** — SMTP Server
  > Hostname or IP of SMTP server
- `smtp_port` **(integer)** — SMTP Port
  > SMTP Port. Usually 465 for SSL, and 25 or 587 for other cases.
- `smtp_user` **(char)** — Username
  > Optional username for SMTP authentication
- `smtp_pass` **(char)** — Password
  > Optional password for SMTP authentication
- `smtp_ssl_certificate` **(binary)** — SSL Certificate
  > SSL certificate used for authentication
- `smtp_ssl_private_key` **(binary)** — SSL Private Key
  > SSL private key used for authentication
- `smtp_debug` **(boolean)** — Debugging
  > If enabled, the full output of SMTP sessions will be written to the server log at DEBUG level (this is very verbose and may include confidential info!)
- `max_email_size` **(float)** — Max Email Size
- `sequence` **(integer)** — Priority
  > When no specific mail server is requested for a mail, the highest priority one is used. Default priority is 10 (smaller number = higher priority)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `owner_limit_time` **(datetime)** — Owner Limit Time
- `owner_limit_count` **(integer)** — Owner Limit Count

## Relacionamentos

- `mail_template_ids` **(one2many)** — Mail template using this mail server 🔒 readonly → `mail.template`
- `owner_user_id` **(many2one)** — Owner → `res.users`
- `active_mailing_ids` **(one2many)** — Active mailing using this mail server 🔒 readonly → `mailing.mailing`

## Campos Calculados (readonly)

- `microsoft_outlook_uri` **(char)** — Authentication URI 🔒 readonly
  > The URL to generate the authorization code from Outlook
- `google_gmail_uri` **(char)** — URI 🔒 readonly
  > The URL to generate the authorization code from Google
- `smtp_authentication_info` **(text)** — Authentication Info 🔒 readonly
