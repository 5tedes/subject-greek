# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

GFL-Flashcards is an educational web application for learning Greek at A1 beginner level. It targets Year 1, Semester 1 (Y1S1) high school Greek language curriculum.

## Development

This is a static HTML project with no build system. Files can be opened directly in a browser or served via any static file server.

To serve locally:
```bash
python3 -m http.server 8000
# Then open http://localhost:8000
```

## Architecture

- **index.html** - Main flashcards interface with 40 cards covering introductions, location/living, verb conjugation, and numbers
- **y1s1/** - Semester-specific content folder
  - **flashcards-beginner.html** - Extended flashcard set with 7 categories (numbers, directions, positions, places, school items, articles, verbs)
  - **practice-exam.html** - Comprehensive practice test (Pokemon-themed)
  - **practice-test-2.html** - Alternative practice test with multiple sections

Each HTML file is self-contained with inline CSS and JavaScript. No external dependencies.

## Key Patterns

**Flashcard data structure:**
```javascript
{ front: "Greek text", back: "English translation", category: "category-name" }
// Extended format includes: main, subtitle, category
```

**Core functionality in each flashcard file:**
- Category filtering via button clicks
- Card navigation (Previous/Next/Shuffle)
- Flip animation with CSS 3D transforms (perspective + rotateY)
- Keyboard support (Arrow keys, Space to flip)

## Content Guidelines

- Greek text uses UTF-8 encoding
- Include romanized pronunciation in subtitle where helpful
- Categories should group related vocabulary (verbs, numbers, places, etc.)
- Maintain consistent card styling across flashcard files
