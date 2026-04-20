# cc-plugins

One marketplace, all of my Claude Code plugins.

**Add it once:**

```
/plugin marketplace add iamtouchskyer/cc-plugins
```

Then browse and install anything from the catalog below with `/plugin install <name>`.

---

## Catalog

| Plugin | Category | What it does |
|---|---|---|
| [`memex`](https://github.com/iamtouchskyer/memex) | memory | Zettelkasten persistent memory for AI coding agents. Markdown + git sync, no vector DB. |
| [`logex`](https://github.com/iamtouchskyer/logex) | content | Turn Claude Code session transcripts into blog-style articles — narrative, not logs. |
| [`opc`](https://github.com/iamtouchskyer/opc) | orchestration | One Person Company — a full team in a single skill. Adaptive agent orchestrator. |
| [`opc-extensions`](https://github.com/iamtouchskyer/opc-extensions) | orchestration | Extension skills and flow templates for OPC. |
| [`dreamworks`](https://github.com/iamtouchskyer/dreamworks-plugin) | product | Full AI product pipeline — ideafactory, pitch, publish, orchestrator. |
| [`repo-advisors`](https://github.com/iamtouchskyer/repo-advisors) | knowledge | Distilled architecture advisors for popular repos. |
| [`ink-flow`](https://github.com/iamtouchskyer/ink-flow) | content | Full-lifecycle content operations — write, review, publish, distribute. |
| [`cli-x`](https://github.com/iamtouchskyer/cli-x) | integration | Universal external platform interface. MCP > CLI/API > Playwright. |
| [`cli-x-builder`](https://github.com/iamtouchskyer/cli-x-builder) | integration | Designer companion to cli-x — adds new platform adapters. |
| [`session-recap`](https://github.com/iamtouchskyer/session-recap) | content | Generate a visual session recap infographic. |
| [`tooleval`](https://github.com/iamtouchskyer/tooleval) | quality | Evaluate MCP server quality with automated checks. |

---

## One install path — don't double-add

Each plugin also has its own `.claude-plugin/marketplace.json` in its own repo, so historically you could run:

```
/plugin marketplace add iamtouchskyer/memex
/plugin install memex
```

That still works and stays supported for backward compatibility.

**But pick one path.** If you add both this `cc-plugins` marketplace *and* an individual plugin's marketplace, Claude Code will show the same plugin listed twice (once as `memex@cc-plugins`, once as `memex@memex`). Installing both just wastes disk and slows startup.

**Recommendation for new machines / new users: just add `cc-plugins` and forget the individual ones.**

---

## Why a meta marketplace?

- **One command on a new machine** instead of eleven.
- **One source of truth** when I ship a new plugin — add an entry here, done.
- **Easier for others to discover** the whole collection instead of stumbling on plugins one at a time.

Per-plugin marketplaces stay because some of them are referenced in existing docs and blog posts. They are not going away.

---

## Versioning

Entries in this marketplace **don't pin versions**. Each plugin's own `plugin.json` is the version source of truth — we just point at `ref: main`. This avoids version drift between this repo and the plugin repos.

If you need a specific version of a plugin, install it from its own marketplace with a ref pin.

---

## Source health

A weekly GitHub Actions job (`.github/workflows/check-sources.yml`) runs `git ls-remote` against every plugin's source repo. If any becomes unreachable, renamed, or archived, the workflow fails — that's the signal to update `marketplace.json`.

---

## License

MIT. Each individual plugin has its own license — check the linked repo.
