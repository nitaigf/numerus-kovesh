# Numerus Kovesh

Repositorio de governanca e orquestracao do ecossistema Numerus Kovesh.

Este repositorio nao contem o codigo-fonte principal de API/Web diretamente.
Ele referencia dois projetos independentes e centraliza contratos, regras e operacao conjunta.

## Repositorios filhos

- API: `nitaigf/numerus-kovesh-api`
- Web: `nitaigf/numerus-kovesh-web`

## Estrutura

```text
.
├── numerus-kovesh-api/        # submodulo
├── numerus-kovesh-web/        # submodulo
├── contracts/                 # contratos API <-> Web
├── docs/                      # documentacao operacional compartilhada
├── .github/workflows/         # CI do superprojeto
├── docker-compose.yml         # orquestracao local dos dois sistemas
├── Makefile                   # atalhos para compose e operacao
└── README.md
```

## Submodulos

Objetivo:

- branch `main` do pai usa filhos em `main`
- branch `develop` do pai usa filhos em `develop`

Configuracao recomendada em `.gitmodules`:

```ini
[submodule "numerus-kovesh-api"]
	path = numerus-kovesh-api
	url = git@github.com:nitaigf/numerus-kovesh-api.git
	branch = .
[submodule "numerus-kovesh-web"]
	path = numerus-kovesh-web
	url = git@github.com:nitaigf/numerus-kovesh-web.git
	branch = .
```

Comandos uteis:

```bash
git submodule sync --recursive
git submodule update --init --recursive
git submodule update --remote --recursive
```

## Operacao local

Subir stack completa:

```bash
make up
```

Parar stack:

```bash
make down
```

Logs:

```bash
make logs
```

## Contratos

A pasta `contracts/` define:

- `http-contract.md`: endpoint, versionamento e semantica de erro
- `environment-contract.md`: variaveis e portas esperadas entre sistemas
- `release-compatibility.md`: matriz de compatibilidade e checks minimos

Mudancas de contrato devem ser acompanhadas por:

- atualizacao de testes nos repositorios filhos
- atualizacao da documentacao relevante
- versionamento apropriado quando houver breaking change
