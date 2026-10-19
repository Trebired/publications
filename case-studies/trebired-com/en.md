---
title: trebired.com, the organization's own site
lead: A site built from the organization's own packages, with every word and every price kept where a reader can check it.
published: 2026-10-19
author: mirmachynka
client: Trebired
---

## The problem

The organization needed a site that says what it is, what it builds, what it refuses to build and what it charges, and every one of those claims had to be checkable by someone who does not take our word for it. The site is also the first piece of work a client sees, so it had to be built to the standard the organization sells, from the organization's own packages, and published in full like everything else.

## The text lives outside the site

The policies, the philosophy, the standards and the handbook are written in a public repository, <!--tbf:link https://github.com/Trebired/meta tab-->Trebired/meta<!--/tbf:link-->. Posts and case studies, this one included, are written in <!--tbf:link https://github.com/Trebired/publications tab-->Trebired/publications<!--/tbf:link-->. The site reads both when it is built and keeps the last copy it read when GitHub cannot be reached, so a network failure cannot empty a page.

The cost is deliberate. A change to a policy reaches the site only on the next build, and the text format is small: headings, paragraphs and links. Anything a consumer does not render would be dropped without a trace, so the format refuses it instead.

## A price is a number

Every price is a number in Czech koruna, declared once. The site converts it for the language being read with the European Central Bank's daily reference rates, fetched when the site is built, and formats it the way that language writes money. A ceiling rounds down and a floor rounds up, so a converted price never claims more than the original does.

## Pictures that do not have to be maintained

The illustrations are drawn in the browser as risograph prints: separate ink layers, halftone screens and a slight misregistration, using p5.riso. A print is drawn once and kept for the rest of the visit, and nothing moves for a reader who asks for reduced motion.

Covers for posts and case studies are generated from their own text when the site is built. The same text always produces the same image, so a post needs no picture to be published and its cover changes only when its words do.

## Fixed where the problem was

When running text came out smaller than the pages needed, the size was not overridden in the site. It came from a constant in the organization's frontend package, so the package now reads paragraph size from its own text scale and a site chooses the step. The same rule held throughout the build: a problem that belongs to a package is fixed in the package, and every other site built on it gets the fix too.

## What shipped, and what was not measured

The site, its English and Czech text, and every document behind it are public. It carries no trackers and runs no analytics. Load times and page weight were not measured for this study, so it makes no claim about either.
