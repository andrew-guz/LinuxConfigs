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
- Arch specific: man-db
- unzip
- xclip - clipboard
- scrot (scrot -s) interactive screenshot
- pavucontrol
- Arch specific: wireguard-tools

### Work specific programs
- Arch specific: yay -S visual-studio-code-bin
- Arch specific: boost
- Arch specific: yaml-cpp
- Arch specific: doxygen + graphviz
- https://gitlab.softcom.su/bogdan.gulyaev/arch-repo
- Arch specific: yay -S odb libodb-boost libodb-pgsql
- Arch specific: yay -S cmake-format
- Arch specific: pacman -S prettier

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

Arch specific: yay -Syy oxygen-cursors

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

### Fix fonts in VSCode
Arch specific: yay -S ttf-droid OR sudo pacman -S ttf-droid

### Git in console and app without login/password
Use ssh version and set no passpharese for the key (check ssh keys in github and gitlab)

### Set nice lock
For i3 see config and MOD+l.

Use i3lock with -i /path/to/image.png

### Set QEMU
```
sudo pacman -S qemu-full libvirt virt-manager dnsmasq
sudo systemctl enable/start libvirtd
sudo usermod -aG libvirt,kvm %USER%
sudo virsh net-start default
sudo virsh net-autostart default
```

### Polybar scripts
https://github.com/polybar/polybar-scripts

### Set bluetooth
See wiki

For Arch: https://wiki.archlinux.org/title/Bluetooth

I used blueberry as GUI

### Polybar bluetooth
https://github.com/polybar/polybar-scripts/tree/master/polybar-scripts/system-bluetooth-bluetoothctl

And I added right-click = blueberry to configure it

### Set refresh rate 75Hz

Create xorg.conf (X -configure from terminal with no X) and put it to /etc/xorg.conf

Using `cvt 2560 1440 75` get a Modeling string and put it to xorg.conf

Add next lines to Monitor section
```
	Modeline "2560x1440@75.00"  397.25  2560 2760 3040 3520  1440 1443 1448 1506 -hsync +vsync
	Option "PreferredMode" "2560x1440@75.00"
```

### Subline:
See https://www.sublimetext.com/docs/linux_repositories.html

# Questions
- start application on special workplace in fullscreen
- different language in each window

