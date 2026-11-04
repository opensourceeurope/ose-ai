# ose-ai — Agent Instructions

This repository is the [Open Source Europe](https://github.com/opensourceeurope) Claude Code **plugin marketplace**: a single catalog (`.claude-plugin/marketplace.json`) that lists OSE plugins whose code lives in their own repositories. There is no application code here — only the catalog and its docs.

## Authorship Rules

- **NEVER add `Co-Authored-By:` with yourself (an agent) as a co-author of any commit.** Agents are assistants and tools — they are not authors. Only humans can be authors of commits.
- AI assistance disclosure belongs in the pull request description using the exact format below — not in commit authorship metadata:
  ```
  Generated-by: <Agent Name and Version> following [AI Policy](https://github.com/opensourceeurope/.github/blob/main/AI-POLICY.md)
  ```

## Commit Conventions

- Use conventional commits: `feat:`, `fix:`, `docs:`, `ci:`, `chore:`.
- This project is MIT-licensed — do not introduce incompatibly licensed material.

## Editing the catalog

- Each plugin entry uses a `git-subdir` source pointing at the plugin's own repo and subdirectory. Do **not** vendor plugin code into this repo.
- **Do not add a `version` field to marketplace entries.** Each plugin's version is the single source of truth in its own `plugin.json`; a version here would silently mask it.
- The marketplace `name` is `ose-ai` and must stay **unique across all OSE repos** — no other repo's `marketplace.json` may claim the same name, or Claude Code can only register one of them at a time (adding the second collides with the first).
- **Two catalogs.** `.claude-plugin/marketplace.json` is for Claude Code. `.agents/plugins/marketplace.json` is for OpenAI Codex. Add a plugin to the Codex catalog only when its directory has a root `plugin.json` and `mcp.json` in the Agent Plugins format. Codex entries need a full `https://` Git URL, `policy.installation`, `policy.authentication`, and `category`.
