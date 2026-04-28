# Azoth

> Powered by [Azoth](https://github.com/your-org/azoth) — The Universal Agentic Toolkit

---

## Project Overview

- **Name**: Azoth
- **Language**: Python
- **Description**: The Universal Agentic Toolkit — agentic development discipline for AI-assisted projects.

## Boot Sequence

This project uses the Azoth bootloader. Every session:

1. **ACTIVATE** — Load this file, trust contract, governance rules
2. **SURVEY** — Map project state, load memory, check git status
3. **OPERATE** — Execute goal within trust boundaries
4. **HARDEN** — Capture learnings, verify integrity, close session

Run `/start` at the beginning of each session for a visual project snapshot
and routing options (next task, intake, promote, eval, or custom goal).

**Claude Code:** `hooks.SessionStart` runs `.claude/hooks/session_start_welcome.py`, which invokes `welcome.py --plain` and mirrors stdout to `.azoth/session-orientation.txt`. Default: use injected context (efficient). **Read** and paste the file verbatim only when the user asks for the full plain snapshot. **Bash** to run `welcome.py` for the **Rich** UI is allowed — the IDE may collapse output; expand for the full dashboard. **Cursor:** run `python3 scripts/welcome.py` in the **integrated terminal** for the full Rich layout; **Bash** in chat works with expand. **Full policy:** match `CLAUDE.md` **core rules 8–9** in this repo (or root-azoth scaffold).

## Project Routing

| Area | Path | Purpose |
|------|------|---------|
| Source | `src/` | Main source code |
| Tests | `tests/` | Test suite |
| Docs | `docs/` | Documentation |
| Azoth | `.azoth/` | Runtime state (memory, telemetry) |
| Kernel | `.azoth/kernel/` | Read-only governance copy (BOOTLOADER, TRUST_CONTRACT, GOVERNANCE, PROMOTION_RUBRIC) — D42 |

## Development Rules

1. **Quality > speed** — every output passes evaluation before delivery
2. **Test before deliver** — no merge without passing tests
3. **Bounded entropy** — max 10 files per turn, checkpoint in yellow zone
4. **Kernel immutability** — `.azoth/kernel/` changes only via human approval
5. **Cursor (Claude)** — Enable Settings → Rules → third-party plugin configs (loads this file, `.claude/commands/`, `agents/`, `skills/`). **Scaffold:** If you develop the Azoth repo, adapter sources live under `kernel/templates/platform-adapters/cursor/` — run `python3 scripts/azoth-deploy.py` from that checkout after edits. **Consumer install:** You usually do **not** have a repo-root `kernel/templates/` tree; adjust **`.cursor/rules/*.mdc`** in place or re-run install from an Azoth checkout. PreToolUse hooks do not run in Cursor; `.cursor/rules/claude-code-parity.mdc` simulates scope and pipeline gates. For delivery pipelines (`/auto`, `/deliver`, `/deliver-full`), use the **`Task`** tool with `subagent_type` matching each stage per `skills/subagent-router/SKILL.md` — do not role-play every stage in the main chat when `Task` is available.

## Coding Standards

- **Language**: Python
- **Formatting**: ruff format + ruff check
- **Tests**: pytest
- **Types**: Type hints on public functions
- **Comments**: Only for "why", never for "what"

## Installed Azoth Components

- Kernel: v0.1.4.0
- Skills: see skills/
- Agents: see agents/
- Pipeline presets: see pipelines/

## Memory

- Episodes: `.azoth/memory/episodes.jsonl`
- Patterns: `.azoth/memory/patterns.yaml`
- Telemetry: `.azoth/telemetry/session-log.jsonl`
