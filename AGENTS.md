# Repository Guidelines

## Project Structure & Module Organization

This repository is a static, single-page quiz. The full app lives in `index.html`, including markup, inline CSS, inline JavaScript, embedded data URI images, and CDN-loaded browser libraries. There is currently no `src/`, `tests/`, `assets/`, or package manifest. If the project grows, split reusable JavaScript into `src/`, move large images to `assets/`, and keep `index.html` focused on page structure.

## Build, Test, and Development Commands

No dependency install or build step is required.

- `open index.html` previews the page directly in a browser on macOS.
- `python3 -m http.server 8000` serves the repository locally; open `http://localhost:8000` to test browser behavior closer to production.
- `git status --short` checks the working tree before and after edits.

Because the page loads Google Fonts, QRCode.js, and html2canvas from CDNs, test with network access when changing rendering, sharing, QR code, or screenshot behavior.

## Coding Style & Naming Conventions

Keep HTML, CSS, and JavaScript readable within the single file. Match the existing style: two-space indentation in CSS blocks, compact CSS custom properties under `:root`, camelCase JavaScript functions and variables, and uppercase constants such as `QUESTIONS`, `RESULTS`, and `SHARE_URL`. Preserve Thai copy exactly unless the change is explicitly copy-related. Avoid adding frameworks or build tooling for small edits.

## Testing Guidelines

There is no automated test suite. Manually verify quiz flows in a browser after every behavior change: start the quiz, answer all questions, view the result card, restart, test share links, confirm the QR code renders, and check mobile-width layout in responsive tools. For visual changes, test at desktop and phone widths.

## Commit & Pull Request Guidelines

Recent commits use short, imperative summaries, for example `Use canonical share URL pointing to shoutkol.com/influencer-quiz` and `Initial commit: add influencer quiz`. Follow that style: describe the user-visible change in one sentence. Pull requests should include a concise summary, manual test notes, screenshots for UI changes, and any production URL or campaign detail affected by the change.

## Agent-Specific Instructions

Keep changes surgical. Do not reformat the entire embedded HTML or regenerate large data URI assets unless the requested change requires it.
