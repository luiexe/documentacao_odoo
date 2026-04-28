# Payment Provider — `payment.provider`

**Ordenação padrão:** `module_state, state desc, sequence, name`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `code` **(selection)** — Code ⚠️ obrigatório
  > The technical code of this payment provider.
  > Opções: `none` (No Provider Set), `custom` (Custom), `demo` (Demo), `mercado_pago` (Mercado Pago), `stripe` (Stripe)
- `state` **(selection)** — State ⚠️ obrigatório
  > In test mode, a fake payment is processed through a test payment interface. This mode is advised when setting up the provider.
  > Opções: `disabled` (Disabled), `enabled` (Enabled), `test` (Test Mode)
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
  > Define the display order
- `is_published` **(boolean)** — Published
  > Whether the provider is visible on the website or not. Tokens remain functional but are only visible on manage forms.
- `allow_tokenization` **(boolean)** — Allow Saving Payment Methods
  > This controls whether customers can save their payment methods as payment tokens. A payment token is an anonymous link to the payment method details saved in the provider's database, allowing the customer to reuse it for a next purchase.
- `capture_manually` **(boolean)** — Capture Amount Manually
  > Capture the amount from Odoo, when the delivery is completed. Use this if you want to charge your customers cards only when you are sure you can ship the goods to them.
- `allow_express_checkout` **(boolean)** — Allow Express Checkout
  > This controls whether customers can use express payment methods. Express checkout enables customers to pay with Google Pay and Apple Pay from which address information is collected at payment.
- `maximum_amount` **(monetary)** — Maximum Amount
  > The maximum payment amount that this payment provider is available for. Leave blank to make it available for any payment amount.
- `pre_msg` **(html)** — Help Message
  > The message displayed to explain and help the payment process
- `pending_msg` **(html)** — Pending Message
  > The message displayed if the order pending after the payment process
- `auth_msg` **(html)** — Authorize Message
  > The message displayed if payment is authorized
- `done_msg` **(html)** — Done Message
  > The message displayed if the order is successfully done after the payment process
- `cancel_msg` **(html)** — Cancelled Message
  > The message displayed if the order is cancelled during the payment process
- `image_128` **(binary)** — Image
- `color` **(integer)** — Color 🔒 readonly
  > The color of the card in kanban view
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `custom_mode` **(selection)** — Custom Mode
  > Opções: `wire_transfer` (Wire Transfer), `cash_on_delivery` (Cash On Delivery), `on_site` (Pay on site)
- `qr_code` **(boolean)** — Enable QR Codes
  > Enable the use of QR-codes when paying by wire transfer.
- `mercado_pago_access_token` **(char)** — Mercado Pago Access Token
- `mercado_pago_access_token_expiry` **(datetime)** — Mercado Pago Access Token Expiry
- `mercado_pago_refresh_token` **(char)** — Mercado Pago Refresh Token
- `mercado_pago_public_key` **(char)** — Mercado Pago Public Key
- `stripe_publishable_key` **(char)** — Publishable Key
  > The key solely used to identify the account with Stripe
- `stripe_secret_key` **(char)** — Secret Key
- `stripe_webhook_secret` **(char)** — Webhook Signing Secret
  > If a webhook is enabled on your Stripe account, this signing secret must be set to authenticate the messages sent from Stripe to Odoo.
- `stripe_account_id` **(char)** — Stripe Account 🔒 readonly
- `stripe_account_details_submitted` **(boolean)** — Stripe Account Details Submitted 🔒 readonly
- `so_reference_type` **(selection)** — Communication
  > You can set here the communication type that will appear on sales orders.The communication will be given to the customer when they choose the payment method.
  > Opções: `so_name` (Based on Document Reference), `partner` (Based on Customer ID)

## Relacionamentos

- `main_currency_id` **(many2one)** — Currency 🔒 readonly → `res.currency`
  > The main currency of the company, used to display monetary fields.
- `payment_method_ids` **(many2many)** — Supported Payment Methods → `payment.method`
- `redirect_form_view_id` **(many2one)** — Redirect Form Template → `ir.ui.view`
  > The template rendering a form submitted to redirect the user when making a payment
- `inline_form_view_id` **(many2one)** — Inline Form Template → `ir.ui.view`
  > The template rendering the inline payment form when making a direct payment
- `token_inline_form_view_id` **(many2one)** — Token Inline Form Template → `ir.ui.view`
  > The template rendering the inline payment form when making a payment by token.
- `express_checkout_form_view_id` **(many2one)** — Express Checkout Form Template → `ir.ui.view`
  > The template rendering the express payment methods' form.
- `available_country_ids` **(many2many)** — Countries → `res.country`
  > The countries in which this payment provider is available. Leave blank to make it available in all countries.
- `available_currency_ids` **(many2many)** — Currencies → `res.currency`
  > The currencies available with this payment provider. Leave empty not to restrict any.
- `module_id` **(many2one)** — Corresponding Module → `ir.module.module`
- `mercado_pago_account_country_id` **(many2one)** — Mercado Pago Account Country → `res.country`
  > The country of the Mercado Pago account. The currency will be updated to match the country of the Mercado Pago account.
- `journal_id` **(many2one)** — Payment Journal → `account.journal`
  > The journal in which the successful transactions are posted.
- `website_id` **(many2one)** — Website → `website`

## Campos Calculados (readonly)

- `support_tokenization` **(boolean)** — Tokenization 🔒 readonly
- `support_manual_capture` **(selection)** — Manual Capture Supported 🔒 readonly
  > Opções: `full_only` (Full Only), `partial` (Partial)
- `support_express_checkout` **(boolean)** — Express Checkout 🔒 readonly
- `support_refund` **(selection)** — Refund 🔒 readonly
  > Refund is a feature allowing to refund customers directly from the payment in Odoo.
  > Opções: `none` (Unsupported), `full_only` (Full Only), `partial` (Full & Partial)
- `module_state` **(selection)** — Installation State 🔒 readonly
  > Opções: `uninstallable` (Uninstallable), `uninstalled` (Not Installed), `installed` (Installed), `to upgrade` (To be upgraded), `to remove` (To be removed), `to install` (To be installed)
- `module_to_buy` **(boolean)** — Odoo Enterprise Module 🔒 readonly
- `mercado_pago_is_oauth_supported` **(boolean)** — Mercado Pago Is Oauth Supported 🔒 readonly
