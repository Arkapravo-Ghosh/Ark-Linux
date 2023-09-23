![](https://img.shields.io/badge/Work%20In%20Progress-informational)
# Ark GNU/Linux
A simple and easy to use GNU/Linux distribution with KDE Plasma desktop environment based on Arch Linux.

## Build Project from Source
### Requirements
- [Arch Linux](https://archlinux.org/) (or any Arch-based Linux distribution)
> **NOTE:** For a friendly Arch Linux installation guide, visit [Arkapravo-Ghosh/arch-linux-install-guide](https://github.com/Arkapravo-Ghosh/arch-linux-install-guide).
- [Git](https://git-scm.com/)
> **NOTE:** For Arch Linux, Git can be installed by running the following command:
> ```bash
> sudo pacman -S git
> ```

### Clone Repository
```bash
git clone --recurse-submodules https://github.com/Arkapravo-Ghosh/Ark-Linux
```

### Install Dependencies
```bash
sudo pacman -S archiso
```

### Build ISO
```bash
cd Ark-Linux
```
```bash
sudo mkarchiso -v -w arklinuxcache -o arklinuxbuild arklinux
```
> **WARNING:** If [`./build.sh`](build.sh) is interrupted, run [findmnt(8)](https://man.archlinux.org/man/findmnt.8) to make sure there are no mount binds before deleting it - otherwise, you may lose data (e.g. an external device mounted at /run/media/user/label gets bound within arklinuxcache/x86_64/airootfs/run/media/user/label during the build process).

The ISO will be located inside `arklinuxbuild` directory.
> **NOTE:** To clean up the build and cache directory, run the following command:
> ```bash
> sudo rm -rf arklinuxbuild
> sudo rm -rf arklinuxcache
> ```

### Test ISO on QEMU
```bash
run_archiso -u -i arklinuxbuild/Ark\ Linux-*-x86_64.iso
```
> **NOTE:** Requires [QEMU](https://wiki.archlinux.org/title/QEMU).

For more information on Archiso, [Click Here](https://wiki.archlinux.org/title/Archiso).

## License
[Gnu GPL v3.0](LICENSE)

## Credits
- [Arkapravo Ghosh](https://github.com/Arkapravo-Ghosh)

## References
- [Arch Linux](https://archlinux.org/)
- [Archiso](https://gitlab.archlinux.org/archlinux/archiso)
- [QEMU](https://www.qemu.org/)

## See Also
- [Arkapravo-Ghosh/arch-linux-install-guide](https://github.com/Arkapravo-Ghosh/arch-linux-install-guide)
