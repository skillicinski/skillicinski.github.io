---
title: "bo"
date: 2025-05-14
draft: false
description: "A CLI tool that collects web content into a local markdown knowledge tree, compiles topics with an LLM, and answers questions with citations"
tags: ["rust", "cli", "llm", "productivity", "knowledge-management"]
categories: ["Tools"]
---

## Overview

I wokrked on bo to solve my habitual tab hoarding and link collecting. I used to try different products to remind myself to consumer various interesting content later; blogs, videos, podcasts, etc. Those attempts always ended the same way: I wouldn't find the time to properly digest any of it.

What I hoped to achieve was to feel invested in the solution to the problem itself. Being exposed to LLMs and agents through work, I also thought that I could leverage what they really excel at, while being very economical with context.

The inspiration for how to put it together comes from [Andrej Karpathy's "LLM wiki" idea](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f): skip RAG and vector databases entirely. Keep everything as legible local files and let LLMs follow an indexing and schema convention to build up and maintain knowledge base gathered from the raw documents.

## Tech Stack
- Rust
- OpenAI API
- pi Coding Agent

## Architecture

- **domain/** — Pure value types for the knowledge base: `Tree`, `Leaf`, `Branch`, `Index`, `Slug`, `Frontmatter`.
- **engine/** — content extraction with `trafilatura`, quality classification, LLM document summary generation and a provider-agnostic LLM calling layer (trait-based, currently OpenAI).
- **adapters/** — Protocol-specific extensions, eg. YouTube pulls captions.
- **cli/** — Orchestration from a single entrypoint, each command supports `--json` output.

## Key Outcomes
- CLI with a `--json` flag for each command that provides machine-friendly output
- `seed`, `config` & `raze` commands for managing knowledge base lifecycle
- `collect`, `compile` & `query` commands to demonstrate the "product loops"
- "adapter" extensions, eg. for downloading YouTube video captions using `collect`
- OpenAI provider included in first release, defaults to `gpt-4o-mini`

---

Source on [GitHub](https://github.com/skillicinski/bo).
