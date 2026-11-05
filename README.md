<div align="center">

<img src="snap/gui/limusic.png" alt="LiMusic logo" width="128" />

# LiMusic

**Play YouTube Music and local tracks with gapless audio and synced lyrics.**

[![limusic](https://snapcraft.io/limusic/badge.svg)](https://snapcraft.io/limusic)
[![Base: core26](https://img.shields.io/badge/Base-core26-2C8C3C?logo=canonical&logoColor=white)](https://snapcraft.io/core26)
![Confinement: strict](https://img.shields.io/badge/Confinement-strict-2C8C3C)
[![Maintainer: sidaliteir](https://img.shields.io/badge/Maintainer-sidaliteir-2C8C3C?logo=snapcraft&logoColor=white)](https://snapcraft.io/publisher/sidaliteir)
![Architectures: amd64, arm64](https://img.shields.io/badge/Architectures-amd64%20%7C%20arm64-2C8C3C?logo=linux&logoColor=white)

[Getting Started](#getting-started) · [Configure](#configure) · [Limitations](#limitations) · [Build](#build) · [Support](#support) · [License](#license)

Unofficial snap packaging for [LiMusic](https://github.com/SimoHypers/limusic), a desktop YouTube Music client and local music player with playlists, lyrics, music videos and ListenBrainz scrobbling.

</div>

---

## Getting Started

<a href="https://snapcraft.io/limusic"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install limusic
limusic
```

Search for music, sign in to access your YouTube Music library, or add local music from your home directory.

## Configure

Use the application's settings for playback, appearance, accounts and ListenBrainz. Settings and library data stay inside `~/snap/limusic/current`; there are no `snap set` options.

For music on removable storage:

```bash
sudo snap connect limusic:removable-media
```

## Limitations

- Last.fm requires upstream's private build credentials and is unavailable in this package. ListenBrainz uses the token you enter in the application.
- The application's launch-at-login setting is unavailable. Discord Rich Presence and external host theme files are outside the snap's confinement.
- Top-level hidden home directories are not accessible through the `home` interface. Choose music from an accessible directory or connected removable storage.
- Application updates come through `snap refresh limusic`. Streaming client and player-cipher updates remain enabled; playback also depends on YouTube's service and authentication behavior.

## Build

```bash
git clone https://github.com/sidalit/limusic-snap.git
cd limusic-snap
sudo snap install snapcraft --classic
snapcraft pack
```

```bash
sudo snap install --dangerous ./limusic_*.snap
limusic
```

The recipe builds the tagged source natively on amd64 and arm64. The single-instance D-Bus slot may require Snap Store approval before publication.

## Support

- **Installation or snap issues:** [open a packaging issue](https://github.com/sidalit/limusic-snap/issues).
- **Application bugs:** [report them upstream](https://github.com/SimoHypers/limusic/issues).

## License

Snap packaging: [MIT](LICENSE).
