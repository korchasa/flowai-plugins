# flowai-plugins

Generated Claude Code + Codex plugin marketplace for the [AssistFlow](https://github.com/korchasa/flowai) framework.

**This repository is a generated mirror.** Every generated file on `main` is produced by CI in [`korchasa/flowai`](https://github.com/korchasa/flowai) on each `framework-v*` release. Do not edit generated files by hand; only `README.md` and `LICENSE` are maintained directly here.

## Install in Claude Code

```shell
/plugin marketplace add korchasa/flowai-plugins
/plugin install flowai-core@flowai-plugins
/reload-plugins
```

Optional packs:

```shell
/plugin install flowai-deno@flowai-plugins
/plugin install flowai-typescript@flowai-plugins
/plugin install flowai-engineering@flowai-plugins
/plugin install flowai-devtools@flowai-plugins
/plugin install flowai-memex@flowai-plugins
/reload-plugins
```

## Install in Codex

```shell
codex plugin marketplace add korchasa/flowai-plugins
```

Then open Codex `/plugins` and install `flowai-core` or any other pack you use.

Codex hook execution is feature-gated. Enable `[features].plugin_hooks = true` in Codex before relying on plugin hooks from packs that ship hooks.

## Packs

The marketplace currently publishes all framework packs:

- `flowai-core` — base commands and skills: commit, plan, review, init, update, maintenance, and related workflow primitives.
- `flowai-deno` — Deno command, deployment, and project command setup skills.
- `flowai-devtools` — skill, command, agent, rule, hook, and benchmark authoring tools.
- `flowai-engineering` — engineering knowledge workflows: deep research, fixing tests, diagrams, product docs, prompts, and GitHub ticket work.
- `flowai-memex` — long-term project memory skills: save sources, answer from memory, audit the bank.
- `flowai-typescript` — TypeScript strict-mode and Deno code-style setup skills.

Skills are invoked under the plugin namespace, e.g. `/flowai-core:commit`, `/flowai-core:plan`, `/flowai-core:review`, `/flowai-engineering:deep-research`, `/flowai-memex:memex-save`. The `flowai-` prefix is stripped from skill and command directory names during build to avoid `/flowai-core:flowai-commit`-style double prefixes.

## Generated Layout

- `.claude-plugin/marketplace.json` — Claude Code marketplace catalog.
- `.agents/plugins/marketplace.json` — Codex marketplace catalog.
- `plugins/flowai-<pack>/.claude-plugin/plugin.json` — Claude Code plugin manifest.
- `plugins/flowai-<pack>/.codex-plugin/plugin.json` — Codex plugin manifest.
- `plugins/flowai-<pack>/skills/<name>/SKILL.md` — shared skill payload for commands and skills; commands carry `disable-model-invocation: true`.
- `plugins/flowai-<pack>/agents/<name>.md` — Claude Code agents. Codex manifests do not declare agents because current Codex plugin support does not define an agents component.
- `plugins/flowai-<pack>/hooks/hooks.json` — generated only for packs that ship hooks.

## CLI Compatibility

The plugin marketplace is an alternative distribution channel to the [`flowai` CLI](https://github.com/korchasa/flowai-cli). Do not install the same pack into the same IDE and project through both channels; pick either plugins or `flowai sync`.

## Security

Claude Code and Codex plugins execute code at your user privilege. Only install marketplaces and plugins from sources you trust. The generated contents of this repository come from public source: [`korchasa/flowai`](https://github.com/korchasa/flowai) (`framework/<pack>/`) and the build pipeline at [`scripts/build-plugins.ts`](https://github.com/korchasa/flowai/blob/main/scripts/build-plugins.ts).

## Issues and Contributions

File issues and pull requests against the source repository: <https://github.com/korchasa/flowai>. This repository accepts direct changes only for `README.md`, `LICENSE`, or marketplace infrastructure.

## License

MIT — see [`LICENSE`](./LICENSE).
