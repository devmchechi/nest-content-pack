# Newsletter Formatter

Turns this week's raw material (your latest post, a list of links, product updates) into a finished newsletter issue: an intro, sections, blurbs that say why each link matters, five subject lines, preview text, and both Markdown and email-safe HTML you can paste into Buttondown, Mailchimp, Substack, Beehiiv or similar.

## What it needs

**Working folder:** every agent has its own, and this one's is `~/.nest/local/work/newsletter-formatter/` on your computer (`%USERPROFILE%\.nest\local\work\newsletter-formatter\` on Windows). The agent sees it as its current directory, so a path like `./notes/` means `~/.nest/local/work/newsletter-formatter/notes/`. Other agents can't see this folder; in workflows, results pass between agents in their replies.

- Material in its own folder: links and notes in `./newsletter/inbox.md`, posts to feature in `./posts/`. You can also paste them into chat. In the Weekly Content workflow the post arrives in the message from Blog Draft Writer.
- Optional: past issues in `./newsletter/` so it matches your structure and numbering.
- Your newsletter name, sections, sign-off and merge tags in `instructions.md` (edit after forking).

It can't send email or browse the web. Links without a description get a `[BLURB NEEDED]` placeholder instead of a guess.

## What it produces

- `./newsletter/issue-NNN-<date>.md` and `.html` (single-column table layout, inline styles, no scripts or tracking).
- Subject line options, preview text, word count and reading time in chat.

## Example prompts

- "Build this week's issue from inbox.md and the newest draft."
- "Format these five links into a short issue: <paste>"
- "Give me 10 more subject lines for issue 42, less formal."

## Capabilities in plain language

| Capability                    | Why                                           |
| ----------------------------- | --------------------------------------------- |
| Reads files and lists folders | Reads your inbox file, drafts and past issues |
| Writes files (asks first)     | Saves the issue to `./newsletter/`            |
| Shell commands                | No                                            |
| Network                       | None                                          |
