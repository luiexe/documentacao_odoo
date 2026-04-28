# Import Module — `base.import.module`

**Ordenação padrão:** `id`

---

## Campos Obrigatórios

- `module_file` **(binary)** — Module .ZIP file ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `state` **(selection)** — Status 🔒 readonly
  > Opções: `init` (init), `done` (done)
- `import_message` **(text)** — Import Message
- `force` **(boolean)** — Force init
  > Force init mode even if installed. (will update `noupdate='1'` records)
- `with_demo` **(boolean)** — Import demo data of module
- `modules_dependencies` **(text)** — Modules Dependencies
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly
