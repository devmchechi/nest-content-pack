# Content Pack

A small editorial team for a blog and newsletter. Blog Draft Writer turns topics and notes into drafts in your voice, SEO Analyzer audits them with real measurements, and Newsletter Formatter assembles a paste-ready issue in Markdown and email-safe HTML. The **Weekly Content** workflow runs the whole week's cycle.

## Agents

| Agent                                                         | What it does                                                                                     | Network |
| ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ | ------- |
| [Blog Draft Writer](agents/blog-draft-writer/README.md)       | Drafts posts from topics and notes, with headline options, meta description and fact-check flags | none    |
| [Newsletter Formatter](agents/newsletter-formatter/README.md) | Builds an issue from posts and links: subject lines, preview text, Markdown and HTML             | none    |
| [SEO Analyzer](agents/seo-analyzer/README.md)                 | Scored on-page SEO and readability audit with prioritized fixes and rewrites                     | none    |

## Workflow: Weekly Content

`workflows/weekly-content.yaml`:

1. **draft** (Blog Draft Writer): drafts the first open topic in its `content/ideas.md`, saves it to its `drafts/`, and returns the full draft in its reply.
2. **seo** (SEO Analyzer): audits the draft from that reply for its primary keyword. If this step fails, the workflow continues.
3. **revise** (Blog Draft Writer): applies the SEO fixes that improve the post for readers, and says which it skipped.
4. **newsletter** (Newsletter Formatter, pauses for your approval): builds the week's issue from the revised post (passed in the message) and the links in its own `newsletter/inbox.md`.

Suggested files (each agent has its own working folder):

```
~/.nest/local/work/blog-draft-writer/content/ideas.md       topic backlog, one per line
~/.nest/local/work/blog-draft-writer/content/notes/         research notes, quotes, data
~/.nest/local/work/blog-draft-writer/content/published/     a few past posts (voice samples)
~/.nest/local/work/newsletter-formatter/newsletter/inbox.md links collected during the week
```

## Working folders

Every agent has its own working folder, `~/.nest/local/work/<agent-id>/` on your computer (`%USERPROFILE%\.nest\local\work\<agent-id>\` on Windows), which it sees as its current directory. Agents can't see each other's folders. Put input files in the folder of the agent that reads them; in workflows, results pass from step to step in the agents' replies, never through files.

## Capabilities

- **Tools:** reading and writing files, listing folders; SEO Analyzer also runs shell commands (a Python script that measures the text). Shell commands and file writes always ask for your approval first.
- **Network:** none. The agents can't browse, so they never invent statistics or links; they mark what you need to check or fill in. To audit live pages, fork SEO Analyzer and add your domain to its `network.allow`.
- **Publishing:** nothing is published or sent. You paste the results into your CMS and email tool.
- **Pilots:** none.
- **Typical cost:** about $0.06 to $0.50 per Weekly Content run on paid models.

## Fork to customize

Installed agents are read-only. **Fork** an agent in Nest to get your own editable copy, then set your voice, audience, newsletter name, sections and merge tags in its `instructions.md` (marked "Edit me after forking").

## License

MIT. See [LICENSE](LICENSE).
