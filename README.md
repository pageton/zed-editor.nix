# Nix flake for [Zed](https://zed.dev/) editor

This flake provides a [Nix](https://nixos.org/) package for the latest release of Zed editor.

[![FlakeHub](https://img.shields.io/endpoint?url=https://flakehub.com/f/maximoffua/zed-editor.nix/badge)](https://flakehub.com/flake/maximoffua/zed-editor.nix)

## Usage

This flake can be used directly from GitHub or fetched from [FlakeHub](https://flakehub.com/). It uses [flake-parts](https://flake.parts/) for hadling multiple systems.
It provides the following outputs:

- `packages.${system}.default` = `packages.${system}.zed-editor`
- `overlays.default` which overwrites `zed-editor` from nixpkgs

Full list:

- `overlays.default`: Nixpkgs overlay
- `packages.aarch64-darwin.default`
- `packages.aarch64-darwin.zed-editor`
- `packages.aarch64-linux.default`
- `packages.aarch64-linux.zed-editor`
- `packages.x86_64-darwin.default`
- `packages.x86_64-darwin.zed-editor`
- `packages.x86_64-linux.default`
- `packages.x86_64-linux.zed-editor`


Add zed-editor.nix to your `flake.nix`:

```nix
{
  inputs.zed-editor.url = "https://flakehub.com/f/maximoffua/zed-editor.nix/*.tar.gz";

  outputs = { self, zed-editor }: {
    packages.zed-editor = zed-editor.packages.x86_64-linux.default;
  };
}
```
