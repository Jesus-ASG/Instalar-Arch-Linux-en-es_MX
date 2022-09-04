# Instalar Arch Linux en idioma español México con teclado en español latino
Esta instalación se realizará en Oracle VM VirtualBox pero funciona en cualquier pc ya sea UEFI o BIOS
## Instalación

En este documento se supone que usted ya accedió al menú de instalación de Arch Linux, previamente descargando el ISO de la página oficial de [Arch Linux](https://archlinux.org) y creando una usb booteable o agregando el ISO en una máquina virtual según sea el caso.<br>

Al iniciar usted verá una pantalla parecida a la siguiente imagen, debe seleccionar la primera opción y presionar "enter"<br>
![image](https://user-images.githubusercontent.com/106128245/188297014-348f54f4-b505-41e0-9d6c-f6df2d02a9e4.png)<br>
## Configurar teclado
Una vez cargado el sistema hay que configurar el teclado con: loadkeys la-latin1<br>
![image](https://user-images.githubusercontent.com/106128245/188297289-cc56b4b4-a5a0-4adf-934c-75ef1ffa8a9d.png)
## Comprobar conexión a internet
Para comprobar conexión a internet puede usar: ping archlinux.org <br>
### Conexión exitosa
![image](https://user-images.githubusercontent.com/106128245/188297511-b9538bfa-9107-4569-9098-7c2bb42b567b.png)<br>
Si usted recibe mensajes constantemente, pulse ctrl+c para cerrarlos y continúe al siguiente paso
### Error en conexión
![image](https://user-images.githubusercontent.com/106128245/188297413-7915ae7b-2ab6-4b2e-83a2-7a59c23ef1ae.png)<br>
Si recibe un mensaje "Temporary failure in name resolution" puede conectar un cable ethernet directamente o activar su conexión wifi, como esta es una máquina virtual ya está conectada a internet.<br>
### Comandos para activar wifi
Escribir "ip link" para ver los puertos de conexión disponibles, debería aparecer una red wlan0<br>
Escribir "ip link set wlan0 up" <br>
Escriba "iwctl", presione enter e ingrese los comandos para conectar su wifi <br>
iwctl$ station wlan0 scan <br>
iwctl$ station wlan0 get-networks<br>
*Al ejecutar el comando anterior se listaran las redes wifi disponibles*<br>
Para conectarse <br>
iwctl$ station wlan0 connect "Tu red wifi" <br>
passwd$: "tu contraseña aquí" <br>
Por último escribir "exit" para salir de iwctl
iwctl$ exit


archinstall

teclado la-latin1


sudo pacman -S git
git clone aur.archlinux.org/yay.git
cd yay
makepkg -si

yay -S google-chrome
