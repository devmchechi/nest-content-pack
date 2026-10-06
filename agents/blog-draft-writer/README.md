# Blog Draft Writer

Turns a topic, outline or a pile of notes into a draft people finish reading. It settles the reader and the angle first, outlines, writes in your voice, cuts filler and clichés, and gives you five headline options, a meta description and suggested visuals. Anything that needs fact-checking is marked inline. It never invents statistics or quotes.

## What it needs

**Working folder:** every agent has its own, and this one's is `~/.nest/local/work/blog-draft-writer/` on your computer (`%USERPROFILE%\.nest\local\work\blog-draft-writer\` on Windows). The agent sees it as its current directory, so a path like `./notes/` means `~/.nest/local/work/blog-draft-writer/notes/`. Other agents can't see this folder; in workflows, results pass between agents in their replies.

- A topic in chat, or a backlog in `./content/ideas.md` (that is, `~/.nest/local/work/blog-draft-writer/content/ideas.md`).
- Optional, but it makes a big difference: notes and data in `./content/notes/`, and two or three past posts in `./content/published/` so it can match your voice.
- Your voice, audience and defaults in `instructions.md` (edit after forking).

No internet access. It can't research live facts, so it builds on your notes and flags `[CHECK: ...]` items for you to verify.

## What it produces

- `./drafts/<date>-<slug>.md` with frontmatter (title, slug, meta description, keyword) and the full post.
- In chat: headline options, an outline summary, the list of items to verify, and visual ideas.

## Example prompts

- "Draft a post on why our team stopped doing story points, using ./content/notes/estimation.md."
- "Write the next post from my ideas backlog."
- "Outline only: 'A practical guide to on-call for teams of five'."
- "Revise ./drafts/2026-10-01-on-call.md to be 30% shorter and punchier."

## Capabilities in plain language

| Capability                    | Why                                    |
| ----------------------------- | -------------------------------------- |
| Reads files and lists folders | Reads your notes, ideas and past posts |
| Writes files (asks first)     | Saves drafts to `./drafts/`            |
| Shell commands                | No                                     |
| Network                       | None                                   |
