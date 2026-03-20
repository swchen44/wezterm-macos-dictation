# WezTerm — macOS Dictation Build (Apple Silicon)

> Pre-built binary of [Erog38/wezterm feat/macos-dictation](https://github.com/Erog38/wezterm/tree/feat/macos-dictation), adding native macOS Dictation support via IMKit integration.

**[繁體中文說明 →](README.zh-TW.md)**

---

## ⚠️ Requirements

- **Apple Silicon Mac only** (M1 / M2 / M3 / M4)
- Intel Macs (pre-2020) are **not supported**
- macOS 12 Monterey or later recommended

---

## ⬇️ Download

Go to [**Releases**](https://github.com/swchen44/wezterm-macos-dictation/releases/latest) and download `WezTerm-macos-arm64.dmg`.

---

## 📦 Installation

**1. Mount and install**

Double-click the `.dmg` file, then drag `WezTerm.app` into `/Applications`.

**2. Remove Gatekeeper quarantine (required)**

Because this build is unsigned, macOS will block it. Run this command **before opening**:

```bash
xattr -cr /Applications/WezTerm.app
```

**3. Launch**

Double-click `WezTerm.app` in `/Applications`.

---

## 🈳 Chinese Character Display (Recommended)

Create `~/.config/wezterm/wezterm.lua` to enable proper CJK rendering:

```bash
mkdir -p ~/.config/wezterm
```

```lua
local wezterm = require 'wezterm'

return {
  font = wezterm.font_with_fallback {
    'JetBrains Mono',
    'Heiti TC',   -- built-in macOS Traditional Chinese font
  },
  unicode_version = 14,
}
```

---

## 🎙️ Using macOS Dictation

With WezTerm open, press **`Fn` twice** (or the microphone button on supported keyboards) to activate system Dictation and speak to type.

---

## ⚠️ Known Limitations

| Limitation | Details |
|------------|---------|
| Apple Silicon only | arm64 binary — Intel Macs not supported |
| Unsigned build | Must run `xattr -cr` to bypass Gatekeeper |
| Community branch | Based on `feat/macos-dictation`, not yet merged into WezTerm main |
| Dictation language | Depends on system Dictation language setting in System Settings |

---

## 🔗 Links

- [Source branch: Erog38/wezterm feat/macos-dictation](https://github.com/Erog38/wezterm/tree/feat/macos-dictation)
- [WezTerm official docs](https://wezfurlong.org/wezterm/)
- [繁體中文說明](README.zh-TW.md)
