# Run a small before-and-after test

This is an exploratory, lightweight way to investigate whether explicit, discoverable guidance helps with one observed component decision. It is not a validated benchmark.

## 1. Choose one repeatable task

Use the same prompt and design goal for both runs. For example:

> Create a [page or flow] using [component]. Use the existing design system and explain the relevant component choices.

Adapt the prompt to your own system. Avoid mentioning the expected decision in the task prompt.

## 2. Run a baseline

Run the task without the new component rules. Use a fresh session. Save the prompt, output, date, agent/model, and relevant tool or context settings. Note which files were available and, where observable, which files the agent actually read. Keep file access distinct from whether it applied existing guidance.

## 3. Add and connect the guidance

Add a focused `rules.md`, link it from `DESIGN.md`, and make sure the agent can discover both files. Check discovery separately using the quick check in [SETUP.md](SETUP.md).

## 4. Repeat the same task

Keep the prompt and setup as consistent as possible, changing only the availability of the new guidance and the minimal routing instruction needed to expose it. Save the output, settings, and files actually loaded when observable. Use a fresh session again.

## 5. Compare observations

- **Did the agent find the rule?** If not, investigate the instruction or retrieval setup.
- **Was the file actually loaded?** Prefer tool logs or context evidence; a citation or self-report is a weaker check.
- **Did it apply the rule correctly?** If not, clarify the wording or add a useful example.
- **Did the output improve?** If not, investigate other influences, such as the task brief, composition, or conflicting sources.

Repeat paired baseline and treatment runs when practical, using fresh sessions and the same model, prompt, and tool settings. Record all runs, including cases where the output did not improve. Do not reuse an earlier output as context. A small test can guide the next iteration, but it does not establish that the approach will work across agents, tasks, or systems.
