# Luci OS

![Luci OS banner](banner.png)

**A real OS, running today. Your computer, your AI, your rules.**

Luci OS is a sovereign desktop environment built around local ownership, offline AI, a one-file app format, and a user-owned trust model. It is designed so apps, files, themes, and AI workflows can live on the user's machine instead of depending on a cloud account.

## Watch Luci OS

| Desktop | Files | The Gate |
|---|---|---|
| [![The Desktop](https://img.youtube.com/vi/E-KootR0hdQ/hqdefault.jpg)](https://youtu.be/E-KootR0hdQ) | [![Files](https://img.youtube.com/vi/VmUPx38G3jI/hqdefault.jpg)](https://youtu.be/VmUPx38G3jI) | [![The Gate](https://img.youtube.com/vi/CzjcEEcTqUQ/hqdefault.jpg)](https://youtu.be/CzjcEEcTqUQ) |
| Luci desktop, dock, panels, and window chrome. | Local file browsing and project workflow. | Launcher flow for opening apps and moving through the system. |

| VinX AI | Real Apps | Visual Scripting |
|---|---|---|
| [![VinX AI](https://img.youtube.com/vi/qyJjqVo6XHk/hqdefault.jpg)](https://youtu.be/qyJjqVo6XHk) | [![Real Apps Run Too](https://img.youtube.com/vi/nBRnrhDsap4/hqdefault.jpg)](https://youtu.be/nBRnrhDsap4) | [![NodeBase Visual Scripting](https://img.youtube.com/vi/rVJuJQJU2KY/hqdefault.jpg)](https://youtu.be/rVJuJQJU2KY) |
| Offline AI assistant inside the OS. | Native apps can run in Luci workflows. | Build logic by wiring nodes visually. |

| AI Theme | Appearance and LStore | AI FilmMaker |
|---|---|---|
| [![AI Theme](https://img.youtube.com/vi/3NHX1UR-AI0/hqdefault.jpg)](https://youtu.be/3NHX1UR-AI0) | [![Appearance and LStore](https://img.youtube.com/vi/--IApZuCBn8/hqdefault.jpg)](https://youtu.be/--IApZuCBn8) | [![AI FilmMaker](https://img.youtube.com/vi/J6D1MSIZFNc/hqdefault.jpg)](https://youtu.be/J6D1MSIZFNc) |
| Describe a look and let Luci shape the theme. | Personalization and app/store direction. | Early experimental creative workflow. |

## What Makes Luci Different

- **Local-first:** files, apps, identity, and AI workflows stay on the device by default.
- **Offline AI direction:** VinX is designed as an in-OS assistant, not a cloud-only chatbot.
- **One-file apps:** Luci apps use the `.vx` format, a portable Python-based app file.
- **Consistent shell:** apps inherit Luci's standard window frame instead of drawing their own title bar.
- **User-owned trust:** app metadata, network declarations, signing, and trust prompts are part of the model.
- **Expandable:** LStore, L++, NodeBase, Nerds Portal, Tuba, and native app wrappers are all Luci-facing tools.

## `.vx` App Format

Luci apps are designed to be small, portable, and easy to inspect. A typical app starts with a `# VX:` header:

```python
# VX:name=Hello
# VX:icon=H
# VX:version=1.0
# VX:author=Your Name
# VX:net=none
```

Then the app inherits from Luci's app base:

```python
from app import LuciWindow
from PyQt5.QtWidgets import QLabel

class Hello(LuciWindow):
    TITLE = "Hello"
    ICON = "H"
    SIZE = (420, 240)

    def build_body(self, layout):
        layout.addWidget(QLabel("Hello from Luci OS."))
```

Save it as a `.vx` file in Luci's app folder:

```text
Vinx-Desktop/programfiles/hello.vx
```

Or create it with **L++**, Luci's guided app creator.

## App Creation Rules

- Start every Luci app with a `# VX:` metadata header.
- Use `LuciWindow` for normal Luci UI apps.
- Use `LuciNativeApp` when wrapping a native binary.
- Do not hardcode your own title bar; Luci provides the window frame.
- Declare network needs with `# VX:net=none`, `local`, or `web`.
- Keep the app portable as one `.vx` file whenever possible.
- Treat unsigned apps as untrusted until the user or system trust flow approves them.

## Features Shown In The Videos

- Glass desktop shell with dock and app windows
- Local file management
- Launcher Gate
- Offline AI assistant direction through VinX
- AI-assisted theming
- Visual scripting through NodeBase
- Real app workflows
- Early LStore and Appearance direction
- Experimental AI FilmMaker concept

## Nerds Portal And Nerds Gate

Luci OS also includes early work on **Nerds Portal**, a user portal and messaging app.

- **LAN Mode:** direct local discovery and local messaging.
- **Internet Mode:** outbound WebSocket through Nerds Gate.
- **Hybrid Auto:** LAN first, Gate fallback.

Nerds Gate is a public relay direction for users behind NAT, CGNAT, mobile data, hotel Wi-Fi, or normal routers.

## Current Status

Luci OS is a live prototype and active research system. It already demonstrates:

- Working desktop shell
- App launcher and windowing
- `.vx` app format
- L++ app creator direction
- LStore direction
- Local file workflows
- Theme and appearance tools
- Offline AI direction through VinX
- Native app and runtime experiments
- International relay direction through Nerds Gate

## Roadmap

- Harden `.vx` app trust and signing
- Expand LStore packaging
- Improve offline AI app creation
- Continue NodeBase visual scripting
- Add file and live relay to Nerds Gate
- Mature Tuba runtime research
- Prepare public developer examples

## Author

Created by **Vincent Ilagan**.

Luci OS is built around one principle: the user's machine should remain the center of their computing life.
