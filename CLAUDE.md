# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a LaTeX-based learning notes repository containing mathematical notes on optimization, machine learning, and diffusion models. The notes are written in Chinese.

## Building the PDF

The project uses LaTeX with Chinese (ctex) support:

```bash
# Compile with pdflatex + bibtex (standard LaTeX build)
pdflatex note.tex
bibtex note
pdflatex note.tex
pdflatex note.tex

# Or use latexmk for automatic rebuilds
latexmk -pdf note.tex
```

**Build dependencies:** TeX Live or MiKTeX with ctex, amsmath, tcolorbox, and hyperref packages.

## Repository Structure

- **note.tex** — Main LaTeX file that inputs all chapters
- **chapter/chapter1.tex** — Optimization (凸函数、严格凸、强凸、梯度不等式、次梯度)
- **chapter/chapter2.tex** — Diffusion models (DDPM, DDIM 从公式推导到采样)
- **chapter/chapter3.tex** — Agent (Lean 4 语义检索、混合排序、LLM 应用)
- **chapter/chapter4.tex** — PDE (分部积分公式、Green 公式)
- **chapter/chapter5.tex** — Information Theory (熵、自信息量、信源编码)
- **chapter/appendix.tex** — Appendix
- **references.bib** — Bibliography entries (BibTeX format)
- **note.bbl** — Bibliography generated during build (gitignored)
- **fig/**** — Figures and images directory
- **note.pdf** — Compiled PDF output (committed to repo)
- **index.html** — GitHub Pages viewer that embeds note.pdf

## Key Conventions

- **Chinese support:** Uses `\usepackage[UTF8]{ctex}` for Chinese typesetting
- **Custom math macros:** note.tex defines extensive math shortcuts (e.g., `\def\x{{\bm x}}`, `\def\R{{\mathbb R}}`)
- **Theorem boxes:** Uses tcolorbox with `mytheorem`, `mydefinition`, `myproposition` environments
- **Bibliography:** References are cited with `\cite{key}`; uses committed `note.bbl` with SMALLCAPS style

## Git Workflow

- `.gitignore` excludes all `.tex`, `.aux`, `.log`, and other LaTeX build artifacts
- Only the compiled `note.pdf` is committed, not the source `.tex` files
- `note.bbl` is gitignored and generated during build
- Commit messages follow: `docs: <description>` or `fix: <description>`
- GitHub Pages deployment at `conanxu-math.github.io/no-end-for-learning/` serves `note.pdf` via `index.html`
