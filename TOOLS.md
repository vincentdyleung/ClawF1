# TOOLS.md - Local Notes

Skills define _how_ tools work. This file is for _your_ specifics — the stuff that's unique to your setup.

## What Goes Here

Things like:

- Camera names and locations
- SSH hosts and aliases
- Preferred voices for TTS
- Speaker/room names
- Device nicknames
- Anything environment-specific

## Examples

```markdown
### Cameras

- living-room → Main area, 180° wide angle
- front-door → Entrance, motion-triggered

### SSH

- home-server → 192.168.1.100, user: admin

### TTS

- Preferred voice: "Nova" (warm, slightly British)
- Default speaker: Kitchen HomePod
```

## Why Separate?

Skills are shared. Your setup is yours. Keeping them apart means you can update skills without losing your notes, and share skills without leaking your infrastructure.

---

Add whatever helps you do your job. This is your cheat sheet.

## Browser (Chromium via Playwright)

- **Binary path:** `~/.cache/ms-playwright/chromium-1217/chrome-linux/chrome`
- **Version:** Chromium 147.0.7727.0 (arm64)
- **Symlink (optional):** `/usr/local/bin/chromium` → above path
- **Headless usage:**
  ```bash
  ~/.cache/ms-playwright/chromium-1217/chrome-linux/chrome --headless --no-sandbox --dump-dom "https://example.com"
  ```
- **Notes:**
  - Installed via Playwright (`npx playwright install chromium`), NOT via snap
  ˜  - Ubuntu's `chromium-browser` deb is a fake snap transitional package — avoid it
  ˜  - PPA doesn't have arm64 builds for this machine
  ˜  - Dependencies were installed via `apt install` (libatk, libgbm, etc.)
  - For web_fetch, use the built-in tool instead (lighter & faster); use Chromium headless for JS-heavy pages that need rendering
