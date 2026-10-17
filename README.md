# Skills for Understanding

Coding agent skills that help you understand the software you work with.

See how the pieces fit together. Follow a request across services. Build a small
version yourself to learn why it works. This collection focuses on mental models,
clear explanations, and learning through practice.

## Pick a way to learn

| What you need | Skill | What it does |
| --- | --- | --- |
| “Show me the big picture.” | [mental](skills/mental/SKILL.md) | Maps actors and communication with diagrams, from the simplest setup to the system you have now. |
| “Help me learn by building it.” | [coach](skills/coach/SKILL.md) | Guides a learning project while you write the core logic and the agent handles supporting work. |

## What belongs here

Each skill should help you explain how something works, trace an interaction, or
build understanding through practice. A useful result is something you can reason
about yourself: a diagram you can walk through, a flow you can follow, or a small
implementation you understand.

Maintained by [amrable](https://github.com/amrable). Skills use portable
`SKILL.md` instructions; invocation syntax and enforcement vary by coding agent.

## mental

Step back from implementation details and understand the actors, boundaries, and
communication in a system. Start with the simplest working setup, then introduce
new components as the need for them appears.

Every explanation includes a Mermaid diagram or a rendered D2 image. Examples
cover npm distribution, frontend/backend requests, service-to-service calls, and
background jobs.

### Install

```sh
npx skills add amrable/agent-skills --skill mental
```

To install across projects for specific agents:

```sh
npx skills add amrable/agent-skills --skill mental --agent codex claude-code --global
```

### Use

Claude Code and Cursor:

```text
/mental take me from a local Node script to someone running my package with npx
```

Codex:

```text
$mental show how clicking Save travels from the frontend to the database
```

Other agents: explicitly ask to use the `mental` skill. Invocation syntax and
manual-only enforcement depend on the agent. This skill includes explicit-only
settings for Codex, Claude Code, and Cursor; other agents also receive an explicit
invocation requirement in its instructions.

See [installation and compatibility](skills/mental/INSTALL.md), the
[skill instructions](skills/mental/SKILL.md), and
[examples](skills/mental/references/examples.md).

## coach

A learning-by-building mentor skill by
[ogzhanolguncu](https://github.com/ogzhanolguncu). You implement the learning
exercise's core logic while the agent guides you and handles supporting work.

### Install

```sh
npx skills add amrable/agent-skills --skill coach
```

To install globally for Codex:

```sh
npx skills add amrable/agent-skills --skill coach --agent codex --global
```

Invoke `$coach` in Codex or `/coach` in Claude Code.
Unlike `mental`, the imported skill also allows automatic activation for learning
requests, according to its description.

See [the instructions](skills/coach/SKILL.md) and
[source attribution and license status](skills/coach/SOURCE.md).

## License

Original material is MIT licensed; see [LICENSE](LICENSE). The imported
`coach` skill is excluded: its source gist provides no explicit
license. See its [source notice](skills/coach/SOURCE.md).
