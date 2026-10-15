# Try the starter with an AI coding agent

## The quick answer

There is nothing to install. This repository is a set of example files. To try the idea, copy the relevant files into the code project where you want the agent to use your design system.

For example: if you want Codex to use the guidance while editing your app, put the files in the app's repository. Keeping them only in this starter repository will not affect the app or Codex.

There are two different roles: the agent-specific instruction (such as `AGENTS.md`) is the **discovery point**; `DESIGN.md` is the **design context map** it points to. `DESIGN.md` does not make itself load.

## First try with Codex

1. In your app's repository, copy `DESIGN.md` and the `components/` folder from this starter. Put them in the top-level project folder, next to folders such as `src/` or files such as `package.json`.
2. Replace the example links in `DESIGN.md` with links to your real tokens, components, and patterns. You can start with one component rule; you do not need to document everything.
3. In that same top-level folder, find `AGENTS.md`. If it exists, add this at the end. If not, create a plain text file named `AGENTS.md` and paste this in:

   ```md
   For UI work, read `DESIGN.md` first. Follow its links to relevant guidance. Read a component's `rules.md` only when working with that component.
   ```

4. Open the app project in Codex and ask: “Before editing anything, find `DESIGN.md` and the button rule it points to. Tell me which files you read and summarize the button guidance. Do not make changes.”
5. If Codex finds the files, try the comparison in [EXPERIMENT.md](EXPERIMENT.md). Use a new conversation for each run.

If you only want to inspect this starter, open `README.md`, `DESIGN.md`, and `components/example/rules.md`. That does not connect it to an agent.

## What progressive disclosure means here

The intended sequence is: the agent reads its project instruction; that instruction points it to `DESIGN.md` for UI work; `DESIGN.md` points it to relevant source documents; the agent opens a component's rules only when the task involves that component. This keeps detailed rules out of the always-loaded instruction.

This is a workflow, not a guarantee. A Markdown pointer cannot force an agent to open or follow a file. For deterministic loading, an integration has to fetch and supply the right files. Even then, check whether the agent applied the guidance.

## Other coding agents

Use the same idea with the project instruction format your tool supports. Claude Code commonly uses `CLAUDE.md`; Cursor uses `.cursor/rules/`. Check the current official setup instructions before adapting the short Codex example above. You do not need to configure multiple agents to try this starter.

- [Codex project instructions](https://developers.openai.com/codex/guides/agents-md)
- [Claude Code memory and project instructions](https://code.claude.com/docs/en/memory)
- [Cursor project rules](https://cursor.com/docs/rules)
