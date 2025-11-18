# Claude Code Bootstrap System

## 🚀 Quick Start

The bootstrap system now supports **two modes** and **existing project detection**:

### Step 1: Invoke the Bootstrap Agent

```
> Use the project-bootstrap agent to set up this project
```

### Step 2: Choose Your Mode

The agent will detect if you have existing configuration and offer:

**For New Projects:**
- ⚡ **Quick Setup** (2 minutes) - Smart defaults, minimal questions
- 🎯 **Detailed Planning** (8 minutes) - Full customization

**For Existing Projects:**
- 🔄 Update existing configuration
- ➕ Add new subagents
- 🗑️ Start fresh with backup
- ✋ Keep current setup

## ⚡ Quick Setup Mode

**Perfect for:**
- Getting started fast
- Solo projects
- Prototypes and MVPs
- When you trust smart defaults

**What happens:**
1. 🔍 Auto-detects tech stack from your project files
2. 📋 Asks only 2 questions (project purpose + AI needs)
3. ✅ Generates configuration with smart defaults
4. ⏱️ Complete in ~2 minutes

**Auto-detection includes:**
- Framework (Next.js, React, Vue, Django, etc.)
- Database (from env vars, docker-compose)
- UI libraries (from package.json)
- Deployment platform (Vercel, Netlify, etc.)
- Testing tools (Playwright, Jest, etc.)

## 🎯 Detailed Planning Mode

**Perfect for:**
- Production applications
- Team projects
- Complex architectures
- When you need full control

**What happens:**
1. 📋 Phase 1: Project basics (3 questions)
2. 📋 Phase 2: Tech stack (comprehensive options)
3. 📋 Phase 3: Testing & workflow (detailed)
4. 📋 Phase 4: Special requirements
5. ✅ Custom configuration tailored exactly to your needs
6. ⏱️ Complete in ~8 minutes

## 🔄 Existing Project Updates

**The agent checks for:**
- Existing CLAUDE.md
- Current subagents in .claude/agents/
- Your current tech stack

**Update options:**
1. **Refresh** - Update existing config with new best practices
2. **Add** - Keep current setup, add new specialists
3. **Regenerate** - Backup current, create fresh (with your original answers)
4. **Cancel** - Keep everything as-is

## 🎯 What Gets Generated

### Always Created:
- **CLAUDE.md** - Main configuration file
- **general-assistant** - Day-to-day development

### Conditionally Created (based on tech stack):

| Subagent | When Included | Tools |
|----------|---------------|-------|
| database-specialist | Any database detected/selected | Database-specific (Supabase MCP, SQL, etc.) |
| playwright-tester | E2E testing with Playwright | Playwright MCP |
| cypress-tester | E2E testing with Cypress | Bash, Read |
| deployment-specialist | Deployment platform selected | Bash, Read (platform CLIs) |
| ai-integration-specialist | AI integration (OpenAI, Anthropic) | Read, Edit, Write |
| project-planner | Complex/enterprise projects | Read, Grep, Glob (plan mode) |

## 📚 Quick Setup Examples

### Example 1: Auto-Detected Next.js + Supabase
```
🔍 Analyzing your project...

✅ Detected:
   - Framework: Next.js 14 + TypeScript
   - Database: Supabase (from SUPABASE_URL in .env)
   - UI: Tailwind CSS + shadcn/ui
   - Deployment: Vercel (from vercel.json)

📋 Quick questions:
1. What does this project do?
   > A task management SaaS app

2. AI integration?
   > Yes - OpenAI

Creating configuration...
✅ Done! (2 minutes)

Generated:
- general-assistant
- database-specialist (Supabase MCP)
- deployment-specialist (Vercel)
- ai-integration-specialist (OpenAI GPT-5)
```

### Example 2: Python Django Project
```
🔍 Analyzing your project...

✅ Detected:
   - Framework: Django 5.0 (Python 3.12)
   - Database: PostgreSQL (from DATABASE_URL)
   - Testing: pytest
   - Deployment: Docker (from docker-compose.yml)

📋 Quick questions:
1. What does this project do?
   > REST API for mobile app backend

2. AI integration?
   > No

Creating configuration...
✅ Done! (2 minutes)

Generated:
- general-assistant
- database-specialist (PostgreSQL)
- deployment-specialist (Docker)
```

## 📚 Detailed Planning Examples

### Example: Enterprise SaaS
```
🎯 Detailed Planning Mode

📋 Phase 1/4: Project Basics
[3 questions about purpose, problem, users]

📋 Phase 2/4: Technology Stack
Framework: Next.js 14 + TypeScript
Database: Supabase
UI: shadcn/ui
AI: OpenAI GPT-5
Deployment: Vercel + GitHub Actions

📋 Phase 3/4: Testing & Workflow
Testing: Playwright (E2E) + Jest (unit)
Git: Feature branches + PR reviews
Deployment: Auto-deploy on merge
CI/CD: GitHub Actions

📋 Phase 4/4: Special Requirements
Complexity: Complex (microservices)
Team: Medium (10 developers)
Requirements: SOC2 compliance, real-time features

Generating comprehensive setup...
✅ Done! (8 minutes)

Generated 6 subagents:
- general-assistant
- database-specialist (Supabase MCP + compliance)
- playwright-tester (token-optimized)
- deployment-specialist (Vercel + GitHub Actions)
- ai-integration-specialist (OpenAI + rate limiting)
- project-planner (architecture + compliance)
```

## 💡 Tips

### Choosing Your Mode

**Use Quick Setup when:**
- ✅ You have standard tech stack
- ✅ You trust auto-detection
- ✅ You want to start coding ASAP
- ✅ Solo or small team

**Use Detailed Planning when:**
- ✅ Complex architecture
- ✅ Team project with specific needs
- ✅ Enterprise/compliance requirements
- ✅ You need full control

### After Setup

**Quick Setup users:**
- Review auto-detected config in CLAUDE.md
- Add team conventions if needed
- You can always add specialists later

**Detailed Planning users:**
- Check setup-log.md for full documentation
- Share with team for review
- Customize subagent prompts if needed

## 🔄 Re-running Bootstrap

### Update Existing Config
```
> Use the project-bootstrap agent to set up this project

🔍 Found existing configuration!
Choose option 1: Update existing

[Agent reads current config, asks what changed]
```

### Add New Specialist
```
> Use the project-bootstrap agent to set up this project

🔍 Found existing configuration!
Choose option 2: Add new subagents

Which specialist would you like to add?
[ ] playwright-tester
[ ] ai-integration-specialist
[ ] project-planner
```

### Start Fresh
```
> Use the project-bootstrap agent to set up this project

🔍 Found existing configuration!
Choose option 3: Start fresh

[Backs up to CLAUDE.md.backup, .claude/agents.backup]
[Runs full setup again]
```

## 📖 Learn More

- [Subagents Docs](https://code.claude.com/docs/en/sub-agents)
- [Claude Code Docs](https://code.claude.com/docs)
- [MCP Servers](https://code.claude.com/docs/en/mcp)

---

**Installed with claude-bootstrap-installer.sh**
