# Architecture Documentation

This document describes the technical architecture of DO NOT ENTER.

## Overview

DO NOT ENTER is a browser-based horror experience built with vanilla HTML, CSS, and JavaScript. It uses modern web APIs to create an immersive, adaptive horror experience without requiring any external dependencies or frameworks.

```
┌─────────────────────────────────────────────────────────────────┐
│                        User Interface Layer                      │
│  ┌─────────────────────────────────────────────────────────────┐│
│  │                    HTML Structure                            ││
│  │  - Navigation & Header                                      ││
│  │  - Hero Section                                             ││
│  │  - Feature Cards                                            ││
│  │  - Entity Archives (SCP-style documents)                    ││
│  │  - Experiment Logs                                          ││
│  │  - Footer                                                   ││
│  └─────────────────────────────────────────────────────────────┘│
│                              │                                   │
│                              ▼                                   │
│  ┌─────────────────────────────────────────────────────────────┐│
│  │                    Visual Layer (CSS)                        ││
│  │  - Dark theme with red accents                              ││
│  │  - Typography (Courier New / monospace)                     ││
│  │  - Animations & keyframes                                   ││
│  │  - Visual effects (static, glitch, blood, etc.)            ││
│  │  - Responsive design                                        ││
│  └─────────────────────────────────────────────────────────────┘│
│                              │                                   │
│                              ▼                                   │
│  ┌─────────────────────────────────────────────────────────────┐│
│  │                  Horror Engine (JavaScript)                  ││
│  │  ┌─────────────────────────────────────────────────────────┐││
│  │  │                   HorrorEngine Class                     │││
│  │  │  - Horror level tracking (0.0 - 1.0)                   │││
│  │  │  - User state management                                │││
│  │  │  - Effect coordination                                   │││
│  │  │  - Initialization of all systems                        │││
│  │  └─────────────────────────────────────────────────────────┘││
│  │  ┌─────────────────────────────────────────────────────────┐││
│  │  │              Subsystems (Methods)                       │││
│  │  │  - Audio System (Web Audio API + Speech Synthesis)     │││
│  │  │  - Visual Effects (DOM manipulation)                   │││
│  │  │  - Interaction Traps (page freezes, fake notifications)│││
│  │  │  - Biometric Reaction (mouse, device sensors)          │││
│  │  │  - Paranoia Mode (text replacement)                    │││
│  │  │  - Personalization (user name, visit tracking)         │││
│  │  │  - Easter Eggs (Konami code, etc.)                     │││
│  │  └─────────────────────────────────────────────────────────┘││
│  └─────────────────────────────────────────────────────────────┘│
│                              │                                   │
│                              ▼                                   │
│  ┌─────────────────────────────────────────────────────────────┐│
│  │                     Data Layer                               ││
│  │  - localStorage (user name, visit history)                 ││
│  │  - DOM (visual state, content)                             ││
│  │  - Browser APIs (AudioContext, SpeechSynthesis, etc.)      ││
│  └─────────────────────────────────────────────────────────────┘│
└─────────────────────────────────────────────────────────────────┘
```

## Core Components

### 1. HorrorEngine Class

The central controller for all horror effects.

**Location**: `<script>` tag in index.html

**Responsibilities**:
- Track and manage horror level (0.0 - 1.0)
- Initialize all subsystems
- Coordinate effect timing and triggers
- Manage user state and personalization
- Handle user interactions

**Key Properties**:
```javascript
class HorrorEngine {
    horrorLevel: number;        // 0.0 (calm) to 1.0 (terror)
    userSensitivity: number;    // How easily user is affected
    lastScareTime: number;      // Timestamp of last scare
    scareCooldown: number;      // Minimum time between scares (ms)
    paranoiaMode: boolean;      // Whether text replacement is active
    audioEnabled: boolean;      // Whether audio systems are active
    scareCount: number;         // Number of scares triggered
    userName: string | null;    // User's name (if provided)
    nightMode: boolean;         // Whether it's night time
    visitedBefore: boolean;     // Whether user has visited before
}
```

### 2. Audio System

Uses Web Audio API and Speech Synthesis to create eerie audio.

**Components**:

#### Background Noise
- Generates ambient noise using Web Audio API
- Creates buffer of random samples
- Applies bandpass filter for eerie quality
- Loops continuously

```javascript
createBackgroundNoise() {
    const noiseNode = this.audioContext.createBufferSource();
    const bufferSize = 2 * this.audioContext.sampleRate;
    const noiseBuffer = this.audioContext.createBuffer(1, bufferSize, this.audioContext.sampleRate);
    // Fill buffer with random noise
    // Apply bandpass filter
    // Loop and play
}
```

#### Whisper System
- Uses Speech Synthesis API to speak messages
- Messages are eerie, unsettling phrases
- Volume and pitch vary based on horror level
- Includes EVP meter visualization
- Random timing between whispers

```javascript
playWhisper() {
    const whisper = this.whispers[random];
    const utterance = new SpeechSynthesisUtterance(whisper);
    utterance.volume = 0.1 + (this.horrorLevel * 0.3);
    utterance.rate = 0.8;
    utterance.pitch = 1.2;
    window.speechSynthesis.speak(utterance);
}
```

### 3. Visual Effects System

Manages all visual horror effects through DOM manipulation.

**Effects**:

#### Peripheral Vision Faces
- Tracks mouse movement
- At high horror levels, faces appear opposite cursor
- Faces disappear when "looked at" (after timeout)
- Creates feeling of being watched

#### Shadow Figures
- Randomly appear at medium+ horror levels
- Fade in and out over several seconds
- Positioned at edges of viewport

#### Static Overlay
- TV static effect using CSS background
- Random flickering at high horror levels
- Brief opacity increases

#### Screen Melt
- Blood-red gradient overlay
- Clip-path animation for melting effect
- Very high horror level only

#### Glitch Text
- CSS animation on logo text
- Color shifting and offset effects
- Continuous animation on logo

#### Blood Drip & Cursor
- SVG-based blood drip background
- Custom cursor replacement with blood drop
- Activates at high horror levels

### 4. Interaction Trap System

Creates psychological tension through user interaction.

**Traps**:

#### Fake Notifications
- Mimics system notification style
- "Security Alert" messages
- Appears at medium+ horror levels
- Disappears after viewing

#### "DON'T CLICK" Button
- Appears randomly at medium+ levels
- Psychological manipulation (ironic process theory)
- No actual scare on click (just disappears)

#### Page Freeze
- Disables pointer events temporarily
- Creates panic moment
- Very high horror level only
- Short duration (1 second)

#### Bloody Cursor
- Replaces system cursor with blood drop SVG
- Follows mouse movement
- Very high horror level + random triggers

### 5. Biometric Reaction System

Tracks user behavior to adjust horror level.

**Inputs**:

#### Mouse Movement
- Active mouse movement increases tension
- Inactivity slowly increases tension
- Last move time tracked

#### Device Orientation (Mobile)
- Detects device tilt > 45 degrees
- Triggers tilt scare
- Uses DeviceOrientationEvent API

#### Device Motion (Mobile)
- Detects shaking movement
- Triggers shake scare
- Uses DeviceMotionEvent API
- Cooldown prevents spam

### 6. Paranoia Mode

Dynamically replaces text on the page.

**Mechanism**:
- At high horror levels + paranoia mode active
- Periodically scans page for target words
- Replaces words with unsettling alternatives
- Uses CSS transitions for smooth replacement

**Word Replacements**:
```javascript
const replaceableWords = [
    { original: "the", replacements: ["them", "they", "it"] },
    { original: "you", replacements: ["us", "them", "it"] },
    { original: "home", replacements: ["here", "there", "the void"] },
    { original: "see", replacements: ["watch", "observe", "know"] },
    { original: "alone", replacements: ["followed", "watched", "not alone"] }
];
```

### 7. Personalization System

Customizes experience based on user information.

**Features**:

#### User Name
- Optional prompt for name
- Stored in localStorage
- Used in whispers and messages
- Creates personalized horror messages

#### Visit Tracking
- Detects returning visitors via localStorage
- "WELCOME BACK" message for returners
- Can increase horror level for return visitors

#### Night Mode
- Detects current time (10 PM - 6 AM)
- Increases base horror level by 0.3
- Adds glitch effect to body
- Creates more intense night experience

### 8. Easter Egg System

Hidden features for discovering.

**Konami Code**:
- Classic cheat code: UP, UP, DOWN, DOWN, LEFT, RIGHT, LEFT, RIGHT, B, A
- Triggers ultimate scare sequence
- Resets after trigger

## Data Flow

### Initialization Flow
```
Page Load
    │
    ▼
HorrorEngine Constructor
    │
    ├── Get user name (optional prompt or localStorage)
    ├── Detect night time
    ├── Check visit history (localStorage)
    │
    ├── initElements()         → Cache DOM elements, add event listeners
    ├── initAmbientAudio()     → Create AudioContext, start background noise
    ├── initVisualDistortions()→ Set up effect timers
    ├── initInteractionTraps() → Set up trap timers
    ├── initBiometricReaction()→ Add mouse/device event listeners
    ├── initParanoiaMode()     → Set up text replacement timer
    ├── initEasterEggs()       → Add keyboard listener for Konami code
    └── initPersonalizedHorror()→ Add personalized messages, night effects
```

### Horror Level Adjustment
```
User Activity (mouse moves)
    │
    ▼
Increase horror level by 0.1
    │
    ▼
Horror level affects:
    ├── Frequency of visual effects
    ├── Volume/pitch of whispers
    ├── Likelihood of trap triggers
    └── Paranoia mode word replacement rate
```

### Scare Trigger Flow
```
Timer/Event triggers scare
    │
    ├── Check horror level threshold met?
    ├── Check cooldown period passed?
    ├── Check random chance?
    │
    ▼
Execute scare effect:
    ├── Show scare image/modal
    ├── Play audio
    ├── Adjust horror level
    └── Update scare count
```

## Browser Compatibility

### Supported Browsers
- **Chrome/Chromium**: Full support, best experience
- **Firefox**: Full support
- **Safari**: Good support (some audio differences)
- **Edge**: Full support (Chromium-based)

### Browser APIs Used

| API | Purpose | Fallback |
|-----|---------|----------|
| Web Audio API | Background noise generation | Audio disabled |
| Speech Synthesis | Whisper messages | No whispers |
| DeviceOrientationEvent | Mobile tilt detection | No tilt scares |
| DeviceMotionEvent | Mobile shake detection | No shake scares |
| localStorage | User data persistence | No personalization |
| CSS Animations | Visual effects | Static fallback |
| CSS Custom Properties | Theming | Default colors |

### Known Limitations

- Audio must be initiated by user interaction (browser autoplay policy)
- Some effects may perform differently on mobile
- Device sensors require user permission on some browsers
- Speech synthesis voices vary by browser/OS

## Performance Considerations

### Optimization Strategies

1. **Effect Throttling**: Effects use timers and random chances to prevent overload
2. **DOM Queries Cached**: Elements cached in initElements()
3. **Timer Management**: Intervals created once, cleared when not needed
4. **Effect Probability**: Random chance prevents constant effect triggering

### Potential Performance Issues

1. **Multiple setInterval calls**: Many timers running simultaneously
2. **DOM manipulation**: Text replacement scans entire page periodically
3. **Audio processing**: Background noise is lightweight but continuous

### Recommendations for Improvement

1. Use requestAnimationFrame for smoother animations
2. Throttle DOM queries in paranoia mode
3. Consider Web Workers for audio processing
4. Lazy load effects based on horror level

## Security Considerations

### No External Data
- All data stored locally in localStorage
- No server communication
- No tracking or analytics

### User Permissions
- Audio requires user interaction first
- Device sensors require explicit permission
- Users can deny permissions without breaking core experience

### Content Safety
- See SECURITY.md for content warnings
- Effects can be disturbing but not genuinely harmful
- Users can close browser at any time

## Future Architecture Considerations

### Modularization
Current single-file structure could be improved:
- Extract CSS to stylesheet
- Extract JS to modules
- Component-based architecture
- State management for horror level

### Advanced Features
- WebGL for advanced visual effects
- Service workers for offline capability
- PWA for installable experience
- WebRTC for multiplayer horror
