# Contrarian GNU/Linux

Contrarian GNU/Linux is a Devuan-based distribution that deliberately prefers the classic solution when one exists.

The project aims for a stable, familiar desktop with conservative defaults:

- Base system: Devuan GNU/Linux
- Display stack: XLibre on X11 only by default
- Desktop: MATE
- Audio: ALSA with `dmix`, no sound server by default
- Philosophy: minimize churn, avoid fashionable replacements, keep the stack legible

This repository contains the initial distro definition:

- `branding/` contains release identity and `/etc/os-release` metadata
- `profile/` contains package selection rules
- `docs/` contains the project rationale and supported defaults
- `site/` contains the static site for `https://contrarian.soccera.uk`

## What Contrarian ships

- A traditional XLibre session
- MATE as the default desktop environment
- ALSA-based audio configuration with software mixing via `dmix`
- Classic desktop plumbing where practical
- A Devuan base so the system stays free of systemd by design

## What Contrarian avoids

- PipeWire
- PulseAudio
- Systemd

## Design rules

1. Prefer the simplest working classical tool.
2. Keep dependencies small and explicit.
3. Choose stable interfaces over newer abstractions.
4. Preserve compatibility with older workflows where that does not create needless complexity.
5. Default to software that behaves predictably on modest hardware.

## Planned package profile

The package profile is intentionally conservative:

- `xlibre` and `xinit` for the graphical stack
- XLibre Devuan APT repository: `https://github.com/xlibre-debian/devuan`
- `mate-desktop-environment` for the desktop
- `lightdm` as the login manager
- `alsa-utils` and `libasound2-plugins` for audio support
- No default sound server

## Notes

This is an initial project scaffold, not a finished installable ISO. The next step would be to turn the profile into a build system, then generate an installer image or live image from it.
