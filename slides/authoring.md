---
title: Authoring slides
---

# Authoring slides

Decks live in `slides/decks/` and are copied to the site verbatim — docfx treats
that folder as a *resource*, not as content, so a deck is plain HTML with the
slide text written as Markdown inside it.

## Adding a deck

1. Copy `slides/decks/template.html` to `slides/decks/NN-my-talk.html`.
2. Change the `<title>` and edit the Markdown inside the `<textarea>`.
3. Add a row to the table in [Slides](index.md) linking to `decks/NN-my-talk.html`.

## Slide separators

The Markdown block uses reveal.js separators:

| Separator | Meaning |
| --- | --- |
| `---` on its own line | new topic (horizontal slide) |
| `--` on its own line | next slide within a topic (vertical slide) |
| `Note:` | speaker notes for the current slide |

```markdown
### First slide

- a bullet

--

### Second slide, same topic

Note:
Only visible in the speaker view.

---

### A new topic
```

## Images

Put figures in `images/` at the repository root and reference them from a deck
with `../../images/my-figure.svg`. The path is relative to the deck's location
in the built site.

## Previewing locally

```pwsh
dotnet tool update -g docfx
docfx docfx.json --serve
```

Then browse to <http://localhost:8080>. Decks are served from
`/slides/decks/NN-my-talk.html`.
