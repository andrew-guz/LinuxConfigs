# Programs
- git
- base-devel
- cmake
- ninja
- mold
- nano - CLI text editor
- hwinfo
- mc - CLI Far Manager
- btop- like htop but better
- ranger - CLI file browser
- alacritty - terminal
- rofi - instead of dmenu for i3
- feh - view images and set background
- xterm
- zsh
- smbclient
- cifs-utils
- Arch specific: gvfs-smb
- Arch specific: xorg-server
- Arch specific: xorg-xinit
- Arch specific: xorg-apps
- i3
- polybar (do not forget to set launch.sh executable)
- slim (systemctl enable/start slim)
- xcompmgr - windows butify
- nm-connection-editor - will allow to configure network
- firefox - needed to download normal browser
- telegram-desktop
- Arch specific: yay
- Arch specific: yay -S google-chrome

### Work specific programs
- Arch specific:  wireguard-tools
- Arch specific: yay -S visual-studio-code-bin
- Arch specific: boost
- Arch specific: yaml-cpp
- Arch specific: doxygen + graphviz
- https://gitlab.softcom.su/bogdan.gulyaev/arch-repo
- Arch specific: yay -S odb libodb-boost libodb-pgsql

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
Copy any lovely theme from `/usr/share/slim/themes/` and add your custom background to it
Then change theme in `/etc/slim.conf`

### Set Rofi theme
run rofi-theme-selector FROM TERMINAL - not working right now

Create `~/.config/rofi/config.rasi` with content
```
configuration {
  modes: [ combi ];
  combi-modes: [ window, drun, run ];
}
@theme "gruvbox-light"
```
where you can change theme

Themes can be found at https://github.com/newmanls/rofi-themes-collection for example.

### Set cursor theme
Install some themes from repository. For example from https://github.com/wo2ni/Oxygen-Cursors

Themes can be found in `/usr/share/icons`

Add to your .Xresources
```
Xcursor.theme: XXX
```

### Set GRUB resolution and theme
Check resolution with `hwinfo --framebuffer` or `videoinfo` from GRUB

Edit `/etc/default/grub file and` and add next resolution lines:
```
GRUB_GFXMODE=2560x1440x16,auto // your resolution here, auto if for error fallback
GRUB_GFXPAYLOAD_LINUX=keep
```
There also your can set wallpapper OR theme (only one of it). Wallpaper must be tga, png, 8-bit jpg. Better store wallpapper somewhere in a boot section, cause it can be separate drive.
```
#GRUB_BACKGROUND="/path/to/wallpaper"
#GRUB_THEME="/path/to/gfxtheme"
GRUB_BACKGROUND="/boot/grub/wallpapper.jpg"
```
Colors of text can be set in
```
GRUB_COLOR_NORMAL="light-gray/black"
GRUB_COLOR_HIGHLIGHT="white/black"
```
where black means tranparent

Do not forget to recreate grub configuration with `grub-mkconfig -o /boot/grub/grub.cfg`

### Add wiregurad connection if you have a config file
```
sudo nmcli con import type wireguard file PATH_TO/wg.conf
```

### Show ip and vpn in polybar
https://github.com/mntzrr/polybar-ipfinder

### Fix fornts in VSCode
Arch specific: yay -S ttf-droid

# Questions
- normal lock screen
- git push from console
- start application on special workplace in fullscreen
- different language in each window
- stange font in default VSCode terminal
- program to take sceensots
