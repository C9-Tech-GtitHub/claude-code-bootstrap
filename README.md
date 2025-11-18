# Claude Code Bootstrap

Set up Claude Code for any project in minutes - choose between Quick Setup or Detailed Planning.

## 🚀 Quick Start (Claude Code Users)

Open Claude Code and paste this entire message:

```
Hello! I'm making a new project.

If I don't already have a project folder, create one for me.

Then install the Claude Code Bootstrap by running:
curl -s https://raw.githubusercontent.com/C9-Tech-GtitHub/claude-code-bootstrap/main/claude-bootstrap-installer.sh | bash

After installation completes, run the project-bootstrap agent to set up my project.
```

That's it! Claude Code will handle everything automatically.

## Alternative: Terminal Install

```bash
cd your-project
bash <(curl -s https://raw.githubusercontent.com/C9-Tech-GtitHub/claude-code-bootstrap/main/claude-bootstrap-installer.sh)
```

## ⚡ What's New in v2.0

**Two Setup Modes:**
- **Quick Setup** (2 minutes) - Auto-detects tech stack, asks minimal questions, smart defaults
- **Detailed Planning** (8 minutes) - Comprehensive customization, perfect for teams

**Existing Project Support:**
- Detects current CLAUDE.md configuration
- Offers to update, add specialists, or start fresh
- Never loses your existing setup

**Smart Auto-Detection:**
- Scans package.json, requirements.txt, docker-compose.yml
- Detects frameworks, databases, deployment platforms
- Identifies testing tools and CI/CD setup

## 🎯 Choose Your Mode

### ⚡ Quick Setup Mode (Recommended for most projects)

**Perfect for:**
- Getting started fast
- Solo projects or small teams
- Standard tech stacks
- MVPs and prototypes

**What happens:**
1. Auto-detects your tech stack from project files
2. Asks 2 quick questions (project purpose + AI needs)
3. Generates optimized configuration with smart defaults
4. Complete in ~2 minutes

**Example:**
```
🔍 Analyzing your project...

✅ Detected:
   - Framework: Next.js 14 + TypeScript
   - Database: Supabase (from .env)
   - UI: Tailwind CSS + shadcn/ui
   - Deployment: Vercel

📋 Quick questions:
1. What does this project do?
2. Will you need AI integration?

Creating configuration... ✅ Done!
```

### 🎯 Detailed Planning Mode

**Perfect for:**
- Production applications
- Team projects
- Complex architectures
- Enterprise/compliance needs

**What happens:**
1. Phase 1: Project basics (3 questions)
2. Phase 2: Tech stack (comprehensive options)
3. Phase 3: Testing & workflow
4. Phase 4: Special requirements
5. Custom configuration tailored exactly to your needs
6. Complete in ~8 minutes

## 🔄 Works with Existing Projects

Already have CLAUDE.md? No problem! The bootstrap agent offers:

1. **Update** - Refresh existing config with new best practices
2. **Add** - Keep current setup, add new specialists
3. **Regenerate** - Backup current, create fresh
4. **Cancel** - Keep everything as-is

## 📦 What Gets Generated

### Always Created:
- **CLAUDE.md** - Main configuration file
- **general-assistant** - Day-to-day development

### Auto-Included Based on Tech Stack:

| Subagent | When Included | Tools |
|----------|---------------|-------|
| database-specialist | Database detected/selected | Supabase MCP, SQL, etc. |
| playwright-tester | E2E testing (Playwright) | Playwright MCP |
| deployment-specialist | Deployment platform | Platform-specific CLIs |
| ai-integration-specialist | AI integration | OpenAI, Anthropic |
| project-planner | Complex/enterprise projects | Plan mode |

## 🎓 Examples

### Quick Setup: Next.js SaaS
```
⚡ Quick Setup (2 minutes)

Auto-detected:
✅ Next.js + TypeScript + Supabase + Vercel

Generated:
- general-assistant
- database-specialist (Supabase MCP)
- deployment-specialist (Vercel)
```

### Detailed Planning: Enterprise App
```
🎯 Detailed Planning (8 minutes)

Custom configuration for:
- Complex microservices architecture
- 15-person development team
- SOC2 compliance requirements
- Real-time features

Generated:
- general-assistant
- database-specialist (compliance-focused)
- playwright-tester
- deployment-specialist (GitHub Actions)
- ai-integration-specialist
- project-planner (architecture + compliance)
```

## 💡 Key Features

**Smart Auto-Detection:**
- Reads package.json, requirements.txt, go.mod, Gemfile
- Scans docker-compose.yml for services
- Checks .env files for database/API keys
- Detects CI/CD from .github/workflows/, .gitlab-ci.yml

**Minimal & Focused:**
- Only creates subagents you actually need
- No bloat or unnecessary complexity
- Can always add more specialists later

**Team-Ready:**
- Commit .claude/ to git
- Team members get same setup on clone
- Consistent development experience

**Production-Ready:**
- Best practices built-in
- Security considerations included
- Platform-specific optimizations

## 📚 Learn More

- [Full Documentation](bootstrap/README.md)
- [Subagents Guide](https://code.claude.com/docs/en/sub-agents)
- [Claude Code Docs](https://code.claude.com/docs)

## 🆘 Quick Reference

**Install:**
```bash
bash <(curl -s https://raw.githubusercontent.com/C9-Tech-GtitHub/claude-code-bootstrap/main/claude-bootstrap-installer.sh)
```

**Run Bootstrap:**
```
> Use the project-bootstrap agent to set up this project
```

**Choose Mode:**
- Quick Setup: 2 minutes, auto-detection
- Detailed Planning: 8 minutes, full customization

**Commit:**
```bash
git add CLAUDE.md .claude/
git commit -m "feat: Add Claude Code configuration"
```

**Update Later:**
```
> Use the project-bootstrap agent to set up this project
[Choose: Update existing configuration]
```

---

**Version 2.0** - Now with Quick Setup mode and existing project detection!
