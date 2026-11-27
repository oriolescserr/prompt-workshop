---
name: refine-prompt
description: Improve an existing prompt after researching the target model's current official guidance. Use when the user asks to fix, tighten, rewrite, adapt, or change a prompt they already have. Diagnoses the prompt and its flow before editing, then reviews the result.
---

# Refine a prompt

## Where are you?

Check this first, every turn.

| Situation | Do |
| --- | --- |
| A fact from step 1 is missing | Step 1 |
| All facts known, no analysis done yet | Steps 2 to 4 |
| The user answered your proposal, or wants a change to your revision | Step 5 |

## 1. Facts

1. The current prompt (pasted, or a file path)
2. Which model will run it?
3. Reasoning / effort level?
4. Where will it run? (Claude Code, Cursor, Codex, or a chat with no plugins)
5. What is wrong with it, or what should change?
6. Is a project on this computer involved? If yes, where is it?

Facts 2, 3, 4, and the project path come only from the user's messages, never from this machine's settings or folders.

If any is missing, ask for all the missing ones at once, as the rule on clickable questions says. If no answer comes back, end your turn. At the same time, ask for an output that disappointed them, if they have one. That output is optional.

## 2. Research

1. Do step 2 (model guidance) of [create-prompt](../create-prompt/SKILL.md).
2. Do step 3 (plugins) of the same file.
3. Do step 4 (how people get this result) of the same file.

## 3. Diagnose

Read [quality.md](../create-prompt/quality.md) and run its review table on the current prompt. Also look for:

- stale patterns for this model: over-specified steps, "think step by step", generic personas, effort written as prose
- flow problems: wrong order of work, a missing check, no stop condition
- steps that an enabled plugin already covers

A sentence edit that leaves a bad flow is unfinished.

Done when each change you intend to make is tied to a problem you can point at in the prompt, in the disappointing output, or in a page you opened, and you have noted what already works and stays.

## 4. Propose or write

Go to step 5 when your analysis confirms the change they asked for and no open question would change the result.

Otherwise send, in the user's language and in 20 lines or fewer, the problems found, the change to wording and flow you propose, and where the flow comes from (at most 4 lines: link and the idea taken, only from pages you opened and used; if none, say so). Then ask at most 4 questions as the rule on clickable questions says. Do not write the revision until the answers arrive. If they arrive through the question tool, go to step 5. Otherwise end your turn here.

## 5. Write, review, deliver

Read [quality.md](../create-prompt/quality.md) again. Revise the prompt, keeping what works and the user's intent. Run the review and deliver in its format, adding **What changed and why** right before the review result.

End your turn after the delivery.
