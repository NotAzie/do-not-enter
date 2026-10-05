# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2025-11-24

### Added

#### Core Experience
- Initial release of DO NOT ENTER horror experience
- Complete HorrorEngine class with adaptive horror level system
- Dark, atmospheric UI with blood/red color scheme
- Responsive design for desktop and mobile

#### Horror Effects (12+ systems)
- **Ambient Audio System**: Background noise generation using Web Audio API
- **Whisper System**: Speech synthesis for eerie messages
- **EVP Meter**: Visual audio activity indicator
- **Peripheral Vision Faces**: Faces that appear opposite cursor movement
- **Shadow Figures**: Dark humanoid silhouettes that appear randomly
- **TV Static Overlay**: Random static flicker effects
- **Screen Melt Effect**: Blood-like visual distortion
- **Paranoia Mode**: Dynamic text replacement on page
- **Fake System Notifications**: Fake security alerts and notifications
- **"DON'T CLICK" Button**: Psychological manipulation button
- **Bloody Cursor**: Replaces cursor with blood drop at high horror levels
- **Page Freeze**: Temporary UI freeze at high horror levels
- **Device Motion Triggers**: Shake and orientation detection for mobile

#### Content
- **Entity Profiles**: Three detailed SCP-style entity documents
  - ENTITY-001 - THE HUSK (KETER class)
  - ENTITY-002 - THE SMILING MAN (EUCLID class)
  - ENTITY-003 - THE STATIC (EUCLID class)
- **Experiment Logs**: Three experiment documentation entries
- **Entity Categories**: Faceless, Whisperers, Shadow People descriptions

#### User Systems
- **Horror Level Tracking**: Dynamic intensity based on behavior
- **User Name Collection**: Optional name for personalization
- **Visit Tracking**: localStorage to detect returning visitors
- **Night Mode**: Increased intensity during night hours (10 PM - 6 AM)
- **Personalized Messages**: Uses user's name in whispers and messages

#### Features
- Nightmare Mode toggle button
- "Are You Alone?" scare button
- Konami code easter egg (UP, UP, DOWN, DOWN, LEFT, RIGHT, LEFT, RIGHT, B, A)
- Custom cursor with blood drop icon
- Blood drip background effect
- Glitch text animation on logo

### Documentation
- README with complete feature documentation
- Usage instructions
- Horror engine architecture explanation
- Content warnings
- Contribution guidelines

### Technical
- Modern HTML5 semantic structure
- CSS custom properties for theming
- Vanilla JavaScript (no dependencies)
- Responsive design
- Browser compatibility notes

---

## Future Releases

### [1.1.0] - Planned

#### New Entities
- ENTITY-004 - The Whisperers (detailed profile)
- ENTITY-005 - The Shadow People (detailed profile)
- More entity categories and variants

#### Enhanced Effects
- More whisper variations
- Additional visual distortion effects
- Sound effects (footsteps, breathing, etc.)
- Customizable horror intensity settings

#### User Experience
- Settings panel to adjust effect intensity
- Option to disable specific effects
- Skip/intro screen with content warnings
- Better mobile optimization

---

**Note**: This is the initial release. The changelog will be maintained going forward as the project evolves.
