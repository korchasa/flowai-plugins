# flowai-plugins

Generated [Claude Code plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces) for the [AssistFlow](https://github.com/korchasa/flowai) framework.

**This repository is a generated mirror.** Every commit on `main` is produced by CI in [`korchasa/flowai`](https://github.com/korchasa/flowai) on each `framework-v*` release. Do not edit files by hand outside `README.md` and `LICENSE` — they will be overwritten on the next release.

## Install in Claude Code

```shell
/plugin marketplace add korchasa/flowai-plugins
/plugin install flowai-core@flowai-plugins
/reload-plugins
```

Skills are invoked under the plugin namespace, e.g. `/flowai-core:commit`, `/flowai-core:plan`, `/flowai-core:review`. The `flowai-` prefix is stripped from skill / command directory names during build to avoid `/flowai-core:flowai-commit`-style double prefix.

## What's in the marketplace

Pilot scope (this repository): `flowai-core` only. Remaining packs (`devtools`, `engineering`, `deno`, `typescript`, `memex`) continue to ship via the [`flowai` CLI](https://github.com/korchasa/flowai-cli). Multi-pack rollout will land in subsequent framework releases.

Plugin layout per pack:

- `.claude-plugin/plugin.json` — manifest. `version` omitted; the git commit SHA of this repository is the version key, so one framework release maps to exactly one plugin update.
- `skills/<name>/SKILL.md` — both agent-invocable skills and user-only commands (commands carry `disable-model-invocation: true`).
- `agents/<name>.md` — subagents with Claude-native frontmatter.
- `hooks/hooks.json` — only when the pack ships hooks (not present in `flowai-core`).

## Security

Claude Code plugins execute arbitrary code at your user privilege. Only install marketplaces and plugins from sources you trust. The contents of this repository are produced verbatim from public, auditable source: see [`korchasa/flowai`](https://github.com/korchasa/flowai) (`framework/<pack>/`) and the build pipeline at [`scripts/build-claude-plugins.ts`](https://github.com/korchasa/flowai/blob/main/scripts/build-claude-plugins.ts).

## Issues and contributions

File issues and pull requests against the source repository: <https://github.com/korchasa/flowai>. This repository accepts no direct contributions other than infrastructure changes to `README.md` / `LICENSE`.

## License

MIT — see [`LICENSE`](./LICENSE).
