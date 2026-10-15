# Design system agent context starter

**An open experiment** in helping AI agents find and apply design-system decisions.

A small starter kit for trying the approach in your own project.

## What this is — and what it isn't

**This is** a small, open experiment: a starter kit for testing whether design-system guidance helps an AI agent make better UI decisions in your project.

**This isn't** a ready-to-install tool or a proven solution. It won't automatically connect to your agent or ensure that it reads and follows the guidance. You'll need to point your agent to `DESIGN.md` using the project instructions it supports.

## What's included

- [`DESIGN.md`](DESIGN.md): a short map to your design system's sources of truth. The agent-specific instruction tells the agent when to open it.
- [`components/example/rules.md`](components/example/rules.md): a reusable component-level rules template.
- [`SETUP.md`](SETUP.md): ways to connect the files to an agent.
- [`EXPERIMENT.md`](EXPERIMENT.md): a repeatable before-and-after test.
- [`SOURCES.md`](SOURCES.md): research and documentation informing this proposal.

## Try it with your system

**Nothing to install:** this repository is a set of example files. To try it, copy the relevant files into the code repository where you want the agent to work, then add a short project instruction that points to them. See the beginner path in [SETUP.md](SETUP.md). The starter repository itself does not change how an agent behaves.

1. Copy `DESIGN.md` into the project repository where the agent will work and replace each placeholder with a real path or URL to your design system sources.
2. Choose a component where an agent has made a repeatable, observable mistake.
3. Check the existing documentation and code before writing a rule. Preserve existing decisions; flag disagreements for human review.
4. Add a component-level `rules.md` with only the relevant guidance and sources.
5. Add a short discovery instruction using the format your agent supports. See [SETUP.md](SETUP.md).
6. Run the same task with and without the guidance and record what changed. See [EXPERIMENT.md](EXPERIMENT.md).

Keep the test task, model, tools, and other context as consistent as possible. Use separate fresh sessions for each run so the baseline does not carry the new rule into the comparison. Treat the results as observations, not proof; repeat runs before drawing conclusions.

## Adapt the component template

The component file uses placeholders rather than prescribing design decisions. Replace them with guidance confirmed by your own design system documentation and code. Don't copy rules from another system without validating them.

## Possible next steps

If repeated use shows a real need, this could grow into tooling. A CLI might scaffold files, check links, or verify that an agent can access the guidance. An MCP server might let agents retrieve relevant guidance on demand. Those are directions to validate with users; they are not part of this starter kit.
