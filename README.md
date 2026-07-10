# gh-copilot-plugin-token-minimizing

This repo provides ways to reduce the number of tokens used when using the GitHub Copilot plugin in IDEs (e.g. VSCode or WebStorm).

## Caveman

Caveman's original description:
> A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill/plugin and Codex plugin that makes agent talk like caveman — cutting **~75% of output tokens** while keeping full technical accuracy. Now with 文言文 mode( wenyan-mode), [...] that cuts **~46% of input tokens** every session.

> Based on the viral observation that caveman-speak dramatically reduces LLM token usage without losing technical substance. [...]

Credit goes to [Julius Brussee](https://github.com/JuliusBrussee) and all contributors to the original project. Made usable for GitHub Copilot by [Mijutra](https://github.com/Mijutra/caveman-copilot) by simply providing all necessary information in the `copilot-instructions.md` file.

If you want to use it simply copy-paste the `# caveman` section of the `.gihub/copilot-instructions.md` into your own and switch to your desired mode via chat e.g. `/caveman ultra`.

**Important**: Instead of `caveman`, you could also use the prefix `be brief` in your prompts, which works in a similar way. You can find more information in this [video](https://www.youtube.com/watch?v=wijoYNiZq3M) by Max Taylor.

## RTK - Rust Token Killer

RTK's original description:
> Your AI agent is drowning in CLI noise. Fix it. RTK compresses command outputs before they reach the context window. Better reasoning. Longer sessions. Lower costs.

> See [reasons](https://www.rtk-ai.app/#problem) and [repo](https://github.com/rtk-ai/rtk) for more information.

To install it for your GitHub Copilot first you need to get the `.exe` for your operation system, see [Downloads](https://github.com/rtk-ai/rtk/releases) and put it under `C:\Program Files\rtk`. Also add this exact path to your system variables `Path`.

After this is done simply run `rtk init -g --copilot` in the desired project to set it up. This will generate an entrance for it in your `copilot-instructions.md` and it will also create the `rtk-rewrite.json` hook (can both be seen in this repo to check if it worked or to copy-paste it).

Use `rtk gain` to see statistics of its effects.

## Ponytail

Ponytail's description:
> You know him. Long ponytail. Oval glasses. Has been at the company longer than the version control. You show him fifty lines; he looks at them, says nothing, and replaces them with one.
> Ponytail puts him inside your AI agent.
> The rule was never "fewest tokens." It is: write only what the task needs, and never cut validation, error handling, security, or accessibility. The code ends up small because it is necessary, not golfed. Lower cost and latency are a side effect on the models that follow the ladder; a terse reasoning model that spends thinking tokens deliberating the rungs can go the other way (on GPT-5.5 it does).

Credit goes to [Dietrich Gebert](https://github.com/DietrichGebert), see the original [ponytail repo](https://github.com/DietrichGebert/ponytail) for more information.

If you want to use it simply copy-paste the `# Ponytail, lazy senior dev mode` section of the `.gihub/copilot-instructions.md` into your own. 

## Headroom

Headroom's description:
> Headroom compresses everything your AI agent reads — tool outputs, logs, RAG chunks, files, and conversation history — before it reaches the LLM. Same answers, fraction of the tokens.

Credit goes to [Tejas Chopra](https://github.com/chopratejas) and all contributors to the original project, see the original [headroom repo](https://github.com/headroomlabs-ai/headroom) for more information. 

Best approach for setting headroom up for GitHub Copilot Plugin inside e.g. Visual Studio Code is still to be done from my side. There is a way to set it up provided by [Antoine Mahassadi aka damnthonyy](https://github.com/damnthonyy). You can find a whole discussion about this topic [here](https://github.com/headroomlabs-ai/headroom/issues/962) and his integration fork of headroom into vscode [here](https://github.com/damnthonyy/vscode/tree/feat/headroom-proxy-for-chat-copilot). Feel free to use his approach.

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
