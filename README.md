# Trebired Publications

The posts the Trebired organization publishes, in English and Czech, as the single source every consuming site reads at build time.

This repository owns the wording of each post, its author, and its publication date. Consumers own their routing, their rendering, the cover a post is shown with when it carries none, and their fallback behaviour. It does not own policies or other standing documents, which live in `Trebired/meta`, and it does not own changelogs, which ship in the repository of the software they describe.

## Documents

| Folder | Covers |
| --- | --- |
| `trebired-goes-public` | The organization and its website going public, what is already published, and what comes next |

## Structure

```txt
<post>/
  en.md
  cs.md
  cover.png
```

The folder name is the consumer-facing slug in kebab-case. `trebired-goes-public/` is served at `/blog/trebired-goes-public`. Renaming a folder breaks every link that points at the post, so a published folder is never renamed.

Language files are named by ISO 639-1 code. There is no `index.md`, no locale suffix, and no post file at the repository root.

`cover.png`, `cover.jpg`, `cover.webp` or `cover.svg` is optional and is the image the post is shown with. One cover per post, shared by every language.

## Format

Every file opens with front matter and then paragraphs.

```md
---
title: Trebired goes public
lead: One sentence a reader sees before opening the post.
published: 2026-10-19
author: mirmachynka
---

One paragraph.

Another paragraph.
```

`title` is the rendered heading. `lead` is one line, shown under the title and in every list of posts. `published` is an ISO date, `YYYY-MM-DD`, and orders the posts newest first. `author` is the GitHub login of the person who wrote the post. All four are required.

`updated` is optional and is an ISO date. It is set when the text changes in substance after publication. Fixing a typo does not set it.

A blank line separates paragraphs, and each paragraph becomes one rendered block. The first paragraph is rendered as the opening of the post.

The rendered subset is paragraphs and links. A post has no headings, lists, tables, bold, italics, images, or code blocks. A consumer refuses a post that contains a heading rather than rendering part of it, and the build that reads it fails until the post is fixed.

A link is written with a comment pair, the same way as in `Trebired/meta`, so that a reader of this repository sees the words and nothing else:

```md
Read <!--tbf:link /philosophy-->the philosophy page<!--/tbf:link--> for why.
Get it from <!--tbf:link https://github.com/Trebired tab-->GitHub<!--/tbf:link-->.
```

The first token after the marker is the destination and is required. `tab` opens the link in a new tab; `reload` makes the consumer navigate fully instead of swapping the page in place.

## Language

Every post ships in English and Czech, with the same paragraphs in the same order. A post missing either language is not published by any consumer. Both languages are written, never machine-translated.

## Consumption

`trebired.com` reads this repository when it builds. It lists the post folders from the repository tree on `main`, fetches each language file, and publishes every post that is complete in both languages. A post without a cover is shown with one generated from its text: the same text always produces the same image, so a cover changes only when the post does.

When the repository cannot be reached, the build keeps the posts it read last time instead of publishing an empty blog.

## Authoring

Posts are written by the people who maintain the organization. The author must have a profile on the team page, through `<login>/<login>/meta.json` on GitHub, for their name and portrait to appear beside the post; otherwise the post shows the login alone.

A published post is corrected, not rewritten. A substantive correction sets `updated` and goes in the changelog.

## What It Does Not Do

This repository does not:

- Hold policies, terms, or any other standing document. Those are in `Trebired/meta`.
- Schedule posts. A post in the repository is published at the next build.
- Carry analytics, tracking, or comment threads for a post.
- Render anything. Layout, covers, and routing belong to the consuming site.
