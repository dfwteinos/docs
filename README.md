# Lope Product Guide

This repository powers the public documentation for **Lope**, the recruiter-first platform formerly known as Kaktus. Every page in `projects/lope` is written for recruiters, sourcers, and client partners who use the product—not for engineers.

## Editing the docs locally

1. Install the [Mintlify CLI](https://www.npmjs.com/package/mint):  
   `npm i -g mint`
2. From the repo root (where `docs.json` lives), run:  
   `mint dev`
3. Visit `http://localhost:3000` to preview your changes live. The preview reloads automatically whenever you save a file.

## Publishing changes

Push commits to the default branch. Our connected Mintlify project picks up changes automatically and redeploys the hosted docs with the latest Lope branding.

## Writing guidelines

- Keep the audience in mind: recruiters, hiring managers, and collaborators.
- Use the style rules in `.cursor/rules.md` (plain language, outcomes first, minimal jargon).
- Reference real UI labels and flows inside Lope so readers can follow along without digging into code.

## Need help?

- Run `mint update` if the CLI misbehaves.
- Check `docs.json` if a page 404s locally.
- Contact the Lope product team in Slack if you need access to brand assets (also stored under `Lope_zip/` in this repo).
