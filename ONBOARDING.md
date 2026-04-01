# Onboarding Completo — Dynamis Dev Team

Guia passo a passo para configurar seu ambiente de desenvolvimento do zero.

---

## 1. Ferramentas Base

### Node.js (v20+)

**Mac:**
```bash
curl -fsSL https://fnm.vercel.app/install | bash
source ~/.zshrc
fnm install 20
fnm use 20
node -v  # deve mostrar v20.x
```

**Linux (Ubuntu):**
```bash
curl -fsSL https://fnm.vercel.app/install | bash
source ~/.bashrc
fnm install 20
fnm use 20
```

### Git

**Mac:** Ja vem instalado. Verificar: `git --version`

**Linux:**
```bash
sudo apt update && sudo apt install git -y
```

**Configurar nome e email:**
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
```

### GitHub CLI

**Mac:**
```bash
brew install gh
```

**Linux:**
```bash
sudo apt install gh -y
```

**Autenticar:**
```bash
gh auth login
# Escolher: GitHub.com → HTTPS → Login with browser
```

---

## 2. Editor de Codigo

### VS Code (recomendado)

**Mac:** Baixar em [code.visualstudio.com](https://code.visualstudio.com/)

**Extensoes recomendadas:**
- ES7+ React/Redux/React-Native snippets
- Tailwind CSS IntelliSense
- Prettier - Code formatter
- GitLens
- Claude Code (Anthropic)

---

## 3. Claude Code

### Instalar

```bash
npm install -g @anthropic-ai/claude-code
```

### Primeiro uso

```bash
claude
# Vai abrir o browser para login na Anthropic
# Siga as instrucoes para autenticar
```

### Instalar skills da equipe

```bash
cd ~/code
gh repo clone Dynamis-Educacao/claude-code-team-setup
cd claude-code-team-setup
chmod +x install.sh
./install.sh
```

### Instalar plugins

Dentro do Claude Code:
```
/install-plugin superpowers@claude-plugins-official
/install-plugin context7@claude-plugins-official
/install-plugin claude-mem@thedotmack
/install-plugin code-review@claude-plugins-official
/install-plugin frontend-design@claude-plugins-official
```

---

## 4. Clonar os Projetos

```bash
mkdir -p ~/code/dynamis
cd ~/code/dynamis

# Hub (principal)
gh repo clone Dynamis-Educacao/hub
cd hub
npm install
npm run dev
# Testar: abrir http://localhost:3000

# Website
cd ~/code/dynamis
gh repo clone Dynamis-Educacao/website

# Portal (LMS)
gh repo clone Dynamis-Educacao/portal
```

---

## 5. Git — Como Trabalhar

### Fluxo basico

```bash
# 1. Sempre comece atualizado
git pull origin main

# 2. Crie uma branch
git checkout -b feat/nome-da-feature

# 3. Faca suas mudancas e commite
git add .
git commit -m "feat: descricao do que voce fez"

# 4. Push para o GitHub
git push -u origin feat/nome-da-feature

# 5. Crie um Pull Request
gh pr create --title "feat: descricao" --body "O que mudou"
```

### Regras

- **NUNCA** commitar .env, API keys ou senhas
- **NUNCA** fazer `git push --force` na main
- **SEMPRE** fazer Pull Request — nunca push direto na main
- Prefixos de commit: `feat:`, `fix:`, `refactor:`, `docs:`, `chore:`

---

## 6. Stack Dynamis

| Camada | Tecnologia |
|--------|-----------|
| Framework | Next.js 14 (App Router) |
| Linguagem | TypeScript (strict) |
| Styling | Tailwind CSS + ShadCN/UI |
| Database | SQLite + Drizzle ORM |
| AI | Gemini, OpenRouter, Anthropic |
| Deploy | VPS + PM2 + GitHub Actions |

---

## 7. Links Uteis

| O que | Onde |
|-------|-----|
| Hub | hub.dynamisfamily.com |
| Website | dynamisfamily.com.br |
| LMS | portal.dynamiseducacao.com.br |
| GitHub Org | github.com/Dynamis-Educacao |
| Onboarding visual | hub.dynamisfamily.com/reports/onboarding-dev.html |

---

## Duvidas?

Abre o Claude Code no projeto e pergunta. Ele conhece toda a codebase e pode te ajudar com qualquer coisa.

```bash
cd ~/code/dynamis/hub
claude
# "como funciona o sistema de agentes?"
# "me explica a estrutura do projeto"
# "crie uma pagina nova de exemplo"
```
