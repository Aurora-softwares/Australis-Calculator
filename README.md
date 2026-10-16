# Australis Calculator

## Current status

The current source prints `Hello, World!`; its commented argument loop is not executable calculator behavior.

`Calculator.hyproj` builds `calculator.exec`. The Australis OS aggregate includes
this project and installs the executable at `/System/Bin/calculator.exec` in the read-only
HyFS 2 boot image. Run it by its bare name `/System/Bin/` through the current
recovery shell's `PATH`, or use `run /System/Bin/calculator.exec`.

## Planned direction

Add expression parsing and useful numeric output after the external-command shell is established.

Build this checkout with:

```bash
mkdir -p build
hy build Calculator.hyproj -o build/calculator.exec
```

AUEX `.exec` files currently run in the checked interpreter. Native ring-3
processes and a normal userland shell are later milestones. The boot root is
read-only; writable application data belongs on the separate `/data` volume.
The OS-level build, supported APIs, and packaging rules are described in the
Australis OS `applications/README.md`. This README describes this project's
actual source rather than treating its filename as proof of a finished feature.
