# CLAUDE.md Template — Dynamis

> Copie este arquivo para `~/.claude/CLAUDE.md` e personalize com seus dados.

## Quem Sou

- **Nome:** [Seu nome]
- **Cargo:** [Dev / Designer / PM]
- **Equipe:** Dynamis Family

## Projetos

| Projeto | Repo |
|---------|------|
| Dynamis Hub | Dynamis-Educacao/hub |
| Dynamis Website | Dynamis-Educacao/website |
| Dynamis LMS | Dynamis-Educacao/portal |

## Comunicacao

- **Lingua:** Portugues BR para tudo. Termos tecnicos em ingles OK.
- **Estilo:** Direto, sem enrolacao. Respostas curtas e objetivas.

## Stack Padrao

| Camada | Tecnologia |
|--------|-----------|
| Framework | Next.js 14 (App Router) |
| Linguagem | TypeScript strict (sem `any`) |
| Styling | Tailwind CSS + ShadCN/UI |
| Database | SQLite + Drizzle ORM |
| AI | Gemini, OpenRouter, Anthropic |

## Regras de Codigo

- TypeScript strict — sem `any`, usar `unknown` quando necessario
- Imports absolutos com alias `@/`
- Server Components por padrao, Client so quando necessario
- Tailwind para styling (sem CSS modules)
- Conventional Commits: feat:, fix:, docs:, chore:, refactor:
- NUNCA commitar .env, credentials, API keys
- Quando terminar codigo, roda build/lint pra garantir que funciona

## Modo de Trabalho

- Git: commit so quando eu pedir. Nunca push sem confirmacao.
- Se travar, tenta alternativa antes de perguntar.
