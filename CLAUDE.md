# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Single-file browser game: `tictactoe.html`. Open it directly in any browser — no build step, no dependencies, no server required.

## Architecture

Everything lives in one HTML file with three co-located sections:

- **CSS** (`<style>`) — Dark theme (`#1a1a2e` background). Color palette: red `#e94560` for X, teal `#a8dadc` for O. Grid is 3×3 via CSS Grid, 120px cells.
- **HTML** — Static 9-cell board (`data-i="0"` through `data-i="8"`), score display, status line, restart button.
- **JS** (`<script>`) — All game logic. Key globals: `board` (9-element array), `current` (active player), `over` (game-ended flag), `scores` object `{X, O, T}`. Win detection uses a hardcoded `WINS` array of the 8 possible winning index triplets.

## Git workflow

A Stop hook in `~/.claude/settings.json` automatically stages all changes, commits with a message listing the changed files, and pushes to `origin master` at the end of every Claude session. Manual commits are not needed unless a specific message is required.
