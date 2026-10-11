---
name: plain-tickets
description: Rewrite tickets (Linear, GitHub issues, or repo ticket files) to remove jargon and made-up names, replacing them with plain words anyone on the team understands. Edits the tickets directly.
---

# Remove jargon and made-up names from tickets

Tickets drift into private vocabulary. Someone coins a name for an idea ("minds", "lanes", "the floor", "evidence card", "exposure set") and later tickets use it as if everyone knows what it means. A new reader, or an agent picking up the ticket, then has to guess. This skill finds those words and rewrites each ticket in plain language. It edits the tickets directly, without asking first.

## What to replace

- **Made-up names.** Words invented for this project that a newcomer wouldn't know: coined nouns ("mind", "lane", "librarian"), metaphors used as terms ("the floor", "shop"), and invented compounds ("intent owner", "exposure delta").
- **Jargon.** Terms of art a product-minded teammate wouldn't use: "idempotent", "p95", "projection", "control log", "quorum", "principal", "compaction".
- **Unexplained acronyms and internal shorthand**, such as "ACP", "v1 bets", "DM read gate".

## What to keep

- **Names people see in the product.** Keep a button label, screen name or setting name exactly as the UI shows it, and put it in quotes.
- **Real outside names**, such as products, libraries, companies and standards (Claude Code, Codex, Convex, Git, macOS).
- **Code identifiers in engineering sections.** File paths, function names, package names and daemon names (`hostd`, `local-agent.ts`) stay under engineering notes, where engineers need them. Remove them from the product half (outcome, done when, out of scope, constraints).
- **Ticket links and quotes from other people.**

## Steps

1. **Scope.** Use the tickets the person names. Otherwise, use every open ticket in the team or project they mean, skipping Done, Canceled and Duplicate ones.
2. **Read every ticket in full.** For more than about 30 tickets, split them into chunks of about 30 for subagents. Collect every candidate term across all tickets first, so each term is replaced the same way everywhere.
3. **Build a glossary** of every term to replace. For each one, record the term, what it actually means (from the tickets that define it, or from the code if needed), and the plain replacement. Prefer a short ordinary phrase that says what the thing does, such as "lane" → "a coding task running on a member's Mac", or "intent owner" → "the person who asked for the work". Once a long replacement has been used in full in a ticket, a shorter plain form is fine for the rest of that ticket. Don't coin a new term to replace an old one.
4. **Rewrite each ticket.**
   - Replace every glossary term in the product half. In engineering notes, replace it in prose but keep real code identifiers.
   - Keep every fact, requirement, number, link and open question. Change words, not meaning or scope.
   - If a term's meaning is unclear and the tickets and code don't settle it, leave it in place and add an open question: "What does '<term>' mean here?"
   - Don't touch title, status, priority, labels, project, assignee or relations unless the title itself carries a made-up name. In that case, retitle it plainly.
5. **Save** each ticket directly. In Linear, `save_issue` keeps description history, so any edit can be restored from the issue menu. Before the first edit, save a copy of each original description to a backup folder (the shared project folder if there is one).

## Report

- Write the glossary (term, meaning, replacement, and how many tickets used it) to a Markdown file next to the backups.
- In chat, say how many tickets were rewritten, how many terms were replaced, and which terms were left in place as open questions. Link the glossary.
