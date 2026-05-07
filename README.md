# HubSpot to GitBook Knowledge Base Sync

This repository powers a one-way sync flow:

**HubSpot Knowledge Base -> GitHub Markdown -> GitBook**

When articles are synced, they are converted to Markdown, committed to this repo, and then published by GitBook from the connected branch/path.

---

## What This Repo Is For

- Keep HubSpot as the source of truth for KB content
- Mirror articles into GitHub as versioned Markdown files
- Let GitBook publish the docs site from GitHub
- Avoid bidirectional sync complexity

---

## Sync Direction

- ✅ HubSpot -> GitHub
- ✅ GitHub -> GitBook (via GitBook Git sync)
- ❌ GitHub -> HubSpot (not enabled)

---

## Prerequisites

1. HubSpot private app access token
2. GitHub personal access token (repo contents write access)
3. GitBook connected to this repository
4. Sync app configured with:
   - `HUBSPOT_ACCESS_TOKEN`
   - `GITHUB_TOKEN`
   - `GITHUB_REPO`
   - `GITHUB_BRANCH`
   - `GITHUB_DOCS_ROOT` (optional)

---

## Content Structure

Synced files are stored as:

```text
{group-slug}/{category-slug}/{article-slug}.md
