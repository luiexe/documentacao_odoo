# Website — `website`

**Ordenação padrão:** `sequence, id`

---

## Campos Obrigatórios

- `name` **(char)** — Website Name ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`
- `language_ids` **(many2many)** — Languages ⚠️ obrigatório → `res.lang`
- `default_lang_id` **(many2one)** — Default Language ⚠️ obrigatório → `res.lang`
- `user_id` **(many2one)** — Public User ⚠️ obrigatório → `res.users`
- `shop_default_sort` **(selection)** — Shop Default Sort ⚠️ obrigatório
  > Opções: `website_sequence asc` (Featured), `publish_date desc` (Newest Arrivals), `name asc` (Name (A-Z)), `list_price asc` (Price - Low to High), `list_price desc` (Price - High to Low)
- `product_page_image_layout` **(selection)** — Product Page Image Layout ⚠️ obrigatório
  > Opções: `carousel` (Carousel), `grid` (Grid)
- `product_page_image_width` **(selection)** — Product Page Image Width ⚠️ obrigatório
  > Opções: `none` (Hidden), `33_pc` (33 %), `50_pc` (50 %), `66_pc` (66 %), `100_pc` (100 %)
- `product_page_image_spacing` **(selection)** — Product Page Image Spacing ⚠️ obrigatório
  > Opções: `none` (None), `small` (Small), `medium` (Medium), `big` (Big)
- `product_page_image_roundness` **(selection)** — Product Page Image Roundness ⚠️ obrigatório
  > Opções: `none` (None), `small` (Small), `medium` (Medium), `big` (Big)
- `product_page_image_ratio` **(selection)** — Product Page Image Ratio ⚠️ obrigatório
  > Opções: `auto` (Auto), `21_9` (Wider (21/9)), `16_9` (Wide (16/9)), `4_3` (Landscape (4/3)), `6_5` (Horizontal (6/5)), `1_1` (Default (1/1)), `4_5` (Portrait (4/5)), `2_3` (Vertical (2/3))
- `product_page_image_ratio_mobile` **(selection)** — Product Page Image Ratio Mobile ⚠️ obrigatório
  > Opções: `auto` (Auto), `21_9` (Wider (21/9)), `16_9` (Wide (16/9)), `4_3` (Landscape (4/3)), `6_5` (Horizontal (6/5)), `1_1` (Default (1/1)), `4_5` (Portrait (4/5)), `2_3` (Vertical (2/3))
- `ecommerce_access` **(selection)** — Ecommerce Access ⚠️ obrigatório
  > Opções: `everyone` (All users), `logged_in` (Logged in users)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `sequence` **(integer)** — Sequence
- `domain` **(char)** — Website Domain
  > E.g. https://www.mydomain.com
- `auto_redirect_lang` **(boolean)** — Autoredirect Language
  > Should users be redirected to their browser's language
- `cookies_bar` **(boolean)** — Cookies Bar
  > Display a customizable cookies bar on your website.
- `configurator_done` **(boolean)** — Configurator Done
  > True if configurator has been completed or ignored
- `block_third_party_domains` **(boolean)** — Block 3rd-party domains
  > Block 3rd-party domains that may track users (YouTube, Google Maps, etc.).
- `custom_blocked_third_party_domains` **(text)** — User list of blocked 3rd-party domains
- `logo` **(binary)** — Website Logo
  > Display this logo on the website.
- `social_twitter` **(char)** — X Account
- `social_facebook` **(char)** — Facebook Account
- `social_github` **(char)** — GitHub Account
- `social_linkedin` **(char)** — LinkedIn Account
- `social_youtube` **(char)** — Youtube Account
- `social_instagram` **(char)** — Instagram Account
- `social_tiktok` **(char)** — TikTok Account
- `social_discord` **(char)** — Discord Account
- `social_default_image` **(binary)** — Default Social Share Image
  > If set, replaces the website logo as the default social share image.
- `has_social_default_image` **(boolean)** — Has Social Default Image 🔒 readonly
- `google_analytics_key` **(char)** — Google Analytics Key
- `google_search_console` **(char)** — Google Search Console
  > Google key, or Enable to access first reply
- `google_maps_api_key` **(char)** — Google Maps API Key
- `plausible_shared_key` **(char)** — Plausible Shared Key
- `plausible_site` **(char)** — Plausible Site
- `cdn_activated` **(boolean)** — Content Delivery Network (CDN)
- `cdn_url` **(char)** — CDN Base URL
- `cdn_filters` **(text)** — CDN Filters
  > URL matching those filters will be rewritten using the CDN Base URL
- `homepage_url` **(char)** — Homepage Url
  > E.g. /contactus or /shop
- `custom_code_head` **(html)** — Custom <head> code
- `custom_code_footer` **(html)** — Custom end of <body> code
- `robots_txt` **(html)** — Robots.txt
- `favicon` **(binary)** — Website Favicon
  > This field holds the image used to display a favicon on the website.
- `specific_user_account` **(boolean)** — Specific User Account
  > If True, new accounts will be associated to the current website
- `auth_signup_uninvited` **(selection)** — Customer Account
  > Opções: `b2b` (On invitation), `b2c` (Free sign up)
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
- `karma_profile_min` **(integer)** — Minimal karma to see other user's profile
- `website_slide_google_app_key` **(char)** — Google Doc Key
- `show_line_subtotals_tax_selection` **(selection)** — Line Subtotals Tax Display
  > Opções: `tax_excluded` (Tax Excluded), `tax_included` (Tax Included)
- `add_to_cart_action` **(selection)** — Add To Cart Action
  > Opções: `stay` (Stay on Product Page), `go_to_cart` (Go to cart)
- `account_on_checkout` **(selection)** — Customer Accounts
  > Opções: `optional` (Optional), `disabled` (Disabled (buy as guest)), `mandatory` (Mandatory (no guest checkout))
- `contact_us_button_url` **(char)** — Contact Us Button URL
- `cart_abandoned_delay` **(float)** — Abandoned Delay
- `send_abandoned_cart_email` **(boolean)** — Send email to customers who abandoned their cart.
- `send_abandoned_cart_email_activation_time` **(datetime)** — Time when the 'Send abandoned cart email' feature was activated. 🔒 readonly
- `shop_page_container` **(selection)** — Shop Page Container
  > Opções: `regular` (Regular), `fluid` (Full-width)
- `shop_ppg` **(integer)** — Number of products in the grid on the shop
- `shop_ppr` **(integer)** — Number of grid columns on the shop
- `shop_gap` **(char)** — Grid-gap on the shop
- `shop_opt_products_design_classes` **(char)** — Shop Design Class
  > CSS class for shop products design
- `product_page_container` **(selection)** — Product Page Container
  > Opções: `unset` (Unset), `regular` (Regular), `fluid` (Full-width)
- `product_page_cols_order` **(selection)** — Product Page main columns order
  > Opções: `regular` (Regular order), `inverse` (Inverse order)
- `product_page_grid_columns` **(integer)** — Product Page Grid Columns
- `prevent_zero_price_sale` **(boolean)** — Hide 'Add To Cart' when price = 0
- `enabled_gmc_src` **(boolean)** — Google Merchant Center
- `wishlist_opt_products_design_classes` **(char)** — Wishlist Page Design Class
  > CSS class for wishlist page design
- `wishlist_grid_columns` **(integer)** — Wishlist Grid Columns
  > Number of columns to display on the wishlist page
- `wishlist_mobile_columns` **(integer)** — Wishlist Mobile Columns
  > Number of columns to display on mobile for the wishlist page (1 or 2)
- `wishlist_gap` **(char)** — Wishlist Grid Gap
  > Gap between products on the wishlist page

## Relacionamentos

- `partner_id` **(many2one)** — Public Partner → `res.partner`
  > Partner-related data of the user
- `menu_id` **(many2one)** — Main Menu 🔒 readonly → `website.menu`
- `theme_id` **(many2one)** — Theme → `ir.module.module`
  > Installed theme
- `crm_default_team_id` **(many2one)** — Default Sales Teams → `crm.team`
  > Default Sales Team for new leads created through the Contact Us form.
- `crm_default_user_id` **(many2one)** — Default Salesperson → `res.users`
  > Default salesperson for new leads created through the Contact Us form.
- `salesperson_id` **(many2one)** — Salesperson → `res.users`
- `salesteam_id` **(many2one)** — Sales Team → `crm.team`
- `cart_recovery_mail_template_id` **(many2one)** — Cart Recovery Email → `mail.template`
- `shop_extra_field_ids` **(one2many)** — E-Commerce Extra Fields → `website.sale.extra.field`
- `currency_id` **(many2one)** — Default Currency 🔒 readonly → `res.currency`
- `pricelist_ids` **(one2many)** — Price list available for this Ecommerce/Website 🔒 readonly → `product.pricelist`
- `confirmation_email_template_id` **(many2one)** — Confirmation Email Template → `mail.template`
- `newsletter_id` **(many2one)** — Newsletter List → `mailing.list`
- `warehouse_id` **(many2one)** — Warehouse → `stock.warehouse`
- `wa_sale_template_id` **(many2one)** — Wa Sale Template → `whatsapp.template`
- `in_store_dm_id` **(many2one)** — In-store Delivery Method 🔒 readonly → `delivery.carrier`

## Campos Calculados (readonly)

- `domain_punycode` **(char)** — Punycode Domain 🔒 readonly
- `language_count` **(integer)** — Number of languages 🔒 readonly
- `blocked_third_party_domains` **(text)** — List of blocked 3rd-party domains 🔒 readonly
