# Changelog

All notable changes to Trebired Publications will be documented here.

This repository follows semantic versioning.

## 3.0.0

- Breaking: every post and case study is written in sections. A file without a `##` section is refused, where a post written as plain paragraphs was accepted before.
- Split `blog/trebired-goes-public` into seven sections in English and Czech. The text did not change.

## 2.0.0

- Breaking: posts moved under `blog/`. `trebired-goes-public/` is now `blog/trebired-goes-public/`; a consumer that read the old folder finds nothing there. The slug, and the route a consumer serves it at, did not change.
- Added case studies under `case-studies/`, and the first one, `case-studies/trebired-com`, in English and Czech: the organization's own site, where its text lives, how its prices are converted, how its pictures are made, and what was not measured.
- Added `client` to the front matter of a case study, and `##` sections to the format of both kinds. Any other heading level is refused.

## 1.0.0

- Added `trebired-goes-public` in English and Czech: the organization and its website going public, what is already published, and what comes next.
