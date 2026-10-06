# SEO Analyzer

Audits a draft or an exported HTML page for on-page SEO and readability. It measures real numbers (title and meta lengths, heading outline, keyword placement, readability, links, alt text, canonical and structured data), judges whether the content matches the searcher's intent, and returns a scored, prioritized list of fixes with ready-to-paste rewrites.

## What it needs

**Working folder:** every agent has its own, and this one's is `~/.nest/local/work/seo-analyzer/` on your computer (`%USERPROFILE%\.nest\local\work\seo-analyzer\` on Windows). The agent sees it as its current directory, so a path like `./notes/` means `~/.nest/local/work/seo-analyzer/notes/`. Other agents can't see this folder; in workflows, results pass between agents in their replies.

- A draft pasted into chat (in the Weekly Content workflow, Blog Draft Writer's draft arrives in the message), or a Markdown file in `./drafts/` or an HTML file in `./pages/` in its own folder.
- Optional: a target keyword, given in chat, in the draft's frontmatter, or in `instructions.md`.

It works offline. It doesn't have search volumes, rankings or competitor pages, and it never makes them up. Want it to audit live URLs? Fork it and add your domain to `network.allow` in `skill.md`:

```yaml
network:
  allow:
    - host: www.example.com
```

## What it produces

An audit in chat: a score with a transparent breakdown, a checks table, fixes in priority order (with impact and effort), and title, meta and heading rewrites. It doesn't edit your files.

## Example prompts

- "Audit the newest draft for 'incident postmortem template'."
- "Check ./pages/pricing.html for technical SEO problems."
- "Is the title of ./drafts/2026-10-01-on-call.md any good? Give me better options."

## Capabilities in plain language

| Capability                       | Why                                                     |
| -------------------------------- | ------------------------------------------------------- |
| Runs shell commands (asks first) | Runs a small Python script to measure the text and HTML |
| Reads files and lists folders    | Reads your drafts and pages                             |
| Writes files                     | No                                                      |
| Network                          | None (add your own domain after forking)                |
