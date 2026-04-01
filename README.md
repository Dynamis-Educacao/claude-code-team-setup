# Claude Code Team Setup — Dynamis

Setup do Claude Code para a equipe Dynamis. Clone este repo e rode o instalador para ter o mesmo ambiente AI que usamos em todos os projetos.

## O que e o Claude Code?

Claude Code e a ferramenta CLI da Anthropic que coloca o Claude AI direto no seu terminal ou VS Code. Pensa nele como um dev senior sentado do seu lado que le codigo, escreve codigo, roda comandos e usa ferramentas externas — tudo por conversa.

## O que tem neste pacote?

| Pasta | O que e | Qtd |
|-------|---------|-----|
| `skills/` | Workflows inteligentes que ativam automaticamente ou sob demanda | 40+ |
| `commands/` | Slash commands que voce invoca com `/nome-do-comando` | 29 |
| `hooks/` | Scripts que rodam automaticamente em eventos do Claude Code | 6 |
| `agents/` | Definicoes de agentes (code reviewer, etc.) | 1 |
| `lib/` | Scripts utilitarios usados pelas skills | 1 |

---

## Pre-requisitos

1. **Node.js 20+** — `node -v`
2. **Git** — `git --version`
3. **GitHub CLI** — `brew install gh` (Mac) ou `sudo apt install gh` (Linux)
4. **Claude Code** — `npm install -g @anthropic-ai/claude-code`

Se nao tem nada disso, siga o guia completo em [ONBOARDING.md](ONBOARDING.md).

---

## Instalacao

### Passo 1: Clonar este repo

```bash
gh repo clone Dynamis-Educacao/claude-code-team-setup
cd claude-code-team-setup
```

### Passo 2: Rodar o instalador

```bash
chmod +x install.sh
./install.sh
```

Isso copia skills, commands, hooks, agents e lib para `~/.claude/`.

### Passo 3: Instalar plugins (dentro do Claude Code)

Abra o Claude Code no terminal e rode:

```
/install-plugin superpowers@claude-plugins-official
/install-plugin context7@claude-plugins-official
/install-plugin claude-mem@thedotmack
/install-plugin code-review@claude-plugins-official
/install-plugin frontend-design@claude-plugins-official
```

### Passo 4: Clonar o Hub

```bash
cd ~/code
gh repo clone Dynamis-Educacao/hub dynamis-hub
cd dynamis-hub
npm install
npm run dev
```

Abra `http://localhost:3000` — a tela de login deve aparecer.

---

## Credenciais do Hub

| Nome | Email | Senha |
|------|-------|-------|
| Diogo | diogo@dynamisfamily.com.br | dynamis-diogo-2026 |
| Bruno | bruno@dynamisfamily.com.br | dynamis-bruno-2026 |
| Yuri | yuri@dynamisfamily.com.br | dynamis-yuri-2026 |
| Juan | juan@dynamisfamily.com.br | dynamis-juan-2026 |

---

## Usando o Claude Code

```bash
# Abrir no projeto
cd ~/code/dynamis-hub
claude

# Exemplos de pedidos
"crie um componente de card para alunos"
"corrija o bug na pagina de login"
"explique como funciona o sistema de agentes"
```

### Comandos uteis

| Comando | O que faz |
|---------|-----------|
| `/help` | Ajuda geral |
| `/commit` | Cria commit com mensagem automatica |
| `/review` | Code review do codigo |
| `/plan` | Cria plano de implementacao |
| `Ctrl+C` | Cancela acao atual |
| `/clear` | Limpa contexto |

---

## Projetos Dynamis

| Projeto | Repo | URL |
|---------|------|-----|
| Hub (interno) | Dynamis-Educacao/hub | hub.dynamisfamily.com |
| Website | Dynamis-Educacao/website | dynamisfamily.com.br |
| LMS (Portal) | Dynamis-Educacao/portal | portal.dynamiseducacao.com.br |
| Mobile App | Dynamis-Educacao/mobile-app | — |

---

## Duvidas?

- Pagina de onboarding completa: `hub.dynamisfamily.com/reports/onboarding-dev.html`
- Fala com o Juan no Telegram
- Abre o Claude Code e pergunta — ele conhece todo o projeto
