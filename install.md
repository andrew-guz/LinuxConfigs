# Programs
- git
- base-devel
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
- firefox - needed to download normal browser
- Arch specific: yay
- Arch specific: yay -S google-chrome

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

### Set resoultion, cusror size and DPI
see .Xresources file - DPI is there

.Xresources must be called from .xinit:
```
xrdb ~/.Xresources
```

### Set numlock ON
Change '/etc/slim.conf` - numlock can be set there

### Set slim normal background and theme
Copy any lovely theme from /usr/share/slim/themes/ and add your custom background to it
Then change theme in /etc/slim.conf

### Set Rofi theme
run rofi-theme-selector FROM TERMINAL - not working right now

Create ~/.config/rofi/config.rasi with content
```
configuration {
  modes: [ combi ];
  combi-modes: [ window, drun, run ];
}
@theme "gruvbox-light"
```
where you can change theme

Themes can be found at https://github.com/newmanls/rofi-themes-collection.

 # Questions
- normal lock screen
- git push from console
- grub resolution
- grub images
