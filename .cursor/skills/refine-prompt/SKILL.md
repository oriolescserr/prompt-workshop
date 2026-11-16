---
name: refine-prompt
description: Improve an existing prompt after researching the target model's current official guidance. Use when the user asks to fix, tighten, rewrite, adapt, or change a prompt they already have. Searches the best change to the prompt and the flow before editing.
---

# Refine a prompt

## 1. Facts

Ask and stop when one of these is missing:

- Which model will run it?
- Reasoning / effort level?
- Where will it run? (Claude Code, Cursor, Codex, or a chat with no plugins)
- What is wrong with the current prompt, or what should change?
- Local project involved? Path?

## 2. Best change

Read the matching file in `.cursor/skills/create-prompt/labs/`, then **search official docs for that exact model**. Fix stale patterns (over-specified steps, “think step by step”, generic personas, effort stuffed into prose). Live docs beat the lab file.

Then sync that host's file in `.host-plugins/` the same way as [create-prompt](../create-prompt/SKILL.md) section 3. Create the file if it is missing. If a noted plugin already covers part of the task, name it in the revised prompt instead of restating its steps.

Then search or analyze the best way to change the **prompt and the flow** so the task works. Look at order of work, what gets checked, and when the run stops. A sentence edit that leaves a bad sequence is unfinished. Prefer official docs and write-ups of real workflows, the same way create-prompt searches how people get the outcome.

Done when you can say what should change in the wording and in the flow, from that search, or you can say the search came back empty and the change comes from the model docs and the prompt in front of you.

## 3. Align or write

When the best flow differs from the change they named, or an open question would change the result, propose the flow and ask. Wait. The revised prompt is the next turn.

When the analysis confirms their change, write it.

## 4. Return

- What you changed and why (from the docs, not vibes)
- The revised copyable prompt (**English** unless the user asked for another language)
- Effort / thinking setting to use
- After the prompt, before the expected result, every plugin or skill the prompt tells the model to use. One short line each: the id, and why this prompt names it. If it names none, say that no plugin was used and give the reason in one short line (a plain chat, or none of the enabled plugins fit this task). Same language as the expected result.
- A short **expected result** in the language the user used in this chat. A numbered list with as many items as the outcome needs, at most 5. Each item is one plain line: what they will see or have after that prompt is run. Not a recap of the prompt.
