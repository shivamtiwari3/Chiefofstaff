# Claude EA — Your Personal Executive Assistant + Second Brain

A ready-to-clone Claude Code workspace that turns Claude into your personal EA. It knows who you are, what you're building, who's on your team, and what's due — so you don't have to re-explain context every session.

## What it does

- **Session startup briefing** — Claude reads your priorities, memory, and calendar cadence and gives you a 5-line status brief every time you open a session
- **Content drafting** — LinkedIn posts, Instagram adaptations, all in your voice
- **Sprint tracking** — pulls GitHub project boards and surfaces blockers
- **Decision log** — append-only log so you never lose "why we did this"
- **Skills** — reusable workflows (draft post, sprint summary, etc.) that get smarter over time
- **Memory** — Claude remembers what happened last session and builds on it

## Who this is for

Founders, PMs, and builders who:
- Run multiple parallel workstreams (day job + side project + content + admin)
- Want an assistant that already knows their context, not one they have to onboard every session
- Post content consistently and want help drafting in their voice
- Track work across GitHub projects

---

## Setup (5 minutes)

### 1. Clone the repo

```bash
git clone https://github.com/YOUR_USERNAME/claude-ea.git my-ea
cd my-ea
```

### 2. Open in Claude Code

```bash
claude .
```

### 3. Run setup

In the Claude Code chat, type:

```
start
```

Claude will ask you ~10 questions and write your context directly into the repo. This takes about 5 minutes and only needs to happen once.

### 4. Keep context fresh

- **Weekly:** Update `context/current-priorities.md` when your sprint changes
- **Per session:** Claude auto-reads memory and priorities on startup
- **As needed:** Say "remember that I always want X" to save preferences permanently

---

## Repo Structure

```
├── CLAUDE.md                    # Main EA instructions (Claude reads this)
├── CLAUDE.local.md              # Your local overrides — gitignored
├── .claude/
│   ├── HEARTBEAT.md             # Auto-runs on session open
│   ├── FEEDBACK-LOG.md          # Content style corrections
│   ├── settings.json            # Permissions
│   ├── rules/
│   │   ├── content-style.md     # Your content voice + formulas
│   │   └── communication-style.md
│   └── skills/
│       ├── setup/               # First-time onboarding wizard
│       ├── draft-linkedin-post/
│       └── sprint-summary/
├── context/
│   ├── me.md                    # Who you are
│   ├── work.md                  # Your workstreams
│   ├── team.md                  # Your team
│   ├── current-priorities.md    # This week's priorities
│   └── goals.md                 # Quarterly goals
├── decisions/log.md             # Append-only decision log
├── memory/                      # Session logs (gitignored except template)
│   └── template.md
├── projects/                    # Per-project subdirs
├── references/                  # SOPs + examples
├── archives/
└── templates/
```

---

## Skills

Run skills with `/skill-name` or just describe what you want:

| Skill | How to trigger |
|-------|---------------|
| `setup` | `start` or `/setup` — first-time onboarding |
| `draft-linkedin-post` | "draft a post about X" or `/draft-linkedin-post` |
| `sprint-summary` | "sprint status" or `/sprint-summary` |

Add your own skills in `.claude/skills/your-skill/SKILL.md`.

---

## Content workflow

The EA supports a 3x/week LinkedIn posting cadence with day-specific formats:
- **Tue** — "I Built It" (what you shipped this week)
- **Wed** — "I Taught It" (insight from teaching/working with others)
- **Fri** — "I Noticed" (personal observation + the pattern it reveals)

Your voice, formulas, and style live in `.claude/rules/content-style.md`. Edit it to match how you actually write.

---

## GitHub board integration

The EA can pull from GitHub Projects boards to summarize sprint status. After setup, configure your board IDs in `context/work.md`.

Requires `gh` CLI authenticated: `gh auth login`

---

## Keeping it sharp over time

- Log decisions: `decisions/log.md` (append-only)
- End-of-session: Ask Claude to save a session log to `memory/YYYY-MM-DD.md`
- Content corrections: `.claude/FEEDBACK-LOG.md` (Claude checks this before drafting)
- Build new skills when a workflow repeats 3+ times

---

## License

MIT — fork it, adapt it, make it yours.
