# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository purpose

This repository is a personal collection of Claude Code **skills** — packaged instruction sets that Claude Code loads and follows for particular kinds of tasks (see `/help` or the Claude Code skills docs for how skills are invoked). There is no application code, build system, or test suite; the repository's only content is skill definitions under `skills/`.

## Structure and conventions

Skills live at `skills/<category>/<skill-name>/SKILL.md`, e.g. `skills/productivity/grill-me/SKILL.md`. When adding a new skill, follow this same `<category>/<skill-name>/SKILL.md` layout.

Each `SKILL.md` has two parts:
- **YAML frontmatter** with `name` (matches the directory name) and `description` (states what the skill does and, crucially, *when* to trigger it — this is what the skill-matching system uses to decide when to invoke the skill, so phrase it around concrete trigger phrases/situations, not just a summary).
- **Body**: the actual instructions given to Claude when the skill runs, written as direct imperative guidance (addressing Claude, not the end user).

Existing skills are written in German; match the language of a skill to its existing content if editing, and default to German unless the user requests otherwise for new skills.

## Working in this repo

There is nothing to build, lint, or test — changes are limited to creating or editing Markdown skill files. Verify a new or edited `SKILL.md` by checking that:
- the frontmatter is valid YAML with `name` and `description` present,
- the directory name matches `name`,
- the `description` clearly states the trigger condition, since that's what determines whether the skill fires.
