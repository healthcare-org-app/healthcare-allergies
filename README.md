# allergies-service

allergies-service — domain: ehr

- **Port:** 8305
- **Language:** Python 3.11 + Flask
- **Database:** `ehr` (Postgres, table `allergies`)
- **Event bus:** Kafka

## API

| Method    | Path                       |
|-----------|----------------------------|
| GET       | `/api/allergies/`          |
| POST      | `/api/allergies/`          |
| GET       | `/api/allergies/<id>`      |
| PUT/PATCH | `/api/allergies/<id>`      |
| DELETE    | `/api/allergies/<id>`      |
| GET       | `/health`                  |
| GET       | `/ready`                   |

## Events

**Publishes:** (none)
**Subscribes:** (none)

## HTTP peer dependencies

- `patients-service`
- `drug-interactions-service`
- `audit-log-service`

## Local dev

```bash
pip install -e ../../libs/py-healthcare-common
pip install -r requirements.txt
cp .env.example .env
(cd ../../infra && docker compose up -d postgres kafka kafka-init)
python -m app.main
```

## Tests

```bash
pytest
```
