# Design System Agent Context Starter

A small, experimental starting point for making existing design system knowledge easier for AI agents to find and apply.

Built around two Markdown files:

- `DESIGN.md` helps agents navigate existing design system knowledge.
- `rules.md` captures component decisions that aren't obvious from the API or are difficult to find in existing documentation.

The goal is to start small, test what agents get wrong, and improve the guidance based on what you learn.

## Why this exists

An AI agent with access to an entire design system still needs to find the guidance relevant to its task.

Some decisions are documented but difficult to discover. Others are implicit, outdated, or scattered across different sources.

This starter kit explores a lightweight way to make those decisions more accessible without rewriting the entire design system documentation.

## What's included

- [DESIGN.md](DESIGN.md): an entry point to existing design system sources.
- [AGENTS.md](AGENTS.md): an example instruction for agent discovery.
- [templates/rules.md](templates/rules.md): a reusable component guidance template.
- [components/card/rules.md](components/card/rules.md): the template filled in with the Card decisions described in the article.
- [SETUP.md](SETUP.md): a short guide to connecting the files to your agent.
- [EXPERIMENT.md](EXPERIMENT.md): a comparison workflow and a blank table for recording your runs.
- [LICENSE](LICENSE): the MIT license.

## How to use

### 1. Start with a problem

Choose a component or pattern an AI agent has been using incorrectly.

Avoid documenting the entire design system upfront.

### 2. Check existing guidance

Find out whether the correct decision is already documented.

If it exists, reference the source.

If it's missing or ambiguous, clarify the decision with the appropriate design system owners.

### 3. Configure DESIGN.md

Update `DESIGN.md` with the relevant paths or URLs for your design system.

Keep it short. The file should help agents find information, not duplicate the entire documentation library.

### 4. Add component rules

Start with a copy of `templates/rules.md`.

Put `rules.md` next to the component's source, or in `components/<name>/` if that's simpler, and update the path in `DESIGN.md`.

The included Card example uses the same structure, with the optional Exceptions section omitted. Replace its source placeholders and decisions with guidance from your own system.

Document only the decisions relevant to the problem you're investigating.

Include the reasoning behind each decision.

### 5. Connect the agent

Follow [SETUP.md](SETUP.md) to configure your agent to read `DESIGN.md` before working on UI and check that it can find the relevant component rules.

### 6. Test and refine

Use [EXPERIMENT.md](EXPERIMENT.md) to compare runs and record the expected decision, its source, and what happened.

## Keeping guidance up to date

Review component rules as part of the same pull request when the component changes. Confirm the decisions with the appropriate design system owners.

## About DESIGN.md

Here, `DESIGN.md` is a project-specific map to existing knowledge. Other tools use the same filename for different purposes. Adapt the filename and discovery instructions to your environment; this kit does not implement those other formats.

## Limitations

This starter kit is experimental and has not been validated. Creating the files alone does not ensure that an agent will find or follow them. UI validation, documentation updates, and keeping rules aligned with component code remain manual work. The Card decisions describe the context in the article; they need review before use in another design system.

## Further reading

- [Atlassian — DESIGN.md](https://www.atlassian.com/blog/how-we-build/atlassians-design-md-is-here-what-we-learned-testing-portable-design-context-in-practice)
- [Figma — Write design system guidelines for Make kits](https://help.figma.com/hc/en-us/articles/43602393097239-Write-design-system-guidelines-for-Make-kits)
- [TJ Pitre — Anatomy of an AI-Ready Design System](https://southleft.substack.com/p/anatomy-of-an-ai-ready-design-system)
- [Nathan Curtis — Component Contracts and Schemas](https://nathanacurtis.substack.com/p/component-contracts-and-schemas)

## License

MIT. See [LICENSE](LICENSE).
