# Instalar Arch Linux en idioma español México con teclado en español latino

## Descripción
Esta instalación se realizará en Oracle VM VirtualBox pero funciona en cualquier pc ya sea UEFI o BIOS <br>

En este documento se supone que usted ya accedió al menú de instalación de Arch Linux, previamente descargando el ISO de la página oficial de [Arch Linux](https://archlinux.org) y creando una usb booteable o agregando el ISO en una máquina virtual según sea el caso.<br>
También se supone que usted ya tiene sus particiones listas para que únicamente seleccione un disco de instalación. <br>

Al iniciar usted verá una pantalla parecida a la siguiente imagen, debe seleccionar la primera opción y presionar "enter"<br>
![image](https://user-images.githubusercontent.com/106128245/188297014-348f54f4-b505-41e0-9d6c-f6df2d02a9e4.png)<br>

## Configurar teclado
Una vez cargado el sistema hay que configurar el teclado con "loadkeys la-latin1" (el '-' se encuentra al lado derecho del 0)<br>
    
    loadkeys la-latin1
    
![image](https://user-images.githubusercontent.com/106128245/188297289-cc56b4b4-a5a0-4adf-934c-75ef1ffa8a9d.png) <br>

## Comprobar conexión a internet
Para comprobar conexión a internet puede usar: ping archlinux.org <br>

    ping archlinux.org

### Conexión exitosa
Si usted recibe mensajes constantemente, pulse ctrl+c para cerrarlos y continúe con la instalación <br>
![image](https://user-images.githubusercontent.com/106128245/188297511-b9538bfa-9107-4569-9098-7c2bb42b567b.png)<br>

### Error en conexión
Si recibe un mensaje "Temporary failure in name resolution" puede conectar un cable ethernet directamente o activar su conexión wifi, como esta es una máquina virtual ya está conectada a internet.<br>
![image](https://user-images.githubusercontent.com/106128245/188297413-7915ae7b-2ab6-4b2e-83a2-7a59c23ef1ae.png)<br>

### Comandos para activar wifi
Escribir "ip link" para ver los puertos de conexión disponibles, debería aparecer una red wlan0<br>
Escribir "ip link set wlan0 up" <br>
Escriba "iwctl", presione enter e ingrese los comandos para conectar su wifi <br>
iwctl$ station wlan0 scan <br>
iwctl$ station wlan0 get-networks<br>
*Al ejecutar el comando anterior se listaran las redes wifi disponibles*<br>
Para conectarse <br>
iwctl$ station wlan0 connect "Tu red wifi" <br>
passwd$: tu contraseña aquí <br>
Escribir "exit" para salir de iwctl <br>
iwctl$ exit <br>
Por último se puede verificar la conexión con "ping archlinux.org" y cancelarla con ctrl+c después de recibir respuesta <br>

## Instalación
Una vez que tenga internet ejecute el comando "archinstall"<br>

    archinstall

![image](https://user-images.githubusercontent.com/106128245/188323745-d66e8e84-e52b-4960-8df6-1b2e234a560e.png)<br>

Si llegara a ocurrir un error al ejecutar el comando puede usar "reboot" para resetear su máquina, en este caso debe volver a configurar teclado e internet, procure tener la imagen ISO de Arch Linux actualizada

    reboot

Si todo salió bien se cargará una pantalla similar a la siguiente, presionar enter en cada apartado. <br>
![image](https://user-images.githubusercontent.com/106128245/188323810-fa4c4d0c-75be-4ec2-9e63-e39d6a3b6753.png)

### Archisntall Language / Idioma de Archinstall
Tecla "enter" para configurar, elegir "Spanish" para español y presionar enter <br>
![image](https://user-images.githubusercontent.com/106128245/188323892-4909fb77-517b-4523-a8cd-dc6fe1f94614.png) <br>
Como resultado ahora las opciones se verán así <br>
![image](https://user-images.githubusercontent.com/106128245/188323964-ca070137-f525-43d7-8ee5-d6ed0b347984.png) <br>

### Distribución del teclado
Tecla "enter" para configurar, con las flechas de arriba y abajo busque la opción "la-latin1", entonces seleccione con la tecla "enter" <br>
![image](https://user-images.githubusercontent.com/106128245/188324153-b42b0824-e692-4e5a-817d-8684023cb56e.png)

### Región del servidor
Tecla "enter" para configurar, con las flechas de arriba y abajo busque y elija la opción de su país <br>
![image](https://user-images.githubusercontent.com/106128245/188324344-a8797ace-fc67-45e5-b965-f029512b4514.png)

### Idioma local
Tecla "enter" para configurar, con las flechas de arriba y abajo busque y elija su idioma <br>
![image](https://user-images.githubusercontent.com/106128245/188324475-aaa3a23f-fb5f-4770-89b5-aa0224bae018.png)

### Disco(s)
Tecla "enter" para configurar, seleccionar un disco para realizar la instalación <br>
![image](https://user-images.githubusercontent.com/106128245/188324611-b73ce392-1acd-4e61-8f47-9376e16069f9.png)

### Diseño del disco
Tecla "enter" para configurar, seleccionar la primera opción, como ya se comentó al inicio, esto borrará el disco seleccionado e instalará ahí Arch Linux<br>
![image](https://user-images.githubusercontent.com/106128245/188324665-2c9c3eae-a7c9-4359-a263-6691556038b4.png) <br>
Elegir la opción "ext4" <br>
![image](https://user-images.githubusercontent.com/106128245/188324867-8e77deb8-8e19-4e31-95d1-e89c4ae11891.png)<br>

### Nombre del host
Opcional, este es el nombre de host que aparecerá en terminal, ejemplo, nombre_usuario@nombre_de_host<br>
![image](https://user-images.githubusercontent.com/106128245/188326430-5d119118-2e1f-4f54-80fc-7cc083482709.png)<br>

### Contraseña del root
Escriba una contraseña y presione enter <br>
![image](https://user-images.githubusercontent.com/106128245/188326620-9c082d85-1a05-4790-8e20-5ec30f39854e.png) <br>
Si aparece el siguiente mensaje, elegir si <br>
![image](https://user-images.githubusercontent.com/106128245/188326664-4809ccbc-243a-4b06-9d2e-77ad0b335143.png) <br>
Repetir la contraseña <br>
![image](https://user-images.githubusercontent.com/106128245/188326692-43ff9e7f-38f7-48de-be31-d1c5dcf8c0fb.png) <br>

### Cuenta de usuario
Escriba un nombre de usuario para iniciar sesión, luego ingrese una contraseña, esta puede ser la misma que la anterior <br>
![image](https://user-images.githubusercontent.com/106128245/188326839-18d28ff7-bb4e-4aca-b3ab-bd4b4fe06ff4.png) <br>
![image](https://user-images.githubusercontent.com/106128245/188326863-8a118498-089d-444a-a8f2-b8238cc203fa.png) <br>
![image](https://user-images.githubusercontent.com/106128245/188326881-b5ff88c3-9ced-449d-98e1-df0f4b2d3d36.png) <br>
Es importante elegir si, ya que de lo contrario no podremos instalar paquetes por terminal <br>
![image](https://user-images.githubusercontent.com/106128245/188326981-9b31b390-4fbe-41da-9c93-857b7012fc3e.png) <br>
Al terminar de agregar usuarios seleccionar "Confirmar y salir" <br>
![image](https://user-images.githubusercontent.com/106128245/188327088-0cbfcc12-39e0-43ab-b079-55ed8744c934.png)

### Perfil
Esta opción es para cargar un entorno gráfico<br>
Seleccione "desktop" <br>
![image](https://user-images.githubusercontent.com/106128245/188327169-55df4d85-0d72-48bc-85d4-ad4de155be99.png) <br>
Seleccione el escritorio de su preferencia <br>
![image](https://user-images.githubusercontent.com/106128245/188327206-8d0a729f-9dd5-4c35-beb0-9740299d6ea7.png) <br>
Elija los gráficos dependiendo su máquina o puede presionar "esc" para descargar todos<br>
![image](https://user-images.githubusercontent.com/106128245/188327365-56702a55-c324-4f47-b151-e75bd489c922.png) <br>

### Audio
Seleccione "pipewire" <br>
![image](https://user-images.githubusercontent.com/106128245/188327410-2c552a2b-aa79-4f3c-b463-9e82c1ec904b.png) <br>

### Configuración de la red
Seleccione "NetworkManager" <br>
![image](https://user-images.githubusercontent.com/106128245/188327468-d4f46e69-982d-48de-82ad-c269db93f940.png) <br>

### Zona horaria
Con las flechas de arriba y abajo busque y elija su zona horaria <br>
![image](https://user-images.githubusercontent.com/106128245/188327560-340fa2f6-9a02-474e-9070-f4f864d4e24e.png) <br>

### Repositorios adicionales
Si se desea correr aplicaciones de 32 bits, se puede habilitar la casilla "multilib"<br>
![image](https://user-images.githubusercontent.com/106128245/188328727-4fae3ee7-0644-4096-8dab-b1f585245d37.png)<br>

### Confirmar instalación
Después de seguir todos los pasos anteriores tendremos algo parecido a esto: <br>
![image](https://user-images.githubusercontent.com/106128245/188328760-df282e9b-9daa-44be-a477-6066351aff0a.png) <br>

Seleccionar "Instalar" <br>
![image](https://user-images.githubusercontent.com/106128245/188328803-cfda18d6-06f8-4ef8-b389-0e259602daba.png) <br>

Desplegará una pantalla con información, presionar "enter" para empezar a instalar <br>
![image](https://user-images.githubusercontent.com/106128245/188328882-d8ed9b6b-95f2-419c-949e-1d8f6e21f34a.png) <br>

Muestra información de la instalación, ahora simplemente esperamos a que termine de instalar <br>
![image](https://user-images.githubusercontent.com/106128245/188328930-e9508a8e-0e62-42a0-b1b9-6544ea359b9f.png) <br>

Aquí seleccionar sí <br>
![image](https://user-images.githubusercontent.com/106128245/188329309-9062de5e-f5ac-490c-9334-cbb1141bd9f5.png) <br>

Por último mostrará este mensaje de que todo ha salido bien <br>
![image](https://user-images.githubusercontent.com/106128245/188329423-835c9379-6fb2-45b4-b418-99b5dc135add.png) <br>
Escriba "reboot" para reiniciar, una vez apagada la máquina quite el usb o disco de instalación <br>
![image](https://user-images.githubusercontent.com/106128245/188329476-3f6d729e-f7b7-403a-9ff3-40e7f1994e4c.png) <br>
*En Oracle VM Virtualbox así se quitan los dispositivos de instalación* <br>
![image](https://user-images.githubusercontent.com/106128245/188329561-f12f3e57-8c59-4986-b6ff-aee34b24ea9e.png) <br>
Al momento de que usted vuelva a iniciar su máquina aparecerá de la siguiente forma, deberá elegir "Arch Linux" <br>
![image](https://user-images.githubusercontent.com/106128245/188329693-269ea7d5-a49d-40c5-86ef-eb64a2fac91d.png) <br>

Inicie sesión con su usuario y contraseña <br>
![image](https://user-images.githubusercontent.com/106128245/188329747-a93d25dc-e5c5-45df-83d1-4344201f03fd.png) <br>
![image](https://user-images.githubusercontent.com/106128245/188329763-05a96c4c-ecfd-439a-9dab-667cb7255aaa.png) <br>
![image](https://user-images.githubusercontent.com/106128245/188329817-a47cdb8b-b831-4dc0-a712-bbbfb1afb457.png)<br>

### Ver el sistema operativo en terminal
Se puede ver el sitema operativo y características desde la termina con el comando "neofetch" <br>

    sudo pacman -S neofetch
    
![image](https://user-images.githubusercontent.com/106128245/188329931-fac4c63c-9ef2-462f-825e-536ca962c516.png) <br>
Y a continuación <br>

    neofetch
    

![image](https://user-images.githubusercontent.com/106128245/188329966-720029ef-4a1b-4035-b5cf-b9c3e2bdd35e.png)


## Bonus: Instalar google chrome
Ejecute los siguientes comandos, presione "enter" y "s" cada que sea necesario <br>

Desplazarse a la carpeta de descargas <br>

    cd Descargas/

Instalar git <br>
    
    sudo pacman -S git
    
Clonar el repositorio de yay<br>
    
    git clone https://aur.archlinux.org/yay.git
    
Desplazarse al repositorio<br>
    
    cd yay
    
Instalar yay<br>
    
    makepkg -si
    
Instalar google chrome<br>
    
    yay -S google-chrome
    
Ahora solo queda reiniciar su computadora <br>

   reboot
   
### Navegador de google chrome instalado
![image](https://user-images.githubusercontent.com/106128245/188330789-410f2fb8-a6fe-422e-a3fa-f7d54ed76e5a.png)

