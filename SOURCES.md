# Sources and rationale

This starter kit is an independent, lightweight proposal. These sources support the general design of the experiment; they do not validate this exact file structure or prove that it will improve every agent's output.

## Granular guidance and progressive disclosure

- [Figma: Write design system guidelines for Make kits](https://help.figma.com/hc/en-us/articles/43602393097239-Write-design-system-guidelines-for-Make-kits) recommends short, granular files, overview files that route to specific guidance, and progressive disclosure. This is guidance for Figma Make kits, not a universal agent standard.
- [Figma: Best practices for optimizing AI credits in Figma Make](https://help.figma.com/hc/en-us/articles/40097793879191-Best-practices-for-optimizing-AI-credits-in-Figma-Make) likewise recommends a primary guideline that points to smaller, task-specific Markdown files rather than one large file. This supports the information-architecture choice, not guaranteed agent behavior.
- [Anthropic: Claude Code skills](https://docs.anthropic.com/en/docs/claude-code/skills) describes a concrete progressive-loading mechanism: skill descriptions are available up front, while full instructions and supporting files can load when the skill is used. This is a tool-specific mechanism; it does not mean arbitrary Markdown files load on demand.
- [Atlassian: What we learned testing portable design context](https://www.atlassian.com/blog/how-we-build/atlassians-design-md-is-here-what-we-learned-testing-portable-design-context-in-practice) reports that a portable `DESIGN.md` helped with some prototyping tasks, while their integrated MCP and Skills performed better in their production-code tests. Atlassian also notes that its findings are not conclusive across systems. This is why the kit treats Markdown as one possible context layer and asks teams to test discovery and outcomes in their own setup.
- [Automattic: Design best practices for agentic experiences](https://system.automattic.design/ai/design-best-practices-for-agentic-experiences/) publishes a draft set of agent rules and reports an internal comparison across 60 runs on WooCommerce/Claude and WordPress/Gutenberg/Codex. The outcomes were mixed, and several rules failed even when loaded. This is useful evidence for measuring whether rules were applied and for pairing text guidance with code checks; it tests different UI tasks, not this starter's file structure.

## Agent discovery

- [Codex: Custom instructions with `AGENTS.md`](https://developers.openai.com/codex/guides/agents-md) describes repository instruction discovery.
- [Claude Code: How Claude remembers your project](https://code.claude.com/docs/en/memory) documents `CLAUDE.md` and current `AGENTS.md` support, including the setting that controls which instructions load.
- [Cursor: Rules](https://cursor.com/docs/rules) documents project rules in `.cursor/rules/` and the `.mdc` format.
- [Google Labs: Stitch's DESIGN.md format is now open-source](https://blog.google/innovation-and-ai/models-and-research/google-labs/stitch-design-md/) announces Google's open format for describing a visual design system to AI agents. That format's purpose differs from this starter's `DESIGN.md` map, so the shared filename should not imply compatibility.

These mechanisms differ across tools and versions. They support loading project-level instructions, but a pointer does not guarantee that a model opens every referenced file or follows its contents. For deterministic retrieval, the surrounding integration must explicitly fetch and inject the relevant files; access logs can verify loading, while output review is still needed to evaluate application.

## Limits of the evidence

The sources support short routing files, scoped guidance, and tool-specific context-loading mechanisms. They do not test this starter kit as a whole. Atlassian's and Automattic's reports are internal comparisons, and Figma's recommendations apply to Figma Make. Treat the experiment in this repository as a local pilot, not evidence of general effectiveness.

Related approaches have different goals. [Google's DESIGN.md specification](https://github.com/google-labs-code/design.md) describes a visual design system itself; this starter's `DESIGN.md` maps to existing sources. [Agentic Design System](https://github.com/aa-on-ai/agentic-design-system) is an installable skill pack with workflows and checks. This repository intentionally provides a smaller, manual experiment rather than either of those products.

Sources checked: 2026-10-15. Product documentation can change; recheck the linked setup docs when adopting the examples.

## About the filename

This kit uses `DESIGN.md` as a concise map to existing design system sources. The agent-specific instruction is the discovery point that tells the agent when to read it. This file is not a complete implementation of Google's portable `DESIGN.md` format or specification.
