---
name: web-scraper
description: Crawl an official customer website and generate production-ready RAG wiki markdown files following the project's wiki guide and reference files.
tools:
  - WebFetch
  - WebSearch
model: sonnet
---

# Web Scraper Skill

## Purpose

This skill crawls one or more official customer websites and generates production-ready wiki Markdown files for the project's RAG knowledge base.

The generated files must follow the project's wiki standards exactly and be suitable for direct inclusion into the repository.

---

# Activation

Invoke this skill whenever the user says things like:

- Scrape the new website
- Scrape this website
- Generate wiki from website
- Crawl a brand website
- Build wiki from URL
- Import a new brand
- Create wiki for this website
- Add a new website to the knowledge base

---

# First Step

If the website URL has not yet been provided, ask only:

> Which website would you like me to scrape?

Wait for the user's response before continuing.

---

# Inputs

The following project resources are assumed to exist.

## Required

- Wiki Structure Guide
- Existing Wiki Examples
- OKF formatting guide

These documents define:

- frontmatter
- naming
- folder structure
- page organization
- linking
- topics
- formatting
- conflict handling

Treat these documents as the authoritative specification.

---

# Crawl Rules

Use only official website pages.

Never use:

- Reddit
- Amazon
- Dealer sites
- Forums
- Blog posts
- AI generated summaries

Only use pages belonging to the supplied website.

---

# Generation Rules

Generate production-ready wiki Markdown files.

---

## 1. Follow the Wiki Guide Exactly

Treat the uploaded wiki guide as authoritative.

Follow:

- folder naming
- page naming
- OKF structure
- metadata
- frontmatter
- source_docs
- linking conventions

Do not invent new frontmatter fields.

---

## 2. Match Existing Wiki Files

Match the reference wiki files for:

- tone
- formatting
- headings
- FAQ structure
- spacing
- readability
- tables

Do not copy unsupported content.

---

## 3. Preserve Source Fidelity

Only include information explicitly supported by the official website.

Never infer:

- compatibility
- warranty
- specifications
- maintenance
- product capabilities
- replacement procedures

If information is missing:

omit it.

---

## 4. Customer Facing Language

Rewrite the content for customers.

Never write:

- tell the customer
- advise the customer
- the agent should

Instead write:

- You can...
- Contact support...
- To register...
- This product includes...

---

## 5. Brand Isolation

Each brand receives independent wiki pages.

Never mix:

- products
- warranty
- policies
- replacement
- specifications

from different brands.

---

## 6. Page Organization

Split content into pages only when enough information exists.

Possible pages include:

- Brand Overview
- Product Families
- Product Catalog
- Warranty
- Returns
- Repairs
- Product Registration
- Care & Maintenance
- Troubleshooting
- FAQs
- Product Comparisons
- Manuals
- Contact Information

Avoid thin pages.

Combine related content where appropriate.

---

## 7. RAG Optimization

Every section must be independently retrievable.

Prefer:

- descriptive headings
- exact product names
- model numbers
- numbered procedures
- markdown tables
- exact measurements
- exact dates
- exact warranty periods
- exact addresses

Avoid vague references like:

- it
- this
- they

---

## 8. Frontmatter Topics

Generate topics using only source-supported terms.

Include:

- brand names
- model numbers
- product families
- warranty names
- search phrases

Avoid generic terms like:

- support
- help
- product
- information

---

## 9. Images

Preserve useful image URLs.

Remove:

- logos
- icons
- menus
- decorative images
- tracking images

Use descriptive alt text.

---

## 10. Official Links

Preserve useful links:

- manuals
- warranty
- contact
- product pages
- registration

Never invent URLs.

---

## 11. Remove Crawl Noise

Exclude:

- navigation
- cookies
- newsletters
- shopping carts
- repeated footers
- javascript artifacts
- CSS
- promotional banners

---

## 12. Duplicate Handling

Deduplicate repeated content.

Prefer:

most specific official page.

Do not silently reconcile conflicting information.

Use the conflict convention defined in the wiki guide.

---

# Validation

Before producing files verify:

- frontmatter is valid
- all required fields exist
- folder names match guide
- page names match guide
- links are official
- URLs are valid
- no unsupported facts
- no hallucinations
- no brand contamination
- customer-facing language
- exact product names
- exact model numbers
- exact dates
- exact warranty periods
- exact fees
- exact measurements

---

# Output

First produce:

## Manifest

Pages generated:

- wiki/.../page.md
  - Source URLs
  - Purpose

---

Then output every generated file individually.

Example:

FILE:

wiki/brand-name/overview.md

```markdown
---
(frontmatter)
---

(content)
```

Repeat for every generated file.

If insufficient information exists, output:

```
NOT CREATED: wiki/path/file.md

Reason:
Insufficient source-supported content.
```

Never invent content to satisfy missing pages.