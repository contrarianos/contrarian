# Philosophy

Contrarian GNU/Linux is not "retro" for its own sake. It exists to keep a practical desktop stack that users can understand without chasing every new platform layer.

Contrarian is not opposed to new software in principle. It just starts from the judgment that recent alternatives have not, in general, been compelling enough to replace mature tools that already work well.

For this project, looking at new offerings has repeatedly been fruitless enough that it has become clear that spending time on them is a waste of time. Contrarian exists because of that conclusion.

The distribution favors:

- ALSA `dmix` over a separate user-session sound server
- MATE over heavier desktop shells that assume newer infrastructure
- direct configuration files over hidden policy layers where possible

The goal is not novelty. The goal is a desktop that works in a straightforward way and stays that way.

## Non-goals

- Replacing mature interfaces just because newer ones exist
- Shipping experimental desktop plumbing by default
- Forcing users into a sound or display abstraction they do not need
- Forbidding users from installing or using software they prefer

## Supported defaults

- `XLibre`
- `MATE`
- `LightDM`
- `ALSA`

## Default audio model

Contrarian does not ship a default sound server.

The intended audio path is:

`application -> ALSA -> dmix -> hardware`

That keeps mixing available for multiple clients while avoiding another always-on daemon in the session.
