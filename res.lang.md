# Languages — `res.lang`

**Ordenação padrão:** `active desc,name`

---

## Campos Obrigatórios

- `name` **(char)** — Name ⚠️ obrigatório
- `code` **(char)** — Locale Code ⚠️ obrigatório
  > This field is used to set/get locales for user
- `url_code` **(char)** — URL Code ⚠️ obrigatório
  > The Lang Code displayed in the URL
- `direction` **(selection)** — Direction ⚠️ obrigatório
  > Opções: `ltr` (Left-to-Right), `rtl` (Right-to-Left)
- `date_format` **(selection)** — Date Format ⚠️ obrigatório
  > Opções: `%d/%m/%Y` (31/01/2026), `%m/%d/%Y` (01/31/2026), `%Y/%m/%d` (2026/01/31), `%d-%m-%Y` (31-01-2026), `%m-%d-%Y` (01-31-2026), `%Y-%m-%d` (2026-01-31), `%d.%m.%Y` (31.01.2026), `%m.%d.%Y` (01.31.2026), `%Y.%m.%d` (2026.01.31)
- `time_format` **(selection)** — Time Format ⚠️ obrigatório
  > Opções: `%H:%M:%S` (13:00:00), `%I:%M:%S %p` ( 1:00:00 PM)
- `week_start` **(selection)** — First Day of Week ⚠️ obrigatório
  > Opções: `1` (Monday), `2` (Tuesday), `3` (Wednesday), `4` (Thursday), `5` (Friday), `6` (Saturday), `7` (Sunday)
- `grouping` **(selection)** — Separator Format ⚠️ obrigatório
  > The International Grouping will represent 123456789 to be 123,456,789.00; The Indian Grouping will represent 123456789 to be 12,34,56,789.00
  > Opções: `[3,0]` (International Grouping), `[3,2,0]` (Indian Grouping)
- `decimal_point` **(char)** — Decimal Separator ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `iso_code` **(char)** — ISO code
  > This ISO code is the name of po files to use for translations
- `active` **(boolean)** — Active
- `thousands_sep` **(char)** — Thousands Separator
- `flag_image` **(binary)** — Image
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Campos Calculados (readonly)

- `flag_image_url` **(char)** — Flag Image Url 🔒 readonly
