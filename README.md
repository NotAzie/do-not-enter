# DO NOT ENTER

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

**YOU SHOULDN'T BE HERE.**

This website contains classified information about entities that should not exist. Proceed at your own risk.

![DO NOT ENTER Banner](assets/screenshots/banner.png)

---

## ⚠️ WARNING ⚠️

**This experience may contain:**
- Sudden loud noises and audio disturbances
- Disturbing imagery and themes
- Psychological manipulation
- Jump scares
- Paranoia-inducing effects

**If you are sensitive to horror content, do not proceed.**

---

## Features

### 🏚️ The Horror Engine

A sophisticated JavaScript engine that creates an adaptive, personalized horror experience:

- **Horror Level System**: Dynamically adjusts intensity based on user behavior, time of day, and visit history
- **Adaptive Audio**: Ambient noise, whispered messages using Web Speech API, EVP-style audio visualization
- **Visual Distortions**: Screen static, shadow figures, peripheral vision faces, screen melt effects, glitch animations
- **Psychological Manipulation**: Paranoia mode (text replacement), fake system notifications, fake security alerts
- **Biometric Response**: Mouse tracking, inactivity detection, device orientation/shake detection
- **Personalization**: Uses your name (if provided), remembers returning visitors, adjusts for night time
- **Easter Eggs**: Konami code triggers ultimate scare sequence

### 📁 SCP-Style Classified Archives

Immersive containment files for fictional entities:

- **ENTITY-001 - THE HUSK**: A skinless humanoid that mimics voices of missing personnel
- **ENTITY-002 - THE SMILING MAN**: An entity with an impossibly wide smile that knows your secrets
- **ENTITY-003 - THE STATIC**: Television static that contains humanoid shapes - prolonged exposure causes severe psychological effects

### 🎯 Interactive Elements

- **Nightmare Mode Toggle**: Activate maximum horror intensity
- **"Are You Alone?" Button**: Triggers personalized scare
- **"DON'T CLICK" Button**: Psychological manipulation - it appears randomly
- **Hidden Messages**: Appear in your peripheral vision
- **Whispers**: Audio messages that seem to come from nowhere
- **EVP Meter**: Visualizes "electronic voice phenomena"

### 🎨 Visual Effects

- Blood drip overlay
- TV static overlay
- Glitching text
- Screen flicker
- Bloody cursor replacement
- Shadow figures in periphery
- Atmospheric color scheme (dark with red accents)

---

## Quick Start

### Local Development

```bash
# Clone the repository
git clone https://github.com/NotAzie/do-not-enter.git
cd do-not-enter

# Option 1: Use a local server (recommended)
npx http-server -p 8080

# Option 2: Open directly in browser
# Double-click index.html or drag it into your browser
```

Then open `http://localhost:8080` in your browser.

### What to Expect

1. **First Visit**: You'll see a classified archives landing page with dark, atmospheric design
2. **Exploration**: Navigate through entity profiles and experiment logs
3. **Tension Building**: The horror engine gradually increases intensity based on your actions
4. **Audio**: If you allow audio, you'll hear whispers and ambient noise
5. **Scares**: Various scare triggers will activate based on the horror level
6. **Paranoia**: Text on the page may slowly change if nightmare mode is active

---

## The Horror Engine Architecture

```
DO NOT ENTER/
├── index.html           # Main page with all content and styles
├── package.json         # Project configuration
├── .gitignore          # Git ignore rules
├── LICENSE             # MIT license
├── README.md           # This file
├── CONTRIBUTING.md     # Contribution guidelines
├── CODE_OF_CONDUCT.md  # Community standards
├── SECURITY.md         # Security and content warnings
├── CHANGELOG.md        # Version history
├── ROADMAP.md          # Future development
├── TODO.md             # Known issues and improvements
├── assets/
│   ├── screenshots/    # Demo screenshots
│   └── sounds/         # Audio assets (future)
└── docs/
    └── ARCHITECTURE.md # Technical documentation
```

### Horror Engine Systems

| System | Description | Trigger |
|--------|-------------|---------|
| **Ambient Audio** | Background noise + whispered messages | Always active (if audio enabled) |
| **Horror Level** | Dynamic intensity scaling | User behavior, time, history |
| **Peripheral Faces** | Faces appear opposite cursor | High horror level + mouse movement |
| **Shadow Figures** | Dark humanoid silhouettes | Medium horror level + random |
| **Static Overlay** | TV static flicker effect | High horror level + random |
| **Screen Melt** | Blood-like visual distortion | Very high horror level + random |
| **Paranoia Mode** | Text replacement on page | Nightmare mode + high horror level |
| **Fake Notifications** | Fake system alerts | Medium horror level + random |
| **"DON'T CLICK"** | Psychological button | Medium horror level + random |
| **Bloody Cursor** | Replaces cursor with blood drop | Very high horror level + random |
| **Page Freeze** | Temporary UI freeze | Very high horror level + random |
| **EVP Meter** | Audio visualization | When whispers play |
| **Device Triggers** | Shake/orientation scares | Mobile devices + physical movement |
| **Konami Code** | Ultimate scare sequence | UP, UP, DOWN, DOWN, LEFT, RIGHT, LEFT, RIGHT, B, A |

---

## Customization

### Adjusting Horror Intensity

The horror engine uses a scale from 0.0 to 1.0:

```javascript
const engine = new HorrorEngine();
engine.horrorLevel = 0.5;  // Moderate horror
engine.horrorLevel = 1.0;  // Maximum terror
```

### Modifying Whispers

```javascript
engine.whispers = [
  "custom whisper 1",
  "custom whisper 2",
  // ...
];
```

### Disabling Specific Effects

```javascript
// Disable audio
engine.audioEnabled = false;

// Disable nightmare/paranoia mode
engine.paranoiaMode = false;

// Modify scare cooldown (in milliseconds)
engine.scareCooldown = 10000;  // 10 seconds
```

---

## Content Warnings

This project contains fictional horror content inspired by SCP Foundation and similar collaborative fiction communities. All entities, events, and documentation are works of fiction.

**Content themes include:**
- Psychological horror
- Supernatural entities
- Isolation and paranoia
- Fictional research/containment scenarios

---

## Browser Compatibility

The horror engine uses modern web APIs and works best on:

- ✅ Chrome/Chromium (best experience)
- ✅ Firefox
- ✅ Safari
- ✅ Edge
- ⚠️ Mobile browsers (some effects limited)

**Note**: Some audio features require user interaction before they can start (browser autoplay policy).

---

## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Ways to Contribute

- 🐛 Report bugs or issues
- 💡 Suggest new horror effects or entities
- 🎨 Improve visual design
- 📝 Add new entity files or experiment logs
- 🔧 Help with code organization
- 🌐 Translate content to other languages
- ♿ Improve accessibility

---

## License

This project is licensed under the MIT License - see [LICENSE](LICENSE) for details.

---

## Acknowledgments

- Inspired by the [SCP Foundation](https://scp-wiki.wikidot.com/) collaborative fiction project
- Horror effects inspired by psychological horror games and ARG experiences
- Built with vanilla HTML/CSS/JavaScript (no frameworks)

---

## 🖐️ NOTICE

**By continuing to use this website, you acknowledge that you have been warned.**

*They're watching.*
