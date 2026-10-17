# Agent skills

Portable skills for coding agents, maintained by [amrable](https://github.com/amrable).

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

## socratic-code-mentor

A learning-by-building mentor skill by
[ogzhanolguncu](https://github.com/ogzhanolguncu). You implement the learning
exercise's core logic while the agent guides you and handles supporting work.

### Install

```sh
npx skills add amrable/agent-skills --skill socratic-code-mentor
```

To install globally for Codex:

```sh
npx skills add amrable/agent-skills --skill socratic-code-mentor --agent codex --global
```

Invoke `$socratic-code-mentor` in Codex or `/socratic-code-mentor` in Claude Code.
Unlike `mental`, the imported skill also allows automatic activation for learning
requests, according to its description.

See [the instructions](skills/socratic-code-mentor/SKILL.md) and
[source attribution and license status](skills/socratic-code-mentor/SOURCE.md).

## License

Original material is MIT licensed; see [LICENSE](LICENSE). The imported
`socratic-code-mentor` skill is excluded: its source gist provides no explicit
license. See its [source notice](skills/socratic-code-mentor/SOURCE.md).
