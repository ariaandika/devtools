# What i do in my arch

## Installed

- base base-devel linux linux-headers linux-firmware
- xorg xorg-xinit i3-wm i3blocks i3lock xdotool
- iwd dhcpcd ntfs-3g grub efibootmgr dosfstools mtools os-prober
- amd-ucode xf86-video-amdgpu
- sudo pulseaudio git dmenu fzf zsh htop feh imagemagick 
  tmux unzip zip vim nvim ripgrep xcompmgr
- arandr
- nodejs github-cli npm vlc opera alacritty mariadb obs-studio qutebrowser
- adobe-source-han-sans-js-fonts

manual

- vscode

## System

- visudo
- /etc/local.gen
- /etc/hostname
- /etc/hosts
- /etc/default/grub

can change background ?

- systemctl dhcpcd
- systemctl iwd
/etc/systemd/system/multi-user.target.wants/iwd.service → /usr/lib/systemd/system/iwd.service
- /etc/systemd/system/startup.service

## System references

- /etc/passwd
- /etc/shells
- df -h

## Config

- i3, .config/i3
- nvim, .config/nvim
- vscode, .config/Code/User/settings.json
- .ssh, .ssh
- alacritty, .config/alacritty
- tmux, .config/tmux
- zsh, .zshr, .zprofile
- xinit, .xinitrc
- boot, .config/session/boot.sh

## How to

- battery, `cat /sys/class/power_supply/BAT0/capacity`
- brightness, `/sys/class/backlight/amdgpu_bl0/brightness`
- create temporary file, `/tmp`
- shortcut a key to shell, in alacritty keymap, at the bottom of config file
