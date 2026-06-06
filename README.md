# gh-copilot-plugin-token-minimizing

This repo provides ways to reduce the number of tokens used when using the GitHub Copilot plugin in IDEs (e.g. VSCode or WebStorm).

## Caveman

Caveman's original description:
> A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill/plugin and Codex plugin that makes agent talk like caveman — cutting **~75% of output tokens** while keeping full technical accuracy. Now with 文言文 mode( wenyan-mode), [...] that cuts **~46% of input tokens** every session.

> Based on the viral observation that caveman-speak dramatically reduces LLM token usage without losing technical substance. [...]

Credit goes to [Julius Brussee](https://github.com/JuliusBrussee) and all contributors to the original project. Made usable for GitHub Copilot by [Mijutra](https://github.com/Mijutra/caveman-copilot) by simply providing all necessary information in the `copilot-instructions.md` file.

If you want to use it simply copy-paste the `# caveman` section of the `.gihub/copilot-instructions.md` into your own and switch to your desired mode via chat e.g. `/caveman ultra`.

