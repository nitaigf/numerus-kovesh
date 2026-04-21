Você é um engenheiro de software sênior especializado em arquitetura de sistemas modernos, FastAPI, SolidJS e organização de monorepos com Git Flow.

Seu objetivo é criar um projeto completo, público no GitHub, seguindo o mesmo padrão do projeto astro-kovesh, porém agora para NUMEROLOGIA PITAGÓRICA.

---

# 🎯 OBJETIVO DO PROJETO

Criar um sistema web composto por:

1. API (FastAPI)
2. Frontend (SolidJS)
3. Repositório pai (monorepo organizador)

O sistema deve:

- Receber um texto (nome de pessoa, empresa ou qualquer string)
- Converter esse texto em números usando numerologia pitagórica
- Retornar:
  - valor de cada letra
  - soma total
  - número reduzido final
  - identificação de número mestre (11, 22, 33)
  - significado básico do número final (curto, sem interpretação profunda)

⚠️ NÃO incluir interpretação avançada nesta versão.

---

# 🔢 REGRAS DE NEGÓCIO (ESSENCIAL)

## Tabela Pitagórica (OBRIGATÓRIO)

A conversão deve seguir:

1 = A, J, S  
2 = B, K, T  
3 = C, L, U  
4 = D, M, V  
5 = E, N, W  
6 = F, O, X  
7 = G, P, Y  
8 = H, Q, Z  
9 = I, R  

Essa tabela é a base do sistema :contentReference[oaicite:0]{index=0}

---

## Regras de normalização

- Remover acentos (UTF-8 → ASCII)
- Remover espaços
- Ignorar caracteres especiais
- Converter para uppercase

Exemplo:
"Nitai Embrás" → "NITAIEMBRAS"

---

## Cálculo

1. Converter cada letra em número
2. Somar todos os valores
3. Reduzir até:
   - 1–9
   - OU 11, 22, 33 (não reduzir)

Exemplo:
NITAI → 5 + 9 + 2 + 1 + 9 = 26 → 2 + 6 = 8

---

## Significados básicos

Mapear:

1 → Liderança  
2 → Cooperação  
3 → Comunicação  
4 → Estrutura  
5 → Liberdade  
6 → Responsabilidade  
7 → Espiritualidade  
8 → Poder  
9 → Humanitarismo  

11 → Intuição  
22 → Mestre construtor  
33 → Mestre professor  

---

# 🏗️ ARQUITETURA DO PROJETO

Criar 3 repositórios:

## 1. numerus-kovesh (PARENT)

Estrutura:

/numerus-kovesh
  README.md
  docker-compose.yml (opcional)
  docs/
  .github/workflows/

Submódulos git:

- numerus-kovesh-api
- numerus-kovesh-web

---

## 2. numerus-kovesh-api (FastAPI)

Estrutura:

/app
  main.py
  routers/
    numerology.py
  services/
    numerology_service.py
  utils/
    normalize.py
  constants/
    mapping.py
    meanings.py
  schemas/
    numerology_schema.py

---

## 3. numerus-kovesh-web (SolidJS)

- Interface simples, bonita e responsiva
- Campo de entrada
- Botão calcular
- Exibição do resultado

---

# 🔌 API - ESPECIFICAÇÃO

## Endpoint

POST /numerology

Request:

{
  "text": "Nitai Embras"
}

Response:

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

---

## Funções obrigatórias

- normalize_text(text)
- map_letters(text)
- calculate_sum(values)
- reduce_number(number)
- get_meaning(number)

---

# 🎨 FRONTEND (SolidJS)

## Tela única

Componentes:

- Input de texto
- Botão "Calcular"
- Área de resultado

## Exibição

- Número final em destaque (grande)
- Lista de letras e valores
- Soma total
- Redução

---

## Estilo visual (IMPORTANTE)

- Tema místico / esotérico
- Gradiente escuro (roxo, azul, preto)
- Glow no número final
- Fonte elegante
- Animação leve ao calcular

---

# 🌌 DIFERENCIAL VISUAL

- Background procedural (gerado dinamicamente)
- Efeito de partículas ou estrelas
- Glassmorphism no container principal

---

# ⚙️ GIT FLOW (OBRIGATÓRIO)

Implementar Git Flow em TODOS os repositórios:

Branches:

- main → produção
- develop → integração
- feature/*
- release/*
- hotfix/*

---

## Fluxo esperado:

1. Criar feature branch
2. Merge em develop
3. Criar release
4. Merge em main

---

# 🚀 DEPLOY

- Frontend: Vercel
- API: Vercel (serverless FastAPI) OU alternativa simples
- Sem banco de dados
- Stateless

---

# 📦 QUALIDADE DE CÓDIGO

- Tipagem (Python + TS)
- Código modular
- Separação clara de responsabilidades
- Fácil de migrar para Go no futuro

---

# 🔮 PREPARAÇÃO PARA FUTURO

O código deve permitir expansão para:

- Número da alma (vogais)
- Número da personalidade (consoantes)
- Nome completo vs nome social
- API unificada com astrologia

---

# 📄 README (OBRIGATÓRIO)

Cada repo deve conter:

- descrição do projeto
- como rodar localmente
- como fazer deploy
- exemplos de uso da API

---

# 🎯 RESULTADO ESPERADO

Gerar:

1. Estrutura completa dos 3 repositórios
2. Código funcional da API
3. Código funcional do frontend
4. Configuração de Git Flow
5. README completos

---

# ⚠️ RESTRIÇÕES

- Não usar banco de dados
- Não usar autenticação
- Não usar cache
- Foco total na lógica e UX

---

# 💡 IMPORTANTE

O projeto deve ser simples, elegante, modular e pronto para evoluir.

Pense como um produto que será reaproveitado futuramente como motor simbólico maior (numerologia + astrologia + outros sistemas).
