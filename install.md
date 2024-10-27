# Programs
- git
- nano - CLI text editor
- mc - CLI Far Manager
- btop- like htop but better
- ranger - CLI file browser
- alacritty - terminal
- rofi - instead of dmenu for i3
- feh - view images and set background
- xterm
- zsh
- Arch specific: xorg-server
- Arch specific: xorg-xinit
- Arch specific: xorg-apps
- i3
- polybar (do not forget to set launch.sh executable)
- slim (systemctl enable/start slim)
- xcompmgr - windows butify
- nm-connection-editor - will allow to configure network

## Arch specific
yay - should be installed from AUR to install from AUR

## How to

### Change layout
See .xinitrc
```
setxkbmap -layout us,ru -option grp:win_space_toggle
```

### Set background
See .xinitrc
```
feh --bg-scale XXX.jpg
```

### Start windows composer
See .xinitrc
```
xcompmgr -c -C -o.75 -f -s &
```

### Hot to set resoultion and DPI
see .Xresources file - DPI is there

 # Questions
- cursor
- normal lock screen
- git push from console
- grub resolution
- grub images
