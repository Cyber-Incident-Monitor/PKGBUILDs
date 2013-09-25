PKGBUILDs
=========

These packages come from the [Arch Linux AUR] and have been adjusted to run on the current [Arch Linux ARM] release for the Raspberry Pi. The modifications will be merged back to the AUR, but unfortunately the maintainer has not yet responded.

# Packages


## [dionaea-git]

changes:

  - add armv6 as supported architecture
  - add sqlite3 as dependency
  - add automake as build dependency
  - include git://git.carnivore.it/dionaea.git as source
  - add dionaea.conf and ihandlers.py as backup
  - remove rc files and add systemd file

status: not asked to merge changes


## [libemu]

changes:

  - add armv6 as supported architecture

status: asked to include armv6, no response yet


## [liblcfg]

changes:

  - add armv6 as supported architecture

status: asked to include armv6, no response yet

# Usage

First install the necessary tools for building: ```pacman -S base-devel```

*dionaea-git* needs *udns* which is available in the AUR.

Download, build and install udns:

```
wget https://aur.archlinux.org/packages/ud/udns/udns.tar.gz
tar -zxvf udns.tar.gz
cd udns
makepkg
sudo pacman -U *.pkg.tar.xz
```


Then check out this repository (you may need to install git first: ```pacman -S git```). Now you can build and install our packages:

```
cd liblcfg/
makepkg
sudo pacman -U *.pkg.tar.xz
cd ..

cd libemu/
makepkg
sudo pacman -U *.pkg.tar.xz
cd ..

cd dionaea-git/
makepgk
sudo pacman -U *.pkg.tar.xz
```

If you want to build the packages as root you need to run ```makepkg --asroot```.

  [Arch Linux ARM]: http://archlinuxarm.org/
  [Arch Linux AUR]: https://aur.archlinux.org/
  [dionaea-git]: https://aur.archlinux.org/packages/dionaea-git/
  [libemu]: https://aur.archlinux.org/packages/libemu/
  [liblcfg]: https://aur.archlinux.org/packages/liblcfg/
