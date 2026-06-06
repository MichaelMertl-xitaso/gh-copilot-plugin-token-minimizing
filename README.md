# gh-copilot-plugin-token-minimizing

This repo provides ways to reduce the number of tokens used when using the GitHub Copilot plugin in IDEs (e.g. VSCode or WebStorm).

## Caveman

Caveman's original description:
> A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill/plugin and Codex plugin that makes agent talk like caveman — cutting **~75% of output tokens** while keeping full technical accuracy. Now with 文言文 mode( wenyan-mode), [...] that cuts **~46% of input tokens** every session.

> Based on the viral observation that caveman-speak dramatically reduces LLM token usage without losing technical substance. [...]

Credit goes to [Julius Brussee](https://github.com/JuliusBrussee) and all contributors to the original project. Made usable for GitHub Copilot by [Mijutra](https://github.com/Mijutra/caveman-copilot) by simply providing all necessary information in the `copilot-instructions.md` file.

If you want to use it simply copy-paste the `# caveman` section of the `.gihub/copilot-instructions.md` into your own and switch to your desired mode via chat e.g. `/caveman ultra`.

## RTK - Rust Token Killer

RTK's original description:
> Your AI agent is drowning in CLI noise. Fix it. RTK compresses command outputs before they reach the context window. Better reasoning. Longer sessions. Lower costs.

> See [reasons](https://www.rtk-ai.app/#problem) and [repo](https://github.com/rtk-ai/rtk) for more information.

To install it for your GitHub Copilot first you need to get the `.exe` for your operation system, see [Downloads](https://github.com/rtk-ai/rtk/releases) and put it under `C:\Program Files\rtk`. Also add this exact path to your system variables `Path`.

After this is done simply run `rtk init -g --copilot` in the desired project to set it up. This will generate an entrance for it in your `copilot-instructions.md` and it will also create the `rtk-rewrite.json` hook (can both be seen in this repo to check if it worked or to copy-paste it).

Use `rtk gain` to see statistics of its effects.

## More direct Tools will come in the future...

## General Tips
- [GitHub Copilot Token Optimization Guide by Muhammad Haseeb Akram](https://medium.com/@haseeb-dev/github-copilot-token-optimization-guide-5a32ec9465ea) - some points:
    - use scoped, selection-based prompts because broad questions cause copilot to search the full repo
    - prefer inline suggestions ([code completion billing](https://docs.github.com/en/copilot/reference/copilot-billing/models-and-pricing)) over chat
    - be careful what is attached to your chat window
    - use the [correct model](https://docs.github.com/de/copilot/reference/ai-models/model-comparison) for the task
- [Optimize AI credit usage in and by VS Code](https://code.visualstudio.com/docs/agents/guides/optimize-usage) - some points:
    - set your thinking effort of the model to something fitting, not every request needs a high thinking effort, use the different modes to adapt it to your task
    - start a new chat for new tasks to clear your context window -> less input tokens
    - disable unneeded tools and MCP servers
    - use /compact to manage your context if the conversations gets to long
- More general tips will come in the future...
