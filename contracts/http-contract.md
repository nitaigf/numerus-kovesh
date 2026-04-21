# HTTP Contract - API <-> Web

## Base

- API base URL definida externamente no frontend por `VITE_API_BASE_URL`
- Todos os endpoints consumidos pelo frontend sao versionados em `/v1/*`

## Endpoint principal

### `POST /v1/numerology`

Body JSON esperado:

```json
{
  "text": "Nitai Embras"
}
```

Resposta de sucesso:

```json
{
  "input": "Nitai Embras",
  "normalized": "NITAIEMBRAS",
  "letters": [
    { "char": "N", "value": 5 },
    { "char": "I", "value": 9 }
  ],
  "sum": 52,
  "reduced": 7,
  "is_master": false,
  "meaning": "Espiritualidade"
}
```

## Semantica de erro

Formato minimo esperado:

```json
{
  "detail": {
    "code": "string",
    "message": "string"
  }
}
```

Codigos relevantes para o frontend:

- `422`: validacao semantica/estrutura
- `500`: erro interno inesperado

Codigos `detail.code` relevantes:

- `invalid_input_text`

## Regras de evolucao

- Mudancas breaking exigem nova versao de endpoint ou plano de migracao.
- Mudancas aditivas sao permitidas sem quebrar clientes.
- Remocao ou renomeacao de campos deve ser previamente comunicada e versionada.