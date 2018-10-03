# brother-hll2310d
Arch linux packaging of `brother-hll2310d` printer drivers. Based on the
[`hll2300d` drivers](https://aur.archlinux.org/packages/brother-hll2300d/).

## Why?
The `hll2300d` drivers work reasonably well with the `hll2310d` machine, but it
doesn't support duplex printing. So this packages the official `hll2310d`
drivers to support duplex printing.

## Testing
```sh
$ makepkg --noarchive  # build but don't zip
$ makepkg --install    # build & install locally
```

## Installation
Using [yay](https://github.com/Jguer/yay):
```sh
$ yay -S brother-hll2310d
```

## License
MIT OR Apache-2
