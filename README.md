# Figma Accessibility Review

**English** | [Русский](README.ru.md)

An AI agent skill that helps designers review Figma designs for accessibility before handing them off to developers. It produces a report with evidence, priorities, and concrete fixes, along with tasks for testing the implemented interface.

## What it checks

The 32 checks cover text and control contrast, use of color, target sizes, labels, images, component states, enlarged text, localization, and intended interface behavior. Particular attention is given to whether the user journey makes sense for someone using a screen reader.

The skill distinguishes confirmed design issues, questions that need clarification, recommendations, and implementation tests. Follow-up reviews preserve finding IDs and show what has changed.

## Installation

1. Download or clone this repository.
2. Place the **entire folder**, named `figma-accessibility-review`, in the user-skills directory documented for your agent. Copying `SKILL.md` alone is not enough: it depends on files in `references/`.
3. Refresh the skill list or restart your agent if your environment requires it.

This is a set of Markdown instructions. No server, package manager, or software dependencies are required.

## What you need for a review

For a detailed review, connect a Figma connector or MCP server with access to the relevant file. Your agent needs to be able to read the design structure, element properties, and images. The specific tools and authentication method depend on your environment.

You can also provide a structured export. If only a screenshot is available, the skill performs a preliminary visual review and states its limitations: exact contrast, interactive bounds, and token bindings cannot be verified from an image alone.

## Example prompts

> Review this screen for accessibility: [Figma frame link]. This is a web interface in light mode. The main user journey is to fill out the form and submit an application.

> Review this component and its states. Show what is confirmed in the design and what needs clarification from a developer.

> Review these frames again after the fixes. Compare them with the attached previous report and preserve the finding IDs.

## What you get

- Review scope, evidence used, and limitations.
- Findings with their location in the design, supporting evidence, user impact, and a suggested fix.
- Specifications for primary actions: name, role, value, state, and expected behavior.
- Tasks for developers and QA to test keyboard access, screen-reader behavior, and enlarged text.
- For follow-up reviews, a list of resolved, remaining, and unverified findings.

By default, the skill reads the design and writes a report. Design edits, comments, and code fixes require a separate request.

A Figma review does not prove that the finished product is accessible and is not WCAG certification. The layer tree is not a substitute for the DOM or accessibility tree; actual behavior must be tested in the working interface.

## Using with Codex

Install the folder as a user skill according to the documentation for your version of Codex, then mention `figma-accessibility-review` in your prompt and include a design link. To modify the skill itself, open the repository in Codex: [AGENTS.md](AGENTS.md) describes the structure and working rules.

## Sources and contributions

For the instructions and full checklist, see [SKILL.md](SKILL.md). For sources and attribution details, see [references/provenance.md](references/provenance.md).

Suggestions and fixes are welcome: see [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT — see [LICENSE](LICENSE). The repository license does not cover external materials cited as sources.
