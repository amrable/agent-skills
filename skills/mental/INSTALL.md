# Install mental

Copy this entire `mental` folder, including `references` and `agents`, to a skill
directory recognized by your agent. The source folder in this repository is a
portable artifact; it is not automatically discovered from `skills/mental`.

| Agent | Suggested destination | Explicit invocation |
| --- | --- | --- |
| Codex | `~/.codex/skills/mental/` | `$mental explain npm distribution` |
| Claude Code | `~/.claude/skills/mental/` | `/mental explain npm distribution` |
| Cursor | `.cursor/skills/mental/` in your project | `/mental explain npm distribution` |
| GitHub Copilot | `.github/skills/mental/` in your project | Explicitly ask to use the `mental` skill; invocation UI varies by surface |
| Gemini CLI | `~/.gemini/skills/mental/` | Explicitly ask to use the `mental` skill |

For example, from this repository, install for Claude Code:

```sh
mkdir -p ~/.claude/skills
cp -R skills/mental ~/.claude/skills/
```

Reload or start a new agent session if the skill does not appear. Avoid installing
duplicate copies of the same skill into multiple locations searched by one agent.

## Portability and invocation limits

The core is ordinary Markdown with Agent Skills `name` and `description`
frontmatter. It requires no plugins, shell execution, external services, or
model-specific tools. Mermaid is the default output; D2 rendering is optional.

`disable-model-invocation: true` is a Claude Code and Cursor extension that
enforces manual activation. Codex uses the included
`agents/openai.yaml` policy `allow_implicit_invocation: false`.

Other agents may ignore these settings. The description and instructions also
require an explicit user request, but instruction-based gating is not equivalent
to host-enforced invocation control. There is no universal guarantee of the exact
`/mental` spelling, manual-only enforcement, or diagram rendering across agents.
For strict loaders that reject unknown frontmatter, remove only the
`disable-model-invocation` line from their installed copy and use that host's
manual-invocation controls if available. Agents without skills support can read
`SKILL.md` and its reference file when the user explicitly requests it.

The format and locations were checked against the documentation below; this is
not a claim that the skill has been run in every agent.

- [Agent Skills format](https://agentskills.io/specification)
- [Claude Code skills](https://code.claude.com/docs/en/skills)
- [Cursor skills](https://cursor.com/docs/skills)
- [GitHub Copilot skills](https://docs.github.com/en/copilot/concepts/agents/about-agent-skills)
- [Gemini CLI skills](https://geminicli.com/docs/cli/skills/)

## Try it

Use the invocation form your agent supports with any of these prompts:

```text
/mental take me from node cli.js to someone running my package with npx
/mental how does clicking Save travel from the frontend to the database?
/mental server A calls server B for pricing; show the actors and replies
/mental why add a queue and worker for slow exports?
```

Check that the response starts from a small working setup, introduces components
for a reason, traces a concrete interaction, and includes labeled Mermaid arrows
or a rendered D2 image. Asking an ordinary coding question without invoking the
skill should not activate it.
