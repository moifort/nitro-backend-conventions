# Nitro Backend Conventions

TypeScript backend conventions for any AI coding tool that supports the [Agent Skills open format](https://agentskills.io/home) — domain-driven structure, branded types, Zod validation, namespaces, and error handling for Nitro/H3.

This skill distills practical Nitro/H3 backend patterns into actionable, concise references for agents and code review workflows.

## Who this is for
- Teams building TypeScript backends with Nitro/H3 who want consistent, type-safe conventions
- Developers structuring domain-driven server-side code with branded types and Zod validation
- Anyone shipping production Nitro APIs with clean error handling, middleware, and business logic

## How to Use This Skill

### Option A: Using skills.sh (recommended)

Install this skill with a single command:

```bash
npx skills add https://github.com/moifort/nitro-backend-conventions --skill nitro-backend
```

For more information, [visit the skills.sh platform page](https://skills.sh/moifort/nitro-backend-conventions/nitro-backend).

Then use the skill in your AI agent, for example:

> Use the nitro backend skill and create a new domain module with branded types and Zod validation

### Option B: Claude Code Plugin

#### Personal Usage

To install this Skill for your personal use in Claude Code:

1. Add the marketplace:

```bash
/plugin marketplace add moifort/nitro-backend-conventions
```

2. Install the Skill:

```bash
/plugin install nitro-backend-conventions@nitro-backend
```

#### Project Configuration

To automatically provide this Skill to everyone working in a repository, configure the repository's `.claude/settings.json`:

```json
{
  "enabledPlugins": {
    "nitro-backend-conventions@nitro-backend": true
  },
  "extraKnownMarketplaces": {
    "nitro-backend-conventions": {
      "source": {
        "source": "github",
        "repo": "moifort/nitro-backend-conventions"
      }
    }
  }
}
```

When team members open the project, Claude Code will prompt them to install the Skill.

### Option C: Manual install

1. **Clone** this repository.
2. **Install or symlink** the `skills/nitro-backend/` folder following your tool's official skills installation docs (see links below).
3. **Use your AI tool** as usual and ask it to use the "nitro-backend" skill for backend tasks.

#### Where to Save Skills

Follow your tool's official documentation, here are a few popular ones:
- **Codex:** [Where to save skills](https://developers.openai.com/codex/skills/#where-to-save-skills)
- **Claude:** [Using Skills](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview#using-skills)
- **Cursor:** [Enabling Skills](https://cursor.com/docs/context/skills#enabling-skills)

## What This Skill Covers

### Domain Structure
- Organize code by business domain (`server/domain/<name>/`)
- Clear file conventions: `types.ts`, `primitives.ts`, `index.ts`, routes

### Branded Types
- Type-safe identifiers with `ts-brand` (no mixing `UserId` with `OrderId`)
- Constructor patterns and type extraction

### Zod Validation
- Reusable validators in `primitives.ts`
- Branded type integration with Zod schemas

### Business Namespaces
- TypeScript namespaces for grouping business logic
- Pure functions, storage access, and error handling patterns

### Error Handling
- Business errors as string literals (`as const`)
- `ts-pattern` for exhaustive error matching in routes
- HTTP error mapping, system error propagation

### Routes & Middleware
- Routes as minimal orchestrators (validate, call business logic, respond)
- Middleware, plugins, and runtime config patterns

## Tech Stack

- **Nitro** (H3) — Server framework
- **TypeScript** (strict mode) — Language
- **Bun** — Runtime
- **Biome** — Linter/formatter
- **ts-brand** — Branded types
- **ts-pattern** — Pattern matching
- **Zod** — Schema validation

## Skill Structure

```text
skills/
  nitro-backend/
    SKILL.md — Full conventions reference (domain structure, branded types, validation, namespaces, error handling, routes, config, principles)
```

## License

This skill is open-source and available under the MIT License.
