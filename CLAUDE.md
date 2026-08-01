# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository overview

This is a minimal static-HTML practice repository. There is no build system, package manager, linter, or test suite — the codebase is a single self-contained HTML file.

## Running the app

There are no build/lint/test commands. To view the app, open `hello-world.html` directly in a browser (or serve the directory with any static file server).

## Architecture

`hello-world.html` is a single-file to-do list app: markup, CSS, and JavaScript all live inline in this one file (no external dependencies, no bundler).

- `#task-input` / `#add-task-btn` — text input and button for adding a task; Enter in the input also submits.
- `#task-list` — the `<ul>` that tasks are appended to. There is no backing data array — the DOM (`<li>` elements) is the only state, so the list resets whenever the page reloads.
- Each task `<li>` contains a `<span>` (the task text) and a "Delete" button. Clicking the `<li>` toggles a `.completed` class (strikethrough) on the text `<span>`; the Delete button calls `event.stopPropagation()` so deleting a task doesn't also toggle its completed state.
