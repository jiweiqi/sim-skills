# sim-skills is archived

This repository is no longer the live source for sim agent skills.

The sim ecosystem now uses one package-owned model:

- Shared runtime skills live in [`svd-ai-lab/sim-cli`](https://github.com/svd-ai-lab/sim-cli), bundled with `sim-cli-core`.
- Solver-specific skills live in the matching `svd-ai-lab/sim-plugin-<solver>` repository and package.
- Agents sync installed skills from the active uv project with:

```bash
uv add sim-cli-core <plugin-package-spec>
uv run sim plugin sync-skills --target .agents/skills --copy
uv run sim check <solver>
uv run sim plugin doctor <solver> --deep
```

For available solver packages, see the plugin index:

- [`svd-ai-lab/sim-plugin-index`](https://github.com/svd-ai-lab/sim-plugin-index)
- [`docs.svdailab.com/plugin-index`](https://docs.svdailab.com/plugin-index/)

Do not add new skills here. This repository remains only for historical
reference until a maintainer archives it on GitHub.
