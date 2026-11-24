# bsp-recomputer-mini-j501x

Board support for the Seeed reComputer Mini J5012 (J501 carrier with a Jetson AGX Orin 64GB module) on JetPack 7.2 (L4T R39.2.0).

This extension targets JetPack 7.2 on the 2026 feed only. The JetPack 6.x variant was not moved from the avocado-os repository.

## Using this extension

`bsp-recomputer-mini-j501x` is an [Avocado](https://avocadolinux.org) extension, a reusable fragment of
build- and runtime-configuration that you compose into your own Avocado project. To use it,
declare it as a package-sourced extension in your `avocado.yaml` and add it to a runtime:

```yaml
extensions:
  avocado-bsp-recomputer-mini-j501x:
    source:
      type: package
      version: "*"        # or pin an exact version

runtimes:
  my-runtime:
    extensions:
      - avocado-bsp-recomputer-mini-j501x
```

Then install and build:

```sh
avocado install   # fetches + installs the SDK, extensions and runtime deps from your config
avocado build     # builds the SDK compile steps, extensions and runtime images
```

`avocado install` pulls the extension from your target's package feed and merges its
config into your project; `avocado build` then produces the runtime.

## Provenance

See [PROVENANCE.md](PROVENANCE.md) for where the carrier files and package list came from.
