# WhatsApp Template — `whatsapp.template`

**Ordenação padrão:** `sequence asc, write_date desc, id`

---

## Campos Obrigatórios

- `sequence` **(integer)** — Sequence ⚠️ obrigatório
- `model_id` **(many2one)** — Applies to ⚠️ obrigatório → `ir.model`
- `phone_field` **(char)** — Phone Field ⚠️ obrigatório
- `lang_code` **(selection)** — Language ⚠️ obrigatório
  > Opções: `af` (Afrikaans), `sq` (Albanian), `ar` (Arabic), `ar_EG` (Arabic (EGY)), `ar_LB` (Arabic (LBN)), `ar_MA` (Arabic (MAR)), `ar_QA` (Arabic (QAT)), `ar_AE` (Arabic (UAE)), `az` (Azerbaijani), `be_BY` (Belarusian), `bn` (Bengali), `bn_IN` (Bengali (IND)), `bg` (Bulgarian), `ca` (Catalan), `zh_CN` (Chinese (CHN)), `zh_HK` (Chinese (HKG)), `zh_TW` (Chinese (TAI)), `hr` (Croatian), `cs` (Czech), `da` (Danish), `prs_AF` (Dari), `nl` (Dutch), `nl_BE` (Dutch (BEL)), `en` (English), `en_GB` (English (UK)), `en_US` (English (US)), `en_AU` (English (AUS)), `en_CA` (English (CAN)), `en_GH` (English (GHA)), `en_IN` (English (IND)), `en_IE` (English (IRL)), `en_JM` (English (JAM)), `en_MY` (English (MYS)), `en_NZ` (English (NZL)), `en_QA` (English (QAT)), `en_SG` (English (SGP)), `en_AE` (English (UAE)), `en_UG` (English (UGA)), `en_ZA` (English (ZAF)), `et` (Estonian), `fil` (Filipino), `fi` (Finnish), `fr` (French), `fr_BE` (French (BEL)), `fr_CA` (French (CAN)), `fr_CH` (French (CHE)), `fr_CI` (French (CIV)), `fr_MA` (French (MAR)), `ka` (Georgian), `de` (German), `de_AT` (German (AUT)), `de_CH` (German (CHE)), `el` (Greek), `gu` (Gujarati), `ha` (Hausa), `he` (Hebrew), `hi` (Hindi), `hu` (Hungarian), `id` (Indonesian), `ga` (Irish), `it` (Italian), `ja` (Japanese), `kn` (Kannada), `kk` (Kazakh), `rw_RW` (Kinyarwanda), `ko` (Korean), `ky_KG` (Kyrgyz (Kyrgyzstan)), `lo` (Lao), `lv` (Latvian), `lt` (Lithuanian), `mk` (Macedonian), `ms` (Malay), `ml` (Malayalam), `mr` (Marathi), `nb` (Norwegian), `ps_AF` (Pashto), `fa` (Persian), `pl` (Polish), `pt_BR` (Portuguese (BR)), `pt_PT` (Portuguese (POR)), `pa` (Punjabi), `ro` (Romanian), `ru` (Russian), `sr` (Serbian), `si_LK` (Sinhala), `sk` (Slovak), `sl` (Slovenian), `es` (Spanish), `es_AR` (Spanish (ARG)), `es_CL` (Spanish (CHL)), `es_CO` (Spanish (COL)), `es_CR` (Spanish (CRI)), `es_DO` (Spanish (DOM)), `es_EC` (Spanish (ECU)), `es_HN` (Spanish (HND)), `es_MX` (Spanish (MEX)), `es_PA` (Spanish (PAN)), `es_PE` (Spanish (PER)), `es_ES` (Spanish (SPA)), `es_UY` (Spanish (URY)), `sw` (Swahili), `sv` (Swedish), `ta` (Tamil), `te` (Telugu), `th` (Thai), `tr` (Turkish), `uk` (Ukrainian), `ur` (Urdu), `uz` (Uzbek), `vi` (Vietnamese), `zu` (Zulu)
- `template_type` **(selection)** — Category ⚠️ obrigatório
  > Authentication - One-time passwords that your customers use to authenticate a transaction or login. Marketing - Promotions or information about your business, products or services. Or any message that isn't utility or authentication. Utility - Messages about a specific transaction, account, order or customer request.
  > Opções: `authentication` (Authentication), `marketing` (Marketing), `utility` (Utility)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `template_name` **(char)** — Template Name
- `active` **(boolean)** — Active
- `wa_template_uid` **(char)** — WhatsApp Template ID
- `error_msg` **(char)** — Error Message
- `model` **(char)** — Related Document Model 🔒 readonly
- `status` **(selection)** — Status
  > Opções: `draft` (Draft), `pending` (Pending), `in_appeal` (In Appeal), `approved` (Approved), `paused` (Paused), `disabled` (Disabled), `rejected` (Rejected), `pending_deletion` (Pending Deletion), `deleted` (Deleted), `limit_exceeded` (Limit Exceeded)
- `quality` **(selection)** — Quality
  > Opções: `none` (None), `red` (Red), `yellow` (Yellow), `green` (Green)
- `body` **(text)** — Template body
- `header_type` **(selection)** — Header Type
  > Opções: `none` (None), `text` (Text), `image` (Image), `video` (Video), `document` (Document), `location` (Location)
- `header_text` **(char)** — Template Header Text
- `footer_text` **(char)** — Footer Message
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `wa_account_id` **(many2one)** — Account → `whatsapp.account`
- `allowed_user_ids` **(many2many)** — Users → `res.users`
- `header_attachment_ids` **(many2many)** — Template Static Header → `ir.attachment`
- `report_id` **(many2one)** — Report → `ir.actions.report`
- `variable_ids` **(one2many)** — Template Variables → `whatsapp.template.variable`
- `button_ids` **(one2many)** — Buttons → `whatsapp.template.button`

## Campos Calculados (readonly)

- `warning_message` **(text)** — Warning Message 🔒 readonly
- `messages_count` **(integer)** — Messages Count 🔒 readonly
- `has_action` **(boolean)** — Has Action 🔒 readonly
- `is_demo_account` **(boolean)** — Is Demo Account 🔒 readonly
