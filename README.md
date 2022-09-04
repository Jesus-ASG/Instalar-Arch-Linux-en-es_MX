# Instalar-Arch-Linux-en-es_MX
Guía para instalar Arch Linux con distribución de teclado en español latino

instalar arch linux sin complicaciones

1 colocar teclado

loadkeys la-latin1

ping archlinux.org
Si se tiene ping continuar con la instalación
si no, activar el wifi
ip list
ip link wlan0 up

iwctl
$ station wlan0 scan
$ station wlan0 get-networks

$ station wlan0 connect "Tu red wifi"
passw: introduces tu contraseña
$ exit

archinstall

teclado la-latin1


sudo pacman -S git
git clone aur.archlinux.org/yay.git
cd yay
makepkg -si

yay -S google-chrome
