---
layout: post
title: "Clear Writing"
subtitle: "Where most writing guides stop at advice, this one enforces it"
categories: projects
tags: [claude-code, automation, writing, python]
new: true
---

![Slop doesn't ship](/assets/images/projects/clear-writing.png)

Most writing skills are lists of guidelines: write clearly, avoid jargon, get to the point. LLMs don't reliably follow guidelines just because they've read them — they can report a rule as applied while quietly breaking it in the same paragraph. This skill treats that as the actual problem to solve. Instead of one pass of guidance, it runs a fixed ruleset through several rounds of drafting and then checks the result mechanically, with a standalone Python script, before anything is shown. Roughly a third of the project is enforcement rather than advice.

**Tech Stack:** Claude Code Skills · Python (stdlib only) · Markdown-based rule references

**What makes it different**

* **Enforced, not suggested.** A `check.py` script scans every draft for concrete violations — em dashes, invented facts, unsupported claims, passive voice, buzzwords — independent of whatever the model claims it did. Guidelines alone don't survive contact with an LLM; a mechanical check does.
* **Built from real newspaper practice, not intuition.** The ruleset comes from analyzing roughly 30 articles across known newspapers and outlets (The Economist, FT, Reuters, HBR) to extract what good writing actually measures at — sentence length, structure, bullet use — rather than what style guides merely claim.
* **Structured thinking, not just cleaner sentences.** Beyond wording, it applies Barbara Minto's Pyramid Principle and SCQA to surface the strongest point first and make sure the key message actually lands, alongside other structural helpers for management summaries, client updates, and technical write-ups.

**Highlights**

* Style-only vs. full-rewrite modes, with a word-loss guard to catch unwanted compression
* Six always-on ground rules promoted to `CLAUDE.md`, with the full ~20,000-word ruleset loaded only on demand
* A drift test keeps documented rules and enforced checks from silently diverging
* Six documented eval cases tied to real failures observed during development

[View the code and full write-up on GitHub →](https://github.com/ThorstenWeberGER/writing-skills)
