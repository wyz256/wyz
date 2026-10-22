# AGENTS.md

This is a **static HTML/CSS practice repository** (no build tools, package managers, or tests). All files are standalone HTML pages with inline/internal CSS.

## Project Overview

- **Type**: Frontend learning/practice exercises for "Advanced Web Design"
- **Tech**: Pure HTML5 + CSS3 (no JavaScript frameworks, no CDN usage)
- **Files**: Individual HTML lesson files (2-1.html through 11-1.html) plus `四级项目/` (project work)
- **Entry**: `index.html` is a portfolio landing page linking all exercises

## Key Commands

This repo requires no installation/build commands. To view work, simply open HTML files in a browser.

- **Serve locally** (recommended for proper file loading): Use any static server, e.g.
  ```bash
  python -m http.server 8000
  # then visit http://localhost:8000
  ```

## Repository Structure

- Root contains numbered practice files (`2-1.html`, `3-1.html`, `3-2 css.html`, ..., `11-1.html`, `10-1.html`, `10-2.html`, `10-3.html`, `10-4.html`)
- `index.html` - Portfolio/index with links to all practice pages and original prompt text
- `四级项目/` - Project work (includes its own `index.html`)
- `css.css` - Shared stylesheet (minimal usage)
- `img/` - Image assets referenced by exercises

## Conventions

- **Naming**: Files use Chinese names in some cases (e.g. `5-1 层叠与继承.html`, `11-1.html`) - preserve exact filenames when creating/editing links
- **Naming convention**: All CSS class names, id names, and JS variables must start with `wyz_` (supersedes the earlier `wang_` prefix; existing files may still contain `wang_` names - do not rename them unless explicitly requested)
- **Author comment**: Every HTML page must include a comment in the form `<!-- 姓名：王宇智，日期：YYYY-MM-DD，功能名称：页面功能名称 -->`, placed near the top of the page (inside `<head>` or right after `<body>`)
- **Navigation**: Every newly created HTML file must include a hyperlink back to the homepage `index.html` (e.g. "← 返回首页")
- **Prompt logging**: Every prompt is appended to `wang_prompt.md` (never overwritten) before execution, including time, model, and prompt content
- **Code style**: Native HTML/CSS/JavaScript only - no third-party libraries and no CDN resources. Icons must come from the local iconfont package in `font/font_5244705_jfikdi7y3ca/`: link `iconfont.css` and call icons via `<span class="iconfont icon-xxx"></span>` (see 13-3.html), or inline the SVG symbol from `iconfont.js` via `<svg><use xlink:href="#icon-xxx"></use></svg>` (see 13-4.html). Never reference online CDNs or icon libraries
- **Encoding**: UTF-8, Chinese content (zh-CN)
- **Styling**: Inline/internal CSS preferred for standalone exercises; external css.css exists but exercises mostly self-contained

## Working Guidelines

- This is a static educational repo - no linting, typechecking, or test commands exist. Do **not** add build tooling unless explicitly requested.
- When adding new pages, update `index.html` links grid to maintain the portfolio navigation.
- Preserve the original prompt text in `index.html` (line ~419) as-is.
- Keep changes minimal and focused on the requested task.

## Notes

- No configuration files (`package.json`, `opencode.json`, CI, etc.) exist in this repo.
- No existing `AGENTS.md`/`CLAUDE.md` instruction files found - this file establishes repo-specific guidance.
- Exercises cover HTML structure, CSS fundamentals, box model, flexbox, layout, CSS3 selectors, transitions, animations, responsive (media queries), and CSS units.