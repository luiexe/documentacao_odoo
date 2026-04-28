# Account Lock Exception — `account.lock_exception`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `company_id` **(many2one)** — Company ⚠️ obrigatório 🔒 readonly → `res.company`
- `lock_date_field` **(selection)** — Lock Date Field ⚠️ obrigatório
  > Technical field identifying the changed lock date
  > Opções: `fiscalyear_lock_date` (Global Lock Date), `tax_lock_date` (Tax Return Lock Date), `sale_lock_date` (Sales Lock Date), `purchase_lock_date` (Purchase Lock Date)

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `active` **(boolean)** — Active
- `reason` **(char)** — Reason
- `end_datetime` **(datetime)** — End Date
- `lock_date` **(date)** — Changed Lock Date
  > Technical field giving the date the lock date was changed to.
- `company_lock_date` **(date)** — Original Lock Date
  > Technical field giving the date the company lock date at the time the exception was created.
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_id` **(many2one)** — User → `res.users`

## Campos Calculados (readonly)

- `state` **(selection)** — State 🔒 readonly
  > Opções: `active` (Active), `revoked` (Revoked), `expired` (Expired)
- `fiscalyear_lock_date` **(date)** — Global Lock Date 🔒 readonly
  > The date the Global Lock Date is set to by this exception. If the lock date is not changed it is set to the maximal date.
- `tax_lock_date` **(date)** — Tax Return Lock Date 🔒 readonly
  > The date the Tax Lock Date is set to by this exception. If the lock date is not changed it is set to the maximal date.
- `sale_lock_date` **(date)** — Sales Lock Date 🔒 readonly
  > The date the Sale Lock Date is set to by this exception. If the lock date is not changed it is set to the maximal date.
- `purchase_lock_date` **(date)** — Purchase Lock Date 🔒 readonly
  > The date the Purchase Lock Date is set to by this exception. If the lock date is not changed it is set to the maximal date.
