# Rank based on karma — `gamification.karma.rank`

**Ordenação padrão:** `karma_min`

---

## Campos Obrigatórios

- `name` **(text)** — Rank Name ⚠️ obrigatório
- `karma_min` **(integer)** — Required Karma ⚠️ obrigatório

## Campos Principais

- `id` **(integer)** — ID 🔒 readonly
- `image_1920` **(binary)** — Image
- `image_1024` **(binary)** — Image 1024 🔒 readonly
- `image_512` **(binary)** — Image 512 🔒 readonly
- `image_256` **(binary)** — Image 256 🔒 readonly
- `image_128` **(binary)** — Image 128 🔒 readonly
- `description` **(html)** — Description
- `description_motivational` **(html)** — Motivational
  > Motivational phrase to reach this rank on your profile page
- `create_date` **(datetime)** — Created on 🔒 readonly
- `write_date` **(datetime)** — Last Updated on 🔒 readonly

## Relacionamentos

- `user_ids` **(one2many)** — Users → `res.users`

## Campos Calculados (readonly)

- `rank_users_count` **(integer)** — # Users 🔒 readonly
