
# fix rdp server Error connecting to user session in archlinux




## XRDP install GUIDE 

[xrdp archlinux wiki](https://wiki.archlinux.org/title/xrdp)






## Installing Yay on Arch Linux 
Step 1: update package

```bash
  sudo pacman -Syu
```
Install the rerquired base-devel (contains tools such as makepkg etc) and git (required for cloning the yay git repository).


```bash
  sudo pacman -S --needed base-devel git
```

Step 2: Clone the Yay git repo and switch to it

```bash
  git clone https://aur.archlinux.org/yay.git
```

Once done, switch to the cloned directory:

```bash
  cd yay
```
 You'll see a PKGBUILD file here. Use the following command to build the package from here:

```bash
  makepkg -si
```

## Using Yay for package management

Search for packages with:

```bash
  yay search_term
```

Install the packages with:

```bash
  yay -S package_name
```
Remove packages with:

```bash
  yay -R package_name
```

To delete a package with its dependencies:

```bash
  yay -Rns package_name
```

Upgrading (only) the AUR packages:

```bash
  yay -Sua
```


## Fix archlinux error connection to user session  For XFCE

To create a script named xrdp_start_wm.sh that starts an XFCE desktop environment for use with XRDP, you can follow these steps:

```bash
  nano xrdp_start_wm.sh
```
Paste the following content into the file:

```bash
  #!/bin/bash

  # Start XFCE Desktop for XRDP

  # Set the session manager
  export XDG_SESSION_DESKTOP=xfce
  export XDG_DATA_DIRS=/usr/share/xfce4:/usr/local/share
  export XDG_CONFIG_DIRS=/etc/xdg/xfce4:/etc/xdg

  # Start XFCE desktop
  exec startxfce4

```
restart xrdp service

```bash
  sudo systemctl restart xrdp
```


















