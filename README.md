# [GrowthBook](https://www.growthbook.io/) developer environment setup with the [Nix](https://nixos.org/) package manager

## Installation

Install [Nix](https://nixos.org/download#download-nix) package manager with [Determinate Nix installer](https://github.com/DeterminateSystems/nix-installer):

```bash
curl --proto '=https' --tlsv1.2 -sSf -L https://install.determinate.systems/nix | sh -s -- install
```

Alternatively you can use [official installer](https://nixos.org/download#download-nix):

``` bash
sh <(curl -L https://nixos.org/nix/install) --no-daemon
```

But it doesn't enable Flakes by default, so you need to [enable them manually](https://nixos.wiki/wiki/Flakes).

Add the following to ~/.config/nix/nix.conf or /etc/nix/nix.conf:

> experimental-features = nix-command flakes

## Usage

From any GrowthBook repo run:

``` bash
nix develop github:mkurkov/growhbook-nix
```

It will open new shell with all dev tools available (node, yarn, python, go, docker).

If you prefer to use your current shell, provide additional command, e.g. SHELL env variable:

``` bash
nix develop github:mkurkov/growthbook-nix -c $SHELL
```

