# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

A browser-based Tic Tac Toe game — single HTML file, no build step, no dependencies.

To play: open `tictactoe.html` directly in a browser.

## Architecture

Everything lives in `tictactoe.html` as a self-contained file with three sections:

- **CSS** (inline `<style>`) — layout, colour scheme, animations. Colour palette: `#e94560` (red, X), `#a8dadc` (teal, O), `#f0f4f8` (page background), `#dce8f5` (cell background).
- **HTML** — static 3×3 grid of `.cell` divs addressed by `data-i` (0–8), plus score display and restart button.
- **JS** (inline `<script>`) — all game logic. Key pieces:
  - `WINS` — hardcoded array of the 8 winning index combinations.
  - `board` (array[9]), `current` (X/O), `over` (boolean) — full game state.
  - `scores` object `{ X, O, D }` — persists across restarts within the same page session.
  - `checkWinner()` — scans `WINS`; returns `{ winner, line }` on a win, `{ winner: null }` on a draw, or `null` if the game is ongoing.
  - Click handler on each cell drives all state transitions.
  - `init()` resets board/turn/over and clears cell classes, but does **not** reset `scores`.

## Git & GitHub

- Remote: `https://github.com/edonline0521/ClaudeCodeTest`
- Commit after every meaningful change and push to keep GitHub in sync.
- Write descriptive commit messages (what changed and why, not just "update file").
