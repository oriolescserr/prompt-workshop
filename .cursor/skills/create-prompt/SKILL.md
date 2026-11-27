---
name: create-prompt
description: Specialist workflow to write a ready-to-paste model prompt. Searches official docs for the exact model named, proposes a flow and asks, then writes and reviews the prompt. Use when the user asks to create, write, generate, or craft a prompt, including when they say to write it now.
---

# Create a prompt

## Where are you?

Check this first, every turn.

| Situation | Do |
| --- | --- |
| A fact from step 1 is missing | Step 1 |
| All facts known, no proposal sent yet | Steps 2 to 5 |
| The user answered your proposal | Step 6. If an answer changes the model, host, or task, redo the affected steps first |
| The user wants a change to the prompt you delivered | Step 6 again, including the review |

## 1. Facts

1. Which model will run the prompt?
2. How much reasoning / effort? (`low` / `medium` / `high` / `xhigh` / `max` / off / default)
3. What should the prompt make that model do, and what does done look like?
4. Where will it run? (Claude Code, Cursor, Codex, or a chat with no plugins)
5. Is a project on this computer involved? If yes, where is it?

The model, the effort, where it will run, and the project path come only from the user's messages. Do not take them from this machine's settings, installed tools, config files, or the folders you can find, even when only one answer looks likely. A project name is not a path.

Once they gave a path, read what you need to understand the task and to ask good questions. Do not ask what the project's files already answer about the task.

If any fact is missing, ask for all the missing ones at once, as the rule on clickable questions says. If no answer comes back, end your turn. When the format or tone of the result matters, ask in the same message for an example they like.

Done when all five are known.

## 2. Model guidance

1. Read [sources.md](sources.md) for the family's official page and its traps. If the prompt will run in Cursor, read its Cursor section too.
2. Search the web for that exact model: prompting guide, effort or thinking settings, migration notes. Prefer the vendor's site. Open the pages; a search snippet is not enough.
3. Where a live page disagrees with `sources.md`, follow the live page.

If you cannot search or open a page, tell the user, and say the prompt will rest on `sources.md` and your training data.

Done when you have opened a page for that model, or have said that you could not.

## 3. Plugins

If the prompt will run in a plain chat or an API call, skip this step. Otherwise read [plugins.md](plugins.md) now and follow it.

Done when you know which enabled plugins, if any, the prompt should name.

## 4. How people get this result

Search the web for what has worked for other people who wanted this kind of outcome: order of work, tools, common failures, and what they check before calling it done. Prefer official docs and write-ups of real workflows. This search is about the task; the search in step 2 was about the model.

Done when you have an order of work and a way to check the result, each from a page you opened, or you can say the search came back empty and the proposal comes from the model docs and the project.

## 5. Propose and ask

A direct request to write the prompt still gets this step. Skip it only when the user said in so many words to ask nothing ("without questions", "sense preguntes"); then go to step 6 and list your assumptions in the delivery. Hurry or impatience ("write it now", "ves per feina", "no weird questions") does not skip it. If in doubt, ask.

The exception never covers step 1.

First send this, in the user's language, in 20 lines or fewer:

```text
**Proposed flow**
<at most 5 steps, one line each, including how the result is checked>

**Changes to your request**
<at most 3 lines, each with its reason; or "none">

**Where the flow comes from**
<at most 4 lines: link — the idea you took from it>
```

Under "Where the flow comes from", list only pages you opened in step 4 and used. If the search gave nothing useful, or you could not search, say that in one line instead; do not fill it with model docs or links you did not open.

Leave out plugins and effort settings; they belong in the delivery.

Then ask the questions as the rule on clickable questions says: at most 4, only those whose answer would change the prompt, the flow, or what done looks like, the highest impact first. Each has 2 to 4 short options.

**Never narrow the request silently.** Before sending, list for yourself every thing the user asked for and every complaint they made. Each one stays in the flow. If you would drop, shrink, or postpone one, or it conflicts with a project rule or with another request, make that one of the questions and say what they would lose. An answer to one question does not cancel a request it did not mention.

Do not write the prompt until the answers arrive. If they arrive through the question tool, go to step 6. Otherwise end your turn here.

## 6. Write, review, deliver

Read [quality.md](quality.md) now, even if you read it earlier. Write the prompt, run its review, and deliver in its format.

End your turn after the delivery.
