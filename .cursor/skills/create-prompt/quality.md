# Write, review, deliver

Used by both create-prompt and refine-prompt.

## What the prompt contains

The model running the prompt sees only the prompt and what its host loads. It has not seen this chat. Include each item below that applies to the task:

- **Goal**, and what the result will be used for.
- **Context and inputs**: files, data, audience, and the facts the user told you. Project details only from files you opened. Say what a file does or what a test covers only after reading enough of it to know; its name or header is not enough.
- **Constraints**, each with its reason, and the scope: what to change and what to leave alone. When a rule applies to every item or section, say so.
- **Flow**: the order of work and the checks agreed with the user or found in the task search.
- **Done criteria** that can be checked, and how to check them: a command, a test, a screenshot, a comparison. If a check cannot be run, the model says so instead of reporting success.
- **Autonomy**: what it may do without asking, when to ask, when to stop.
- **Output**: the shape of the result and of the final report.
- **Role and examples**, only when they change the result.

Shape it as the live page for that model says. Set reasoning with the vendor's effort or thinking control, not with prose such as "think step by step", unless the live page says otherwise. Write direct sentences with measurable criteria.

## Review

Run this on the finished draft, before showing it.

| # | Check | Passes when |
| --- | --- | --- |
| 1 | Self-contained | A reader with only the prompt would not have to guess a fact, a file, or a term |
| 2 | Agreed decisions | Each user answer and each accepted proposal has a sentence in the prompt. "n/a" when you sent no proposal and got no answers |
| 3 | Done is checkable | Every done criterion has its own check that can fail when that criterion is unmet. A visual change is checked by looking at it, with before and after screenshots; lint and tests alone do not show it |
| 4 | No weak spot | Picture the poorest result that still obeys the prompt; a sentence rules it out |
| 5 | No conflicts | No two instructions contradict or repeat each other, and no criterion is vague ("better", "clean") |
| 6 | Fits the model | Structure and effort setting match the page you opened |
| 7 | Lean | Removing any sentence would change what the model does |
| 8 | Nothing lost | Every request, complaint, and answer from the user, from their first message to their last, has a goal and a done criterion in the prompt, unless they agreed to drop it |

Go through the checks one at a time against the text of the draft. For checks 2, 3, 4, and 6, find the sentence that satisfies it. If there is none, fix the draft and run the whole table again. For check 3, pair each done criterion with its check, one row each. A check that does not apply is marked "n/a" with the reason.

For check 8, reread the user's messages and write one row for each thing they asked: their request, then the words from the prompt that cover it. A request that the constraints forbid, or that is only partly met, fails: fix the draft, or ask the user before delivering.

## Deliver

In this order. Everything except the prompt is in the user's language. Outside the prompt, keep each item to one line unless the list says otherwise, with no introduction or recap.

1. **Model and effort**, and how to set the effort in that product or API.
2. **Sources**: links only, for the URLs opened in this conversation that shaped the prompt. If none, say so.
3. **Assumptions**, only if you wrote without asking.
4. **Review**: do the whole review, but do not show the table. Show one line with the count, such as "Review: 8/8 passed", counting "n/a" apart. Under it, one line for each check you had to fix, saying what changed, and one for anything still unmet or not verified. Do not report a pass for a check you did not run.
5. **The prompt**, one copyable block. If it contains triple backticks, fence it with four.
6. **Where to paste it**, and any file or data to attach.
7. **Plugins**: every plugin or skill the prompt names, one line each with the id and why. If none, one line with the reason (a plain chat, or no enabled plugin fits the task). Do not list the ones you rejected.
8. **Expected result**: a numbered list, at most 5 items, as many as the outcome needs. Each item is one plain line saying what they will see or have after running the prompt. Not a recap of the prompt.
