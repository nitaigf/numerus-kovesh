# Environment Contract - API <-> Web

## API

- Porta local padrao: `8010`
- URL local padrao: `http://localhost:8010`

Variaveis esperadas:

- `APP_NAME`
- `APP_ENV`
- `APP_HOST`
- `APP_PORT`
- `FRONTEND_URL`
- `CORS_ORIGINS`

## Web

- Porta local padrao: `5173`
- URL local padrao: `http://localhost:5173`

Variaveis esperadas:

- `VITE_API_BASE_URL`

## Compose local

- O servico `web` consome a API via `http://api:8010` dentro da rede Docker.
- Fora do Docker, o frontend deve apontar para `http://localhost:8010`.