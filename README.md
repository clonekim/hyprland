# My Dotfiles

Hyprland 설정
> Arch(XFCE4) 기반에서 작성 했음 

## Prerequiste

### 필수
* hyprland
* hyprpaper
* hyprlock
* waybar
* rofi-wayland
* alacritty
* dunst
* nwg-drawer
* nwg-look
* xdg-desktop-portal-hyprland
* xdg-desktop-portal-wlr
* qt5-wayland
* qt6-wayland
* awesome-terminal-fonts
* ttf-font-awesome
* udiskie
* brightnessctl
* pamixer 
* grim
* cliphist
* wl-clipboard

### 옵션
* ttf-fira-sans 
* ttf-fira-code 
* ttf-firacode-nerd
* ttf-jetbrains-mono-nerd
* thunar
* fastfetch
* fuse2
* gtk4
* libadwaita
* jq
* python-gobject

## 로그인 

```
pacman -S greetd greetd-tuigreet
```

_/etc/greetd/config.toml_

```
[terminal]
type = "wayland"
vt = 1

[default_session]
command = "tuigreet"
user = "로그인 프롬프트에 표시할 사용자 ID 혹은 호스트명"
```

```sh
sudo systemctl disable lightdm.sevice
sudo systemctl enable greetd.service
```

## 모니터

`hyprctl monitors all` 로 확인 후 설정 할 것  
아래는 예시 
```
# See https://wiki.hyprland.org/Configuring/Monitors/
monitor=HDMI-A-1,1920x1080,auto,1,transform,3
monitor=DP-2,1920x1080,auto,1,transform,1
``` 


## 키바인딩

아래는 사용하지 않는다.  
`bind = $mainMod, M, exit # Exit Hyprland`


> 변경 전
`bind = $mainMod CTRL, RETURN, exec, rofi -show drun `

> 변경 후
`bind = $mainMod, D, exec, rofi -show drun # Open rofi`


## Gsetting

`gsetting set org.gnome.desktop.interface font-hinting "full"`  
`gsetting set org.gnome.desktop.interface font-antialiasing "grayscale"`  
`gsetting set org.gnome.desktop.interface font-name "나눔스퀘어 네오 9"`  
`gsetting set org.gnome.desktop.interface monospace-font-name "JetBrains Mono 9"`  
`gsetting set org.gnome.desktop.interface gtk-theme "Matcha-light-sea"`  
`gsetting set org.gnome.desktop.interface icon-theme "Papirus-Maia"`  
`gsetting set org.gnome.desktop.wm.preference theme "Matcha-light-sea"`  
`gsetting set org.gnome.desktop.wm.preference titlebar-font "나눔스퀘어 네오 9"`  

## fastfetch

``` sh
# -----------------------------------------------------
# Fastfetch if in Hyprland
# -----------------------------------------------------
if [[ $(tty) == *"pts"* ]]; then
    fastfetch
else
    echo
    echo "Start Hyprland with command Hyprland"
fi
```
