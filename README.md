# Stein Loader

**Minecraft 1.8.9 on Java 25 and LWJGL 3.** The game keeps its 1.8.9 rules and its look; what changed underneath
is the engine it runs on. Nothing from Mojang is redistributed here: the installer patches the `1.8.9.jar` that is
already on your machine, on your machine.

## Download

**[Stein Loader — latest installer](https://github.com/Stein-Project/stein-loader/releases/latest)** — one file that
carries its own Java 25, the engine and the loader. It is a `.jar`: double-click it (or `java -jar
SteinLoader-Installer.jar`) with Java 8 or newer. No Java at all? Take `SteinLoader-Installer-windows.zip` from
the same release, unzip it and run the `.exe` inside.

Play Minecraft 1.8.9 once in the launcher first, run the installer, then pick the profile **Stein Loader 1.8.9**.
Already installed? The button says Update and keeps your earlier choices.

## Mods

Each official mod has its own repository and its own releases, with the mod's index (`steinmods.json`) on each one.
The Stein Client and the installer read those indexes, install the mods you choose and keep them updated; the
installer never removes a `.steinmod` it does not manage. You can also drop a `.steinmod` into the `mods` folder by
hand. Mods are turned on and off in the Stein Loader menu and set up in the Panel (Insert).

| mod | what it does | download |
| --- | --- | --- |
| [HUD](https://github.com/Stein-Project/hud) | customizable HUD, minimap and the Tab list | [HUD.steinmod](https://github.com/Stein-Project/hud/releases/latest/download/HUD.steinmod) |
| [Connect](https://github.com/Stein-Project/connect) | accounts, reconnect and SOCKS5 proxy | [Connect.steinmod](https://github.com/Stein-Project/connect/releases/latest/download/Connect.steinmod) |
| [Keybind](https://github.com/Stein-Project/keybind) | chat messages and commands on a key | [Keybind.steinmod](https://github.com/Stein-Project/keybind/releases/latest/download/Keybind.steinmod) |
| [Replay](https://github.com/Stein-Project/replay) | see how you died | [Replay.steinmod](https://github.com/Stein-Project/replay/releases/latest/download/Replay.steinmod) |

## stein.json

Public data that the **Stein Loader** reads on startup, in `stein.json`. Editing it here applies to everyone the
next time they start the game — no new Loader release and no new installer.

- **`discord`** — the invite to the Stein Labs Discord. It is what the button on the main menu and the one on the
  About tab of the Stein Loader menu open. Only `https://discord.gg/...` or `https://discord.com/invite/...` is
  accepted: the Loader refuses any other address.
- **`latest`** — the installer version that is published and where to get it. The game compares it with the
  version installed on that machine and, when this one is newer, shows a balloon on the main menu.
- **`sources`** — the indexes of the official mods (the `steinmods.json` of each mod's latest release), which the
  Stein Client and the installer read. `mods` is the older single list, kept for launchers and installers from before.
- **`news`** — a small balloon on the main menu: `id` (shown once per id), `title` and `text` (one string, or one
  entry per game language, with `en_US` as the fallback) and an optional `url`.

Releases here are published by CI, and `latest` and `news` are written by it. The mods live in their own
repositories, listed above; this one carries the installer and `stein.json`.
