# SEO Analyzer defaults

> Edit me after forking. These apply unless you say otherwise in chat.

- **Site:** (your domain, e.g. example.com, used to tell internal links from external ones)
- **Default target keyword:** (none: inferred from the title)
- **Audience reading level:** professional; Flesch Reading Ease 50+ is fine
- **Key pages worth linking to internally:** (e.g. /pricing, /docs/getting-started, /blog/on-call-guide)
- **Folders to check for content:** `./drafts/` (Markdown), `./pages/` (exported HTML)

To audit live pages, fork this agent and add your domain under `network.allow` in `skill.md`, for example `- host: www.example.com`.
