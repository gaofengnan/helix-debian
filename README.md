![GitHub Downloads (all assets, all releases)](https://img.shields.io/github/downloads/gaofengnan/helix-debian/total)
![GitHub Downloads (all assets, latest release)](https://img.shields.io/github/downloads/gaofengnan/helix-debian/latest/total)
![GitHub Release](https://img.shields.io/github/v/release/gaofengnan/helix-debian)
![GitHub Release Date](https://img.shields.io/github/release-date/gaofengnan/helix-debian?display_date=published_at)

# helix for Debian

> Fork of [dariogriffo/helix-debian](https://github.com/dariogriffo/helix-debian) (MIT); the original packaging is by Dario Griffo. Served at [deb.gaofn.xyz](https://deb.gaofn.xyz) for Debian 12 (bookworm) and 13 (trixie).

This repository contains build scripts to produce the _unofficial_ Debian packages
(.deb) for [helix](https://github.com/helix-editor/helix) hosted at [deb.gaofn.xyz](https://deb.gaofn.xyz)

Currently supported Debian distros are:
- Bookworm (v12)
- Trixie (v13)
- Forky (v14)
- Sid (testing)

**Upstream architectures:** amd64 and arm64 only (upstream also publishes a source tarball; other architectures would need a from-source build).

This is an unofficial community project to provide a package that's easy to
install on Debian. If you're looking for the helix source code, see
[helix](https://github.com/helix-editor/helix).

## Install/Update

### The Debian way

```sh
sudo install -d -m 0755 /etc/apt/keyrings
sudo curl -fsSL https://deb.gaofn.xyz/deb.gaofn.xyz.gpg -o /etc/apt/keyrings/deb.gaofn.xyz.gpg
sudo curl -fsSL https://deb.gaofn.xyz/deb.gaofn.xyz.sources -o /etc/apt/sources.list.d/deb.gaofn.xyz.sources
# Debian 12 (bookworm): fetch deb.gaofn.xyz-bookworm.sources instead
sudo apt update
sudo apt install -y helix
```

### Manual Installation

1. Download the .deb package for your Debian version available on
   the [Releases](https://github.com/gaofengnan/helix-debian/releases) page.
2. Install the downloaded .deb package.

```sh
sudo dpkg -i <filename>.deb
```
## Updating

To update to a new version, just follow any of the installation methods above. There's no need to uninstall the old version; it will be updated correctly.

## Building

### Build for single architecture
```sh
./build.sh <helix_version> <build_version> <architecture>
# Example: ./build.sh 1.2.3 1 arm64
```

### Build for all architectures
```sh
./build.sh <helix_version> <build_version> all
# Example: ./build.sh 1.2.3 1 all
```

## Roadmap

- [x] Produce a .deb package on GitHub Releases
- [x] Set up a debian mirror for easier updates
- [x] Multi-architecture support (amd64, arm64)

## Disclaimer

- This repo is not open for issues related to helix. This repo is only for _unofficial_ Debian packaging.
