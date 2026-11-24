# Skills

A collection of skills that I use when writing code.

[![skills.sh](https://skills.sh/b/aaronasachimp/skills)](https://skills.sh/aaronasachimp/skills)

## Available skills

### [porting-code](./skills/porting-code/SKILL.md)

Port code from one programming language to another. Creates an outline of key functionality, identifies library equivalents, ports unit tests, then iterates on the ported code until tests pass.

Includes language-specific references:
- [Python guidelines](./skills/porting-code/references/python.md)
- [TypeScript guidelines](./skills/porting-code/references/typescript.md)

### [video](./skills/video/SKILL.md)

Guide for creating compelling videos from concept through final render. Walks through preflight checklist, audience definition, outlining, scripting, content gathering, editing, and wrap-up.

### [focus](./skills/project-focus/SKILL.md)

Helps bring projects to completion with structured project planning. Creates a `PROJECT-PLAN.md` with prioritized tasks, deadlines, and milestones accounting for realistic capacity.

### [brainstorm](./skills/brainstorm/SKILL.md)

Use when trying to solve big problems, think through issues, or come up with ideas. Guides through problem definition, constraints, stakeholders, assumptions, requirement prioritization, and solution evaluation.

### [app-dev](./skills/app-dev/SKILL.md)

Playbook for building maintainable applications. Covers version control habits (anchoring comments), logging for debuggability, and other long-term maintainability considerations.

### [eli5](./skills/eli5/SKILL.md)

Explains any concept at a 5th grade reading level using metaphors, diagrams, and sensory language. Use when you ask to "explain like I'm five" or "dumb this down".

### [immaculate-vibes](./skills/immaculate-vibes/SKILL.md)

Reviews a vibe-coded application against quality pillars (security, reliability, performance, UI/UX, accessibility) and produces a go/no-go report with recommendations.

### [project-griller](./skills/project-griller/SKILL.md)

Grills you on your project one question at a time to uncover hidden dependencies, hidden complexity, and vague requirements, driving toward a shared understanding.

### [sst-system-architect](./skills/sst-system-architect/SKILL.md)

Plans serverless infrastructure with SST. Applies YAGNI, least privilege, alarm-fatigue-aware monitoring, and cost-effective backups; only deploys when you explicitly ask.

### [sublime-text](./skills/sublime-text/SKILL.md)

Customizes and extends Sublime Text — writing Python plugins, editing settings and keymaps, and installing or overriding packages — via the `subl` CLI and package files.

### [typescript-cleanup](./skills/typescript-cleanup/SKILL.md)

Cleans up TypeScript issues in a codebase for a less experienced developer. Fixes the 10 most impactful issues per batch (syntax errors and bugs first), with confirmations between batches.

## Installation

```sh
npx skills add aaronasachimp/skills
```

Or install individual skills:

```sh
npx skills add aaronasachimp/skills --skill porting-code
npx skills add aaronasachimp/skills --skill video
npx skills add aaronasachimp/skills --skill focus
npx skills add aaronasachimp/skills --skill brainstorm
npx skills add aaronasachimp/skills --skill app-dev
npx skills add aaronasachimp/skills --skill eli5
npx skills add aaronasachimp/skills --skill immaculate-vibes
npx skills add aaronasachimp/skills --skill project-griller
npx skills add aaronasachimp/skills --skill sst-system-architect
npx skills add aaronasachimp/skills --skill sublime-text
npx skills add aaronasachimp/skills --skill typescript-cleanup
```

## Usage

Skills activate automatically when the agent detects relevant tasks. You can also invoke them directly:

- "Port this Python script to TypeScript"
- "Help me create a video about..."
- "I need a project plan to finish this work"
- "Explain this concept like I'm five"
- "Review my vibe-coded app and tell me if it's ship-ready"
- "Plan the SST infrastructure for this service"
- "Clean up the TypeScript issues in this codebase"
