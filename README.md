# ztos-build

How ztOS is built: the installer, the generic system image (GSI) and the
emulator target. Part of ztOS BETA-1.1; the other repositories are
[ztos-core](https://github.com/Zerone-Laboratories/ztos-core) (the system and
its apps), [ztos-ial](https://github.com/Zerone-Laboratories/ztos-ial) (the
hardware interfaces) and one `ztos-device-<phone>` per phone, such as
[ztos-device-samsung-starlte](https://github.com/Zerone-Laboratories/ztos-device-samsung-starlte).

| Path | What |
|---|---|
| `installer/` | `ztos build --target gsi`, `starlte` or `qemu`: the root filesystem, from Arch Linux ARM |
| `devices/qemu-virt/` | the emulator's device layer |
| `os/overlay-qemu/` | files only the emulator image gets |
| `scripts/split/` | how the old ztOSMobile tree was cut into these repositories |

The GSI holds no kernel, no `/vendor` and no user: a phone gets those from its
device layer, or from [ztConflo](https://github.com/Zerone-Laboratories/ztconflo)
for phones without one (`ztconflo build <phone> --gsi ztos-gsi-<version>-aarch64.tar.zst`).
See `installer/README.md`.
