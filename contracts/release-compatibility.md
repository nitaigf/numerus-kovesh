# Release Compatibility

## Baseline inicial

| Parent | API | Web | Status |
| --- | --- | --- | --- |
| 0.1.x | 0.1.x | 0.1.x | compativel |

## Checks minimos para release

- `api-ci` verde
- `web-ci` verde
- `parent-ci` verde
- contrato HTTP atualizado quando houver mudanca de payload
- smoke local com API e Web integrados