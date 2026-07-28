# ose-ai

The [Open Source Europe](https://github.com/opensourceeurope) Claude Code plugin marketplace — a single catalog listing the OSE plugins. Each plugin's code lives in its own repository; this repo just points at them.

## Plugins

| Plugin | What it does | Source |
|---|---|---|
| `ose-knowledge` | An `ose-researcher` agent backed by the public OSE docs MCP server. | [ose-knowledge-mcp](https://github.com/opensourceeurope/ose-knowledge-mcp) |
| `oc-platform-api` | Read-only Open Collective GraphQL: the `mcp-for-ocp-graphql` MCP server plus querying + local-export skills and an analyst agent. | [mcp-for-ocp-graphql](https://github.com/opensourceeurope/mcp-for-ocp-graphql) |

## Use it

In Claude Code:

```
/plugin marketplace add opensourceeurope/ose-ai
/plugin install ose-knowledge@ose-ai
/plugin install oc-platform-api@ose-ai
```

Pull in newer plugin versions with `/plugin marketplace update ose-ai`.

## How it's wired

This repo holds only the catalog (`.claude-plugin/marketplace.json`). Each entry uses a `git-subdir` source that points at the plugin's own repo and subdirectory, so plugin code, issues, and releases stay where they belong. Plugin versions come from each plugin's own `plugin.json` — never duplicated here.

## AI use

Contributions to this repo may be AI-assisted under the OSE [AI Policy](https://github.com/opensourceeurope/.github/blob/main/AI-POLICY.md). See [AGENTS.md](AGENTS.md) for the rules agents must follow.

## License

[MIT](LICENSE) © Open Source Europe.
