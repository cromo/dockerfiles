# devkitARM

Everything needed to build GBA and NDS games.

## Usage

```sh
$ docker run --rm -it -v $(pwd):/source cromo/devkitarm
```

### Examples

devkitPro is installed in `/opt/devkitPro`, with examples for the GBA and the NDS in the `examples` directory under that. Each contains several folders to demonstrate how to use various capabilities of the systems. To build an example, `cd` into its directory and run `make`. This should result in a `.gba` or `.nds` file being built, which can be run in emulators or put on flash carts.
