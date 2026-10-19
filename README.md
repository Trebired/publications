# Trebired Publications

The blog posts and case studies the Trebired organization publishes, in English and Czech, as the single source every consuming site reads at build time.

This repository owns the wording of each post and case study, its author, its publication date, and for a case study the client it was written about. Consumers own their routing, their rendering, the cover a post is shown with when it carries none, and their fallback behaviour. It does not own policies or other standing documents, which live in `Trebired/meta`, and it does not own changelogs, which ship in the repository of the software they describe.

## Documents

| Folder | Covers |
| --- | --- |
| `blog/trebired-goes-public` | The organization and its website going public, what is already published, and what comes next |
| `case-studies/trebired-com` | The organization's own site: where its text lives, how prices are converted, how its pictures are made, and what was not measured |

## Structure

```txt
blog/
  <post>/
    en.md
    cs.md
    cover.png
case-studies/
  <study>/
    en.md
    cs.md
```

The top folder is the kind, and a consumer serves each kind at its own route. The folder inside it is the consumer-facing slug in kebab-case: `blog/trebired-goes-public/` is served at `/blog/trebired-goes-public`, and `case-studies/trebired-com/` at `/case-studies/trebired-com`. Renaming a folder breaks every link that points at it, so a published folder is never renamed.

Language files are named by ISO 639-1 code. There is no `index.md`, no locale suffix, and no post file at the repository root.

`cover.png`, `cover.jpg`, `cover.webp` or `cover.svg` is optional and is the image the post or study is shown with. One cover per folder, shared by every language.

## Format

Every file opens with front matter and then the text.

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

`title` is the rendered heading. `lead` is one line, shown under the title and in every list. `published` is an ISO date, `YYYY-MM-DD`, and orders each kind newest first. `author` is the GitHub login of the person who wrote it. All four are required.

`client` is required in a case study and nowhere else. It names who the work was done for, and it is written only with that client's agreement. A study that cannot name its client is not published here.

`updated` is optional and is an ISO date. It is set when the text changes in substance after publication. Fixing a typo does not set it.

A blank line separates paragraphs, and each paragraph becomes one rendered block. The first paragraph is rendered as the opening of the post.

`##` opens a section and its heading is rendered as written. A case study is written in sections; a blog post may use them and usually does not. There is no deeper level.

The rendered subset is section headings, paragraphs and links. There are no lists, tables, bold, italics, images, or code blocks. A consumer refuses a file that contains any other heading level rather than rendering part of it, and the build that reads it fails until the file is fixed.

A link is written with a comment pair, the same way as in `Trebired/meta`, so that a reader of this repository sees the words and nothing else:

```md
Read <!--tbf:link /philosophy-->the philosophy page<!--/tbf:link--> for why.
Get it from <!--tbf:link https://github.com/Trebired tab-->GitHub<!--/tbf:link-->.
```

The first token after the marker is the destination and is required. `tab` opens the link in a new tab; `reload` makes the consumer navigate fully instead of swapping the page in place.

## Language

Every post and case study ships in English and Czech, with the same sections and paragraphs in the same order. One missing either language is not published by any consumer. Both languages are written, never machine-translated.

## Consumption

`trebired.com` reads this repository when it builds. It lists the folders under `blog/` and `case-studies/` from the repository tree on `main`, fetches each language file, and publishes everything that is complete in both languages. Anything without a cover is shown with one generated from its text: the same text always produces the same image, so a cover changes only when the post does.

When the repository cannot be reached, the build keeps what it read last time instead of publishing an empty blog.

## Authoring

Posts and case studies are written by the people who maintain the organization. The author must have a profile on the team page, through `<login>/<login>/meta.json` on GitHub, for their name and portrait to appear beside the post; otherwise the post shows the login alone.

A published post or study is corrected, not rewritten. A substantive correction sets `updated` and goes in the changelog.

## What It Does Not Do

This repository does not:

- Hold policies, terms, or any other standing document. Those are in `Trebired/meta`.
- Publish a case study about a client who has not agreed to it.
- Schedule anything. A file in the repository is published at the next build.
- Carry analytics, tracking, or comment threads.
- Render anything. Layout, covers, and routing belong to the consuming site.
