
# switch language in archlinux 

edit file in `/etc/X11/xorg.conf.d/00-keyboard.conf`

```bash
sudo nano /etc/X11/xorg.conf.d/00-keyboard.conf
```

if you press the button `ctrl + alt ` to switch language 

```bash
Section "InputClass"
    Identifier "keyboard"
    MatchIsKeyboard "yes"
    Option "XkbLayout" "us,th"
    Option "XkbOptions" "grp:ctrl_alt_toggle"
EndSection
```
arch wiki `how to config /X11/xorg.conf.d/00-keyboard.conf`

 - [How to switch language ](https://wiki.archlinux.org/title/Xorg/Keyboard_configuration)