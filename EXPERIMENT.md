# Run a small before-and-after test

Choose one component decision an agent has been getting wrong. Use your project's component implementation and confirmed guidance for the comparison.

## 1. Define the task and expected decision

Record the exact task prompt, the decision you are testing, the expected choice in that context, and its source before running the comparison. Keep the expected choice out of the task prompt.

For example:

> Create a [page or flow] using [component]. Use the existing design system and explain the relevant component choices.

## 2. Compare runs

1. Run the task without the additional component rules, using a fresh session.
2. Add the rules and connect them using [SETUP.md](SETUP.md).
3. Run the same task in another fresh session, keeping the model, tools, existing documentation, task, and starting project state as consistent as possible.
4. Record the result of each run, including cases where the guidance did not help. Repeat the pair to check whether the result recurs.

The intended difference is the availability of the additional guidance and the instruction needed to find it. Keep the new rules out of the baseline context, and record any other differences.

## 3. Record each run

Copy this block for each comparison:

```md
Task prompt: [exact prompt, identical for every run]

Decision tested: [one component decision in a specific context]

Expected decision and criterion: [what should happen and how you will judge it]

Source of the expected decision: [path or URL, plus section or version if relevant]

Shared setup: [agent, model/version, tools, starting project state, and existing guidance available in both runs]

| Run | Date | Rules available? | Files loaded (from tool logs) | Decision made | Meets criterion? | Notes / output reference |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | | No | | | | |
| 2 | | Yes | | | | |
```

For files loaded, record paths supported by tool logs. Write **Not observable** when logs are unavailable; distinguish any agent-reported reads in Notes. For Meets criterion?, use **Yes**, **No**, or **Unclear**. Record setup differences and links or paths to saved outputs in Notes.

## 4. Decide what to change

- If the agent did not find the guidance, check how it is connected to the workflow.
- If it found the guidance but misunderstood the decision, clarify the wording or add an example.
- If it understood the decision but the output did not improve, investigate other influences before adding more rules.
