<div align="center">

# 󰍛 Gruvbox Dark Fastfetch

### A warm, retro-inspired Fastfetch dashboard for NixOS and Hyprland.

<br>

[![Fastfetch](https://img.shields.io/badge/FASTFETCH-CONFIG-d79921?style=for-the-badge\&logo=linux\&logoColor=fbf1c7)](https://github.com/fastfetch-cli/fastfetch)
[![NixOS](https://img.shields.io/badge/NIXOS-READY-458588?style=for-the-badge\&logo=nixos\&logoColor=fbf1c7)](https://nixos.org/)
[![Hyprland](https://img.shields.io/badge/HYPRLAND-OPTIMISED-689d6a?style=for-the-badge\&logo=wayland\&logoColor=fbf1c7)](https://hypr.land/)
[![License](https://img.shields.io/badge/LICENSE-MIT-cc241d?style=for-the-badge)](LICENSE)

<br>

A custom **Gruvbox Dark Fastfetch configuration** designed to turn a basic system summary into a clean terminal dashboard.

Built for my personal NixOS setup — at least until I get bored of it within the next **2–4 business days**.

</div>

<br>

## 󰋼 Preview

<div align="center">

<img width="100%" alt="Gruvbox Dark Fastfetch preview" src="https://github.com/user-attachments/assets/6b0f99d8-3e65-4f0e-8d44-c37db2469504" />

<br><br>

<img width="100%" alt="Gruvbox Dark Fastfetch terminal preview" src="https://github.com/user-attachments/assets/fb7cc6de-a047-46fd-8a09-a1903823e1af" />

</div>

<br>

## 󰔎 Features

* Warm **Gruvbox Dark** colour palette
* Custom multicoloured NixOS logo
* Clean, sectioned system-information layout
* NixOS version and system-generation information
* Hyprland monitor and session detection
* CPU, GPU, NVIDIA driver and VRAM statistics
* Root-drive and secondary-drive usage
* Active PipeWire audio output
* Currently playing media through Playerctl
* Local IP address, uptime and package count
* Nerd Font icons throughout
* Absolutely guaranteed to make opening a terminal feel more important

<br>

## 󰏗 Requirements

### Required

* [Fastfetch](https://github.com/fastfetch-cli/fastfetch)
* A terminal with true-colour support
* A [Nerd Font](https://www.nerdfonts.com/) for the icons

### Used by the included modules

| Command         | Purpose                                     |
| :-------------- | :------------------------------------------ |
| `nixos-version` | Displays the current NixOS version          |
| `hyprctl`       | Detects the focused Hyprland monitor        |
| `nvidia-smi`    | Displays NVIDIA driver and VRAM information |
| `wpctl`         | Detects the active PipeWire audio output    |
| `playerctl`     | Displays currently playing media            |

The configuration will still launch when some optional commands are unavailable, but their corresponding values may show as unavailable or unknown.

<br>

## 󰐕 Installation

### Automatic installation

This command backs up an existing Fastfetch configuration, downloads this repository's config and launches Fastfetch:

```bash
mkdir -p ~/.config/fastfetch

test ! -f ~/.config/fastfetch/config.jsonc || \
  cp ~/.config/fastfetch/config.jsonc \
  ~/.config/fastfetch/config.jsonc.bak

curl -fsSL \
  https://raw.githubusercontent.com/Aetherelic/Gruvbox-Dark-Fastfetch/main/config \
  -o ~/.config/fastfetch/config.jsonc

fastfetch
```

### Clone with Git

```bash
git clone https://github.com/Aetherelic/Gruvbox-Dark-Fastfetch.git

mkdir -p ~/.config/fastfetch

cp Gruvbox-Dark-Fastfetch/config \
  ~/.config/fastfetch/config.jsonc

fastfetch
```

<br>

## 󰒓 Customisation

This configuration was created for my own machine, so a few entries are intentionally personalised.

Open the configuration with:

```bash
nano ~/.config/fastfetch/config.jsonc
```

You may want to change the following values.

### Distribution logo

```json
"source": "nixos"
```

Replace `nixos` with another built-in Fastfetch logo when using a different distribution.

### Display information

```json
"text": "printf '2560x1440p @ 200Hz'"
```

Change this to match your monitor's resolution and refresh rate.

### Theme name

```json
"text": "printf 'Retro Nix'"
```

Replace `Retro Nix` with the name of your own desktop theme or rice.

### Secondary drive

```json
"text": "df -h /mnt/HDD1 ..."
```

Change `/mnt/HDD1` to the mount point of your secondary drive, or remove the module entirely.

### NVIDIA modules

The driver and VRAM entries use `nvidia-smi`.

AMD and Intel users can remove or replace these command modules.

### NixOS-specific modules

The `Version` and `Gen` modules rely on NixOS commands and paths.

Users on other distributions should remove or replace them.

<br>

## 󰆍 Usage

Launch the configuration at any time with:

```bash
fastfetch
```

To display it automatically whenever your shell starts, add the following line to your shell configuration.

### Bash

```bash
printf '\nfastfetch\n' >> ~/.bashrc
```

### Zsh

```bash
printf '\nfastfetch\n' >> ~/.zshrc
```

### Fish

```fish
printf '\nfastfetch\n' >> ~/.config/fish/config.fish
```

Avoid adding it automatically when your terminal already launches Fastfetch through another script or dashboard.

<br>

## 󰈙 Colour Palette

The configuration uses colours inspired by the classic Gruvbox Dark palette.

<div align="center">

| Colour |    Hex    | Usage                 |
| :----: | :-------: | :-------------------- |
|   🟨   | `#d79921` | Titles and storage    |
|   🟩   | `#689d6a` | Display and session   |
|   🟦   | `#458588` | Hardware information  |
|   🟥   | `#cc241d` | Network and media     |
|    ⬜   | `#ebdbb2` | Labels and foreground |

</div>

<br>

## 󰊤 Contributing

Suggestions, improvements and ports for other distributions are welcome.

1. Fork the repository.
2. Create a new branch.
3. Make and test your changes.
4. Open a pull request with a screenshot of the result.

Please keep contributions consistent with the existing Gruvbox styling.

<br>

## 󰿃 Credits

* [Fastfetch](https://github.com/fastfetch-cli/fastfetch) for the system-information tool
* [Gruvbox](https://github.com/morhetz/gruvbox) for the iconic colour palette
* The Linux ricing community for repeatedly convincing me that system information needs to be aesthetically pleasing

<br>

## 󰄬 Licence

Released under the [MIT Licence](LICENSE).

You are free to use, modify and redistribute this configuration.

<br>

<div align="center">

### Made with 󰊤, NixOS and an unreasonable amount of terminal customisation.

<br>

[![GitHub profile](https://img.shields.io/badge/AETHERELIC-GITHUB-d79921?style=for-the-badge\&logo=github\&logoColor=fbf1c7)](https://github.com/Aetherelic)

</div>
