# Contributing

Thank you for your interest in contributing to DO NOT ENTER! This document provides guidelines for contributing to this horror experience project.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Project Structure](#project-structure)
- [How to Contribute](#how-to-contribute)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Features](#suggesting-features)
  - [Submitting Changes](#submitting-changes)
- [Horror Effect Guidelines](#horror-effect-guidelines)
- [Entity Documentation](#entity-documentation)
- [Testing](#testing)
- [Style Guidelines](#style-guidelines)

## Code of Conduct

This project follows a [Code of Conduct](CODE_OF_CONDUCT.md). Please review and adhere to it in all interactions.

## Getting Started

1. Fork the repository
2. Clone your fork locally
3. Create a feature branch from `main`
4. Make your changes
5. Test manually in a browser
6. Submit a pull request

## Development Setup

### Prerequisites

- A modern web browser (Chrome, Firefox, Edge, Safari)
- A text editor (VS Code recommended)
- Optional: Node.js and npm (for running local server)

### Installation

```bash
# Clone the repository
git clone https://github.com/NotAzie/do-not-enter.git
cd do-not-enter

# Install dependencies (optional, for local server)
npm install

# Start local development server
npm start

# Open in browser
# http://localhost:8080
```

### Alternative: Direct Open

You can also open `index.html` directly in your browser by double-clicking it or dragging it into a browser window.

## Project Structure

```
do-not-enter/
├── index.html           # Main HTML file with all content, styles, and scripts
├── package.json         # Node.js project configuration (for development server)
├── .gitignore          # Git ignore rules
├── LICENSE             # MIT license
├── README.md           # Project overview and usage
├── CONTRIBUTING.md     # This file
├── CODE_OF_CONDUCT.md  # Community standards
├── SECURITY.md         # Content warnings and security
├── CHANGELOG.md        # Version history
├── ROADMAP.md          # Future development plans
├── TODO.md             # Known issues and improvements
├── assets/
│   ├── screenshots/    # Screenshots for documentation
│   └── sounds/         # Audio files (future)
└── docs/
    └── ARCHITECTURE.md # Technical documentation
```

### Key Components in index.html

- **CSS Styles**: All styling in `<style>` tag (consider extracting to separate file for larger projects)
- **HTML Content**: Entity profiles, experiment logs, navigation
- **JavaScript**: HorrorEngine class with all interactive systems

## How to Contribute

### Reporting Bugs

If you encounter a bug, please report it by opening an issue:

1. Check if the bug has already been reported
2. Include:
   - Browser and version
   - Operating system
   - Steps to reproduce
   - What you expected vs what happened
   - Screenshots if applicable

### Suggesting Features

We welcome suggestions for new horror effects, entities, or improvements:

1. Check if similar feature has been suggested
2. Describe the feature and its purpose
3. Explain how it enhances the horror experience
4. Consider whether it fits the project's tone and style

### Submitting Changes

1. Create a branch: `git checkout -b feature/your-feature-name`
2. Make your changes
3. Test in multiple browsers if possible
4. Ensure changes don't break existing functionality
5. Commit with clear messages
6. Push and create a pull request

#### Pull Request Checklist

- [ ] Changes work as intended
- [ ] No console errors introduced
- [ ] Maintains project's horror aesthetic
- [ ] Follows existing code style
- [ ] Tested in at least one browser
- [ ] Documentation updated if needed

## Horror Effect Guidelines

When adding new horror effects, consider:

### 1. Build Tension Gradually

Effects should escalate, not overwhelm immediately. The horror level system should feel natural.

### 2. Respect User Agency

Users should feel they have some control. Avoid effects that:
- Prevent navigation away from the page
- Hijack browser functions
- Cause genuine distress

### 3. Consider Accessibility

- Don't rely solely on audio (provide visual alternatives)
- Consider photosensitivity (avoid rapid flashing)
- Allow users to disable certain effects if possible

### 4. Maintain Atmosphere

Effects should enhance the horror atmosphere, not feel random or disconnected.

### 5. Test Thoroughly

Horror effects can behave differently across browsers. Test your changes.

## Entity Documentation

When adding new entities to the archives:

### Format

Follow the existing entity document structure:

```html
<div class="document">
    <div class="document-header">
        <div class="document-title">ENTITY-XXX - NAME</div>
        <div class="document-subtitle">Containment Class: <span class="keter">CLASS</span></div>
    </div>
    <div class="document-section">
        <h3>CONTAINMENT PROCEDURES</h3>
        <p>Description of containment...</p>
    </div>
    <div class="document-section">
        <h3>DESCRIPTION</h3>
        <p>Physical description and behavior...</p>
    </div>
    <div class="document-section">
        <h3>ADDENDUM XXX-X</h3>
        <p>Incident reports, experiment results, etc...</p>
    </div>
    <div class="document-footer">
        <p>File last updated: ██/██/████</p>
    </div>
</div>
```

### Containment Classes

- **KETER**: Difficult to contain, requires significant resources
- **EUCLID**: Unpredictable but containable
- **SAFE**: Easily contained (not used currently)

### Writing Style

- Use clinical, scientific tone
- Redact sensitive information with ███
- Include incident reports and experiment logs
- Build mystery and unease

## Testing

Since this is a horror experience, automated testing is limited. Focus on:

### Manual Testing Checklist

- [ ] Page loads without errors
- [ ] Navigation works (anchor links)
- [ ] Horror effects trigger appropriately
- [ ] Audio works (if enabled)
- [ ] Visual effects display correctly
- [ ] No console errors
- [ ] Works on different screen sizes
- [ ] Night mode activates correctly
- [ ] Konami code triggers ultimate scare

### Browser Testing

Test in at least:
- Chrome/Chromium (primary)
- Firefox
- Safari (if available)
- Mobile browser (if applicable)

## Style Guidelines

### CSS

- Use CSS custom properties (variables) for colors
- Maintain the dark theme with red accents
- Use Courier New or monospace fonts for horror feel
- Add comments for complex effects

### JavaScript

- Follow the HorrorEngine class structure
- Use clear method names
- Comment complex logic
- Maintain horror level system consistency

### HTML

- Use semantic HTML where appropriate
- Maintain dark aesthetic
- Ensure content is readable
- Add appropriate ARIA labels if needed

---

## Questions?

If you have questions about contributing, open an issue with your question. We're happy to help!

---

**Remember: The horror must feel real, but never cross the line into genuine distress. Walk the line between terrifying and entertaining.**
