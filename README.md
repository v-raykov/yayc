# yayc - Arch Linux Systemd-nspawn Yay Wrapper  

## Overview  

`yayc` is a script that allows you to manage AUR packages inside a `systemd-nspawn` container using `yay`. It ensures that installed package files (binaries, applications, and optional files) are correctly symlinked to the host system, making them accessible while keeping package management isolated.  

SHOULD BE RAN AS A REGULAR USER (without sudo) !

## Features  

- Runs `yay` inside a container to install or remove AUR packages.  
- Automatically creates symlinks for installed package files on the host system.
- Can use all regular pacman/yay features as normal but inside the container. 
- Cleans up symlinks when a package is removed.  

## Usage examples

`./yayc <yay-flag> [package-name]`

### Install an AUR package inside the container and link it to the host  
`./yayc -S brave-bin`

### Remove a package and clean up symlinks
`./yayc -Rns brave-bin`

## Bugs
- The .desktop symlink for Google Chrome does not work and is not recognized by gtk-launcher

## TODO List
- [ ] Add a setup script for easy configuration
- [ ] Remove the need for config file
