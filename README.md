# Content Hub

A home for my articles, prompts, and Claude Code skills. Built to grow — drop new pieces into the right folder using the templates and they slot in cleanly.

Maintained by **Anthony · VortexMSP**.

## What's in here

| Folder | Contents |
|--------|----------|
| [`articles/`](articles/) | Long-form pieces, ready to publish. One markdown file per article, dated. |
| [`linkedin/`](linkedin/) | LinkedIn post versions of articles. |
| [`social/`](social/) | Twitter/X threads and other short-form social copy. |
| [`prompts/`](prompts/) | Reusable prompts, grouped by topic. See [`prompts/README.md`](prompts/README.md) for the catalog. |
| [`skills/`](skills/) | Claude Code skills (`SKILL.md` files). Copy a folder into `~/.claude/skills/` to install. |
| [`templates/`](templates/) | Starter templates for new articles, prompts, and skills. |

## Featured

- **Article:** [The US Army Has a Free Manual for Not Fooling Yourself](articles/2026-07-01-us-army-red-team-manual.md)
- **Prompts:** [Red Team a Decision](prompts/redteam/) — 7 individual prompts + a composite
- **Skill:** [`/redteam`](skills/redteam/SKILL.md) — the whole pipeline as a one-word command

## How to add new content

1. **New article:** copy [`templates/article-template.md`](templates/article-template.md) into `articles/` as `YYYY-MM-DD-slug.md`. Add a LinkedIn cut in `linkedin/` and a thread in `social/` if you're distributing it.
2. **New prompt set:** copy [`templates/prompt-template.md`](templates/prompt-template.md) into a new folder under `prompts/`, then add a row to [`prompts/README.md`](prompts/README.md).
3. **New skill:** copy [`templates/skill-template.md`](templates/skill-template.md) into `skills/<name>/SKILL.md`. To use it, also copy that folder into `~/.claude/skills/`.

## Installing a skill

```bash
cp -r skills/redteam ~/.claude/skills/redteam
# restart your session; the command loads as /redteam
```

## Conventions

- Filenames: `YYYY-MM-DD-kebab-slug.md` for dated content, `kebab-slug` for evergreen folders.
- Every article ends with the newsletter CTA.
- Prompts are copy-paste ready — no setup required to run them.
