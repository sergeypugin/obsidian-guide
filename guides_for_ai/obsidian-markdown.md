---
name: obsidian-markdown
description: Write and edit Obsidian Flavored Markdown — wikilinks, embeds, callouts, block references, tags, comments, highlights, and math
---

# Obsidian Flavored Markdown

Obsidian extends standard Markdown (CommonMark + GitHub Flavored Markdown) with syntax for connecting and enriching notes: wikilinks, embeds, callouts, block references, tags, comments, highlights, and math.

## Internal Links (Wikilinks)

Link to other notes by title — no path or extension needed unless disambiguating:

| Syntax                        | Meaning                               |
| ----------------------------- | ------------------------------------- |
| `[Note Name](Note%20Name)`               | Link by note title                    |
| `[Display Text](Note%20Name%5C)` | Custom display text                   |
| `[](Note%20Name#Heading)`       | Link to a heading within a note       |
| `[](Note%20Name#^block-id)`     | Link to a specific block              |
| `[#Heading](#Heading)`                | Link to a heading in the current note |
| `[folder/Note Name](folder/Note%20Name)`        | Disambiguate when titles collide      |

Wikilinks are the preferred linking style in Obsidian. Standard Markdown links (`[text](path)`) also work, but wikilinks integrate with the graph view, backlinks, and autocomplete.

### Block References

Append a caret + identifier to the end of any block (paragraph, list item, etc.) to give it a stable anchor, then link to it:

```markdown
This is an important paragraph. ^key-point

See [](Other%20Note#^key-point) for context.
```

Block IDs may contain letters, numbers, and hyphens. Obsidian auto-generates one (e.g. `^a1b2c3`) if you link to a block before naming it.

## Embeds

Prefix any wikilink with `!` to embed the target's content inline instead of linking to it:

| Syntax                     | Meaning                       |
| -------------------------- | ----------------------------- |
| `![Note Name](Note%20Name)`           | Embed an entire note          |
| `![](Note%20Name#Heading)`   | Embed one section             |
| `![](Note%20Name#^block-id)` | Embed a single block          |
| `![image.png](image.png)`           | Embed an image                |
| `![300](image.png%5C)`      | Embed an image at 300px width |
| `![300x200](image.png%5C)`  | Width x height                |
| `![document.pdf](document.pdf)`        | Embed a PDF                   |
| `![](document.pdf#page=3)` | Embed a specific PDF page     |
| `![recording.mp3](recording.mp3)`       | Embed audio                   |
| `![clip.mp4](clip.mp4)`            | Embed video                   |

Embeds only render in Reading view and Live Preview — they appear as raw `![...](...)` text in Source mode. After adding embeds, let the user know they may need Reading view to see them rendered.

## Callouts

Callouts are styled blockquotes for admonitions. Structure: a blockquote whose first line is `> [!type]`, optionally followed by a custom title:

```markdown
> [!note]
> This is a note callout with default title.

> [!warning] Custom Title
> This callout has a custom title.

> [!tip]+ Expanded by default
> The `+` makes a foldable callout that starts open.

> [!info]- Collapsed by default
> The `-` makes a foldable callout that starts closed.
```

Built-in types (each has its own icon/color): `note`, `abstract`/`summary`/`tldr`, `info`, `todo`, `tip`/`hint`/`important`, `success`/`check`/`done`, `question`/`help`/`faq`, `warning`/`caution`/`attention`, `failure`/`fail`/`missing`, `danger`/`error`, `bug`, `example`, `quote`/`cite`. Unknown types fall back to the `note` style. Callouts can be nested by adding more `>` levels, and may contain any Markdown, including wikilinks and embeds.

## Properties (Frontmatter)

```yaml
---
title: My Note
tags:
  - project
  - active
aliases:
  - Alt Name
date: 2026-06-09
cssclasses:
  - wide-page
---
```

For full guidance on property types (text, list, number, checkbox, date, datetime) and their interaction with Bases, Templates, and Search, go to the [`obsidian-properties`](obsidian-properties.md).

## Tags

Inline `#tags` categorize notes and can be nested with `/`:

```markdown
#project #status/active #area/work
```

Tags can also live in frontmatter under the `tags` property (without the `#`). Tags may contain letters, numbers, `-`, `_`, and `/`, but not spaces, and cannot be purely numeric.

## Comments

Text wrapped in `%%` is hidden from Reading view but stays in the file:

```markdown
%%This is a private note that won't render.%%

Visible text %%inline hidden%% more visible text.
```

## Other Syntax

| Feature     | Syntax                                                        |
| ----------- | ------------------------------------------------------------- |
| Highlight   | `==highlighted text==`                                        |
| Inline math | `$e = mc^2$`                                                  |
| Block math  | `$$\int_a^b f(x)\,dx$$` on its own line                       |
| Footnote    | `Some text.[^1]` then `[^1]: The definition.` on its own line |

Mermaid diagrams render from a fenced `mermaid` code block and support wikilinks between nodes:

```mermaid
graph TD
  A[Note A](Note%20A) --> B[Note B](Note%20B)
```

Standard GitHub Flavored Markdown — tables, task lists (`- [ ]` / `- [x]`), fenced code blocks, strikethrough (`~~text~~`) — all work as expected.

## Tips

- Prefer `[wikilinks](wikilinks)` over Markdown links so the note participates in the graph and backlinks.
- When linking to a heading or block that doesn't exist yet, create the anchor in the target note so the link resolves.
- Keep callout types lowercase; the title after `[!type]` is free-form text.
- Don't place body content before frontmatter unless explicitly editing the frontmatter block.
