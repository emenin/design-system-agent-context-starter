# Connect the guidance to your agent

## 1. Put the files in the project where the agent works

Copy `DESIGN.md` into that project's root. Replace its placeholders with the paths or URLs for your tokens, components, and patterns.

Start with [templates/rules.md](templates/rules.md) and fill it with decisions confirmed by your design system owners.

Put `rules.md` next to the component's source, or in `components/<name>/` if that's simpler, and update the path in `DESIGN.md`.

To inspect this starter as provided, use [components/card/rules.md](components/card/rules.md), the filled-in example from the article.

## 2. Add the discovery instruction

Merge the instruction from [AGENTS.md](AGENTS.md) into your project's existing agent instructions:

```md
For UI work, read `DESIGN.md` first and follow its links
to the relevant guidance. Read a component's `rules.md`
only when working with that component.
```

Use the mechanism supported by your environment:

- If your agent reads `AGENTS.md`, add the instruction there.
- For Claude Code, add it to your project's `CLAUDE.md`. See the [project instructions documentation](https://code.claude.com/docs/en/memory).
- For Cursor, create a project rule at `.cursor/rules/design-system.mdc`, set its type to **Always Apply**, and paste the instruction into the rule body. See the [rules documentation](https://cursor.com/docs/rules).
- For other environments, add the instruction through their supported project-guidance mechanism.

Choose the route used by your team and preserve any existing instructions.

## 3. Check discovery

If your agent doesn't read `AGENTS.md`, set up the instruction first (step 2).

Open a fresh agent session in this starter repository and ask:

> Before editing anything, follow the project's agent instructions for a UI task using Card. Report which guidance you read, explain the choice between Default and Subtle, and flag any missing information. Do not change files.

Check for reads of `DESIGN.md` and `components/card/rules.md` in the tool logs, where available. If you adapted the files to another project, use that component's name and paths instead.

Then use [EXPERIMENT.md](EXPERIMENT.md) to compare runs on a real UI task in your project.
