# dwm
This is my fork of the suckless window manager [dwm](https://dwm.suckless.org/). It uses the [catppuccin](https://github.com/catppuccin/catppuccin) color scheme.

## Usage
- clone the repo to your home directory
```sh
git clone https://github.com/MichiTheGenius/dwm.git ~/
```
- cd into the dwm directory and compile dwm in order to use it 
```sh
cd dwm
make
sudo make install
```

- create a `dwm.desktop` file for using for using dwm with the lightDM login manager and copy the following contents into it
```sh
sudo nano /usr/share/xsessions/dwm.desktop

[Desktop Entry]
Encoding=UTF-8
Name=dwm
Comment=Dynamic window manager
Exec=dwm
Icon=dwm
Type=XSession
```

- install the `acpilight` package and add your user to the `video` group
- this enables the ability to control the screen brightness
```sh
sudo pacman -Sy acpilight
sudo usermod -aG video NAME_OF_USER
```

- this fork of dwm features the `autostart` patch
- in order to use it create a `.dwm` directory in your home directory and add a `autostart.sh` script to it
- the script should contain programs like a compositor or sltatus
```sh
mkdir .dwm
cd .dwm
touch autostart.sh
chmod +x autostart.sh

#!/bin/bash
slstatus &
picom &
nitrogen --restore &
```
