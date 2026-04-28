# Certificate — `certificate.certificate`

**Ordenação padrão:** `date_end DESC`

---

## Campos Obrigatórios

- `content` **(binary)** — Certificate ⚠️ obrigatório
- `company_id` **(many2one)** — Company ⚠️ obrigatório → `res.company`

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `name` **(char)** — Name
- `pkcs12_password` **(char)** — Certificate Password
  > Password to decrypt the PKS file.
- `scope` **(selection)** — Certificate scope
  > Opções: `general` (General)
- `content_format` **(selection)** — Original certificate format 🔒 readonly
  > Opções: `der` (DER), `pem` (PEM), `pkcs12` (PKCS12)
- `pem_certificate` **(binary)** — Certificate in PEM format 🔒 readonly
- `subject_common_name` **(char)** — Subject Name 🔒 readonly
- `serial_number` **(char)** — Serial number 🔒 readonly
  > The serial number to add to electronic documents
- `date_start` **(datetime)** — Available date 🔒 readonly
  > The date on which the certificate starts to be valid
- `date_end` **(datetime)** — Expiration date 🔒 readonly
  > The date on which the certificate expires
- `loading_error` **(text)** — Loading error 🔒 readonly
- `active` **(boolean)** — Active
  > Set active to false to archive the certificate
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `private_key_id` **(many2one)** — Private Key → `certificate.key`
- `public_key_id` **(many2one)** — Public Key → `certificate.key`
  > Used to set a public key in case the one self-contained in the certificate is erroneus.                 When a public key is set this way, it will be used instead of the one in the certificate.              

## Campos Calculados (readonly)

- `is_valid` **(boolean)** — Valid 🔒 readonly
- `country_code` **(char)** — Country Code 🔒 readonly
  > The ISO country code in two chars.  You can use this field for quick search.
