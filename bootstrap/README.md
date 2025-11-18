# Claude Code Bootstrap System

> **Quickly set up new projects with optimized CLAUDE.md and subagent configuration**

This bootstrap system creates a tailored Claude Code setup for any new project based on your tech stack and requirements.

## 🚀 Quick Start (New Project Setup)

### Step 1: Copy Bootstrap Files to Your New Project

```bash
# From this repo, copy the bootstrap system
cp -r .claude/agents/project-bootstrap.md YOUR_NEW_PROJECT/.claude/agents/
cp -r .claude/bootstrap YOUR_NEW_PROJECT/.claude/

# Navigate to your new project
cd YOUR_NEW_PROJECT
```

### Step 2: Invoke the Bootstrap Agent

Open Claude Code in your new project and run:

```
> Use the project-bootstrap agent to set up this project
```

### Step 3: Answer Interview Questions

The bootstrap agent will ask you about:
- Project description and purpose
- Technology stack (framework, database, UI library)
- Testing needs (E2E, unit tests)
- Deployment platform
- AI integration requirements
- Git workflow preferences

### Step 4: Review Generated Files

The agent will create:
- `CLAUDE.md` - Main configuration file
- `.claude/agents/*.md` - Subagents tailored to your stack
- `.claude/bootstrap/setup-log.md` - Documentation of what was created

### Step 5: Customize and Commit

```bash
# Review the generated files
cat CLAUDE.md
ls .claude/agents/

# Customize if needed
code CLAUDE.md

# Commit to git
git add CLAUDE.md .claude/
git commit -m "feat: Add Claude Code configuration"
```

## 🎯 What Gets Generated

The bootstrap agent intelligently creates only what you need:

### Always Included:
- ✅ `CLAUDE.md` - Main project configuration
- ✅ `general-assistant` - For day-to-day development

### Conditional (based on your stack):

**Database:**
- Supabase → `database-specialist` with Supabase MCP tools
- PostgreSQL/MySQL → `database-specialist` with SQL patterns
- MongoDB → `database-specialist` with MongoDB patterns

**Testing:**
- Playwright → `playwright-tester` with token optimization
- Cypress → `cypress-tester` with Cypress patterns

**Deployment:**
- Vercel/Netlify → `deployment-specialist` with platform CLI
- AWS → `deployment-specialist` with AWS patterns
- Docker → `deployment-specialist` with Docker commands

**AI Integration:**
- OpenAI → `ai-integration-specialist` with GPT-5 guidance
- Anthropic → `ai-integration-specialist` with Claude API

**Planning:**
- Complex projects → `project-planner` for architecture decisions

## 📋 Example Tech Stack Setups

### Next.js + Supabase + Vercel (like this project)
```
Generated:
✅ general-assistant
✅ database-specialist (Supabase MCP)
✅ playwright-tester
✅ deployment-specialist (Vercel)
✅ ai-integration-specialist (OpenAI)
✅ project-planner
```

### Simple React App (no backend)
```
Generated:
✅ general-assistant
✅ deployment-specialist (Netlify)
```

### Python Django + PostgreSQL
```
Generated:
✅ general-assistant
✅ database-specialist (PostgreSQL)
✅ deployment-specialist (AWS/Heroku)
```

### Node.js API + MongoDB
```
Generated:
✅ general-assistant
✅ database-specialist (MongoDB)
✅ deployment-specialist (Docker)
```

## 🛠️ Customization

After generation, you can:

1. **Edit CLAUDE.md** - Add project-specific guidelines
2. **Modify subagents** - Adjust tools, prompts, permissions
3. **Add new subagents** - Create additional specialists
4. **Remove subagents** - Delete files you don't need

## 📁 File Structure

```
your-project/
├── CLAUDE.md                          # Main configuration
├── .claude/
│   ├── agents/
│   │   ├── project-bootstrap.md      # Bootstrap agent (for future use)
│   │   ├── general-assistant.md      # Generated
│   │   ├── database-specialist.md    # Generated (if database)
│   │   ├── playwright-tester.md      # Generated (if testing)
│   │   ├── deployment-specialist.md  # Generated (if deployment)
│   │   ├── ai-integration-specialist.md  # Generated (if AI)
│   │   └── project-planner.md        # Generated (if complex)
│   └── bootstrap/
│       ├── README.md                 # This file
│       ├── TEMPLATE-CLAUDE.md        # Template used for generation
│       ├── templates/                # Agent templates
│       └── setup-log.md             # Generated - what was created
```

## 🔄 Re-running Bootstrap

If you want to regenerate configuration:

```bash
# Backup current config
mv CLAUDE.md CLAUDE.md.backup
mv .claude/agents .claude/agents.backup

# Re-run bootstrap
> Use the project-bootstrap agent to set up this project

# Compare and merge if needed
diff CLAUDE.md CLAUDE.md.backup
```

## 🎓 Best Practices

### 1. Start Minimal
Don't add subagents you don't need yet. You can always add more later.

### 2. Customize for Your Team
After generation, add team-specific:
- Code conventions
- Review processes
- Deployment procedures
- Testing requirements

### 3. Keep in Git
Commit `.claude/` directory so your team gets the same setup.

### 4. Update as Project Evolves
Re-run bootstrap or manually update when:
- Adding new technologies
- Changing deployment platforms
- Adopting new tools

### 5. Document Decisions
Use `.claude/bootstrap/setup-log.md` to record:
- Why certain subagents were chosen
- Tech stack decisions
- Custom configurations

## 💡 Tips

**For Solo Projects:**
- Keep it simple - maybe just `general-assistant` and `deployment-specialist`
- Add specialists as needs arise

**For Team Projects:**
- Include comprehensive CLAUDE.md with team conventions
- Document all workflows clearly
- Use more specialized subagents for consistency

**For Client Projects:**
- Include deployment automation
- Add thorough testing setup
- Document everything for handoff

## 🆘 Troubleshooting

**Bootstrap agent doesn't respond:**
- Make sure you're in the project root
- Check that `project-bootstrap.md` exists in `.claude/agents/`
- Try explicit invocation: "Use the project-bootstrap agent"

**Generated config doesn't fit:**
- You can re-run bootstrap with different answers
- Manually edit CLAUDE.md and subagent files
- Delete unwanted subagents

**Missing tools/MCPs:**
- Update subagent `tools:` list in frontmatter
- Check that MCPs are installed in Claude Code settings

## 📚 Learn More

- [Subagents Documentation](https://code.claude.com/docs/en/sub-agents)
- [Agent Skills](https://code.claude.com/docs/en/skills)
- [Claude Code Docs](https://code.claude.com/docs)

## 🤝 Contributing

Found a better template? Have a tech stack we should support? 

Add templates to `.claude/bootstrap/templates/` and update the bootstrap agent logic!

---

**Happy bootstrapping!** 🎉

Start your next project with a fully configured Claude Code setup in minutes, not hours.
