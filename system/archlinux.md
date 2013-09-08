# ArchLinux

Guía de uso básico

# Antes de empezar...

## Arquitectura CPU

    $ cat /proc/cpuinfo | sed -nr 's/.*(lm).*/\1/p' | sed 1q

*   **lm:** stands for long mode cpu (x86_64)
*   **_(no output)_:** i686

## Arquitectura OS

    $ uname -m

## ISOs

http://www.archlinux.org/download/

*   **Atención:** Elegir la versión **netinstall** de la arquitectura apropiada

## Listas de correo

https://mailman.archlinux.org/mailman/listinfo/arch-announce
Cosas a tener en cuenta al actualizar

https://mailman.archlinux.org/mailman/listinfo/arch-dev-public
Qué se queda obsoleto, porqué y por que va a ser reemplazado

## Información general

### [TODO]

*   Enlace a Begginers guide
*   Enlace a official guide

# Instalación

## [TODO]

*   kernel modules https://wiki.archlinux.org/index.php/Kernel_modules
*   particiones con **LVM** https://wiki.archlinux.org/index.php/LVM
*   **arch-install-scripts**
*   **systemd** https://wiki.archlinux.org/index.php/Systemd
*   booteo con **syslinux** https://wiki.archlinux.org/index.php/Syslinux

# Configurar la red

## [TODO]

*   método manual
*   rc.conf (o donde toque con systemd
*   netcfg
*   wicd
*   ip fija
*   dhcp
*   ethernet
*   wifi
*   wep
*   wpa
*   dns

# Actualización inicial del sistema

1.  Mirror mínimo:

        [root]$ wget --no-check-certificate -q -O - \
          "https://www.archlinux.org/mirrorlist/?country=ES&protocol=http&ip_version=4" |
          sed -n '/^#Server/ s/^#//' |
          tee /etc/pacman.d/mirrorlist

2.  Renovar repositorios 

    Después de actualizar los mirrors es bueno forzar la actualización de los
    repositorios

        [root]$ pacman -Syy

3.  Actualizar `pacman`

        [root]$ pacman -S --noconfirm pacman

4.  Inicializar claves de `pacman`

        [root]$ pacman-key --init
        [root]$ pacman-key --populate archlinux

5.  Usar `reflector` para optimizar `mirrorlist`

        [root]$ pacman -S --noconfirm reflector
        [root]$ reflector -l 5 --sort rate --save /etc/pacman.d/mirrorlist
        [root]$ pacman -Syy

6.  Actualizar el sistema

        [root]$ pacman -Syu

# Gestión de usuarios

*   Añadir usuario

        [root]$ useradd -m -g users \
          -G audio,optical,power,storage,wheel \
          -s /bin/bash archie

*   Definir password de usuario

        [root]$ passwd archie

*   Actualizar grupos

        [root]$ usermod -g users -G audio,optical,power,storage,wheel archie

*   Eliminar usuario

        [root]$ userdel -r archie

# Instalar herramientas básicas

    $ sudo pacman -S --noconfirm sudo vim openssh

Instalar `packer`

    $ sudo pacman -S base-devel wget git jshon
    $ mkdir -p ~/build/packer/
    $ cd ~/build/packer/
    $ wget https://aur.archlinux.org/packages/pa/packer/PKGBUILD 
    $ makepkg
    $ sudo pacman -U packer-*.pkg.tar.xz
