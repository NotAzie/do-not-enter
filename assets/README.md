# Assets Directory

This directory contains static assets for the DO NOT ENTER project.

## Structure

```
assets/
├── screenshots/    # Screenshots for documentation, README, etc.
└── sounds/         # Audio files (future expansion)
```

## Screenshots

Screenshots should be added to `assets/screenshots/` for use in documentation.

### Recommended Screenshots

1. **Banner/Landing**: Full page screenshot of the home/hero section
2. **Entity Archive**: Screenshot of an entity document
3. **Nightmare Mode**: Screenshot showing UI with nightmare mode active
4. **Mobile View**: Screenshot of mobile layout

### Screenshot Guidelines

- Use dark theme screenshot (matches actual experience)
- Include browser chrome for context (optional)
- PNG format recommended
- Reasonable file size (under 500KB if possible)
- Named descriptively: `banner.png`, `entity-document.png`, etc.

## Sounds

The `assets/sounds/` directory is reserved for future audio file expansion.

Currently, all audio is generated programmatically using Web Audio API and Speech Synthesis. Future versions may include:

- Custom sound effects
- Pre-recorded whisper samples
- Background soundscapes
- Music tracks

### Audio Format Recommendations

- **Format**: WAV or MP3
- **Quality**: 44.1kHz, 128kbps+ for music, 22kHz for effects
- **Duration**: Keep effects short (under 5 seconds)
- **Volume**: Normalize to consistent levels

## Adding New Assets

When adding new assets:

1. Place in appropriate subdirectory
2. Use lowercase filenames with hyphens: `my-file.png`
3. Add to version control (not gitignored)
4. Update references in code if needed
5. Add to README or documentation if applicable
