# Engineering Inspiration & Useful Repositories

A curated collection of projects, tools, patterns, and builders worth studying or borrowing ideas from. The goal is not to collect links endlessly; it is to extract useful ideas and turn them into shipped work.

## Repositories and projects

### Flatpack — local-first, AI-editable personal tools
- **Project:** [Flatpack](https://github.com/ConceptPending/flatpack)
- **Original page:** https://sael.net/flatpack/#lack-coffee
- **Why it is useful:** Flatpack describes a format for small, single-file HTML tools that can run locally without a backend, build step, package installation, or network calls by default. Its stable structure is designed so a person or coding agent can inspect and safely edit the tool later.
- **Ideas worth borrowing:**
  - Build tiny, useful tools before committing to a full application.
  - Prefer local-first and low-dependency designs for personal utilities.
  - Keep purpose, inputs, outputs, constraints, and editing instructions close to the implementation.
  - Make small tools easy to inspect, test, export, and evolve.
- **Potential use in my work:** Prototype personal dashboards, calculators, trackers, and one-off workflow tools quickly. Promote a prototype into a full application only when persistence, collaboration, security, or scale genuinely requires it.
- **How to evaluate it:** Read the specification and examples, build one small utility, then assess portability, maintainability, accessibility, and whether its constraints fit the use case.
- **Status:** Worth exploring; not yet adopted as a standard.

## How to use this collection

For every entry, capture:
1. **What it does** — in one or two sentences.
2. **What is worth learning or borrowing** — a concrete pattern, not just admiration.
3. **A small experiment** — something that can be built or tested in a few hours.
4. **Outcome** — keep, adapt, or discard, with a short reason.

Prefer a small number of useful experiments over an ever-growing bookmark list. Do not adopt a tool just because it is popular.
