# Where to look, per model family

Start from the official page for the family, then find the page for the exact model the user named. These are entry points, not the guidance itself. If a link has moved or covers a different model, search the same vendor's site.

| Family | Official page |
| --- | --- |
| Claude / Anthropic | https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices |
| GPT / OpenAI / Codex | https://developers.openai.com/api/docs/guides/prompt-guidance |
| Gemini / Google | https://aistudio.google.com/docs/prompting-strategies |
| Grok / xAI / Grok Build | https://docs.x.ai/developers/model-capabilities/text/reasoning |
| DeepSeek | https://api-docs.deepseek.com/guides/thinking_mode/ |
| Mistral | https://docs.mistral.ai/inference/prompting |
| Composer / Cursor Grok / Cloud Agents | https://cursor.com/docs and https://cursor.com/docs/cloud-agent/api/endpoints |

For any other family, search for the vendor's official documentation.

## Traps to check

Each one changes how the prompt is run. Confirm it on the live page before telling the user.

- **Claude:** do not ask the model to write its reasoning into the answer; some models decline.
- **Grok:** on recent models reasoning cannot be turned off.
- **DeepSeek:** thinking is on by default, temperature has no effect while it is on, and with tools `reasoning_content` must be passed back or the API returns 400.

## When the prompt runs in Cursor

Applies to any model run in Cursor.

- Standing conventions belong in `.cursor/rules` or `AGENTS.md`. The prompt is the task, not a second style guide.
- Effort and Fast are picker or `model.params` settings, not text in the prompt. Fast can change billing; say so where you explain how to use the prompt.
- State the scope, how to verify, and what needs approval (push, production, secrets).
- Cloud Agents take `prompt.text` plus `model.id` and `model.params`. `GET /v1/models` lists the valid combinations.
