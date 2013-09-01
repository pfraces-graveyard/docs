    $ echo foo | dzen2 -p
    $ echo foo | dzen2 -y 18 -w 100 -ta l -p

    $ sudo python2 ./gerix.py (he modificado el script /usr/bin/gerix para que use
       python2, asi que con sudo gerix deberia funcionar)

    $ sudo netcfg <profile>
    $ sudo netcfg down <profile>
    $ sudo wifi-select wifi

    $ lspci | grep -i net
    $ lsmod

    $ while true
    > do
    >     for ico in *
    >     do echo -n "^i($PWD/$ico) "
    >     done |
    >         cut -d' ' -f1-50
    > done |
    >     dzen2 

    $ fc-list
    $ xfd -fa terminus
    $ xfontsel

    $ asunder

    $ luit -g2 'CP 437' (desde telnet y con terminus-font, muestra semigraficos)
    $ telnet | konwert cp437-utf8 (con terminus-font, tb)

    $ iw dev wifi connect -w ONO39D370 
    $ startx -- :1 vt8
    $ archey # muestra el logo de arch y las caracteristicas del OS en modo texto
    $ tar -h # entara el contenido de un enlace simbolico y no el enlace en si
    $ usermod -g users -G audio,disk,optical,power,storage,wheel pau

crear iso de un cd
------------------
    $ sudo wodim -v -speed=2 -dev='/dev/scd0' source.iso

    $ wodim -devices
    $ wodim -scanbus | grep RW | awk '{print $1}'

reporiducir dvd
---------------
    $ mplayer dvd://<numero de capitulo> -dvd-device /dev/sr0

    # cdrom es un enlace simbolico a sr0. se puede crear otro que se llame dvd
    # mplayer buscara por defecto en /dev/dvd
    $ mplayer dvd://1

cambiar salida de audio
-----------------------
    $ cp /home/pau/.snd.output/bluetooth /home/pau/.asoundrc
    $ cp /home/pau/.snd.output/headset /home/pau/.asoundrc

    # no son necesarios desde que hice el script, que ademas reinicia mpd
    $ switch_sound_output.sh

nvidia
------
    # configura el driver propietario de nvidia
    # no es necesario con nouveau
    sudo nvidia-settings

qemu
----
    qemu-img create -f qcow2 hd.qcow 700M
    qemu-system-x86_64 -cdrom file.iso -boot d hd.qcow

instalar diver wifi
-------------------
    # ya no es necesario desde que uso el driver libre ssb que viene con la
    # distribucion, pero lo dejo aqui hasta que lo pueda documentar
    $ cd /home/pau/build/wifi
    $ sudo make
    $ sudo make install
    $ sudo depmod
    $ sudo modprobe wl
    $ reboot

dns
---
    # opendns
    208.67.222.222
    208.67.220.220

    # google
    8.8.8.8
    8.8.4.4

hacer backups
-------------
    $ cd $HOME
    $ sudo tar czhf backup.laptop.tar.gz --exclude="distro/*" dev/ doc/

montar usb
----------
    sudo mount /dev/disk/by-label/ZIP\\x20ZIP /mnt/storage/
    sudo mount /dev/cdrom /mnt/storage/
    sudo umount /mnt/storage/

montar andriod
--------------
    $ sudo mount /dev/sdb /mnt/storage -t vfat
    # el comando anterior tira error pero es necesario para que se cree el nodo
    # /dev/sdb1, el cual si podemos montar con
    $ sudo mount /dev/sdb1 /mnt/storage -t vfat

    # al pasar ficheros, desconectar desde el terminal antes de desconectar el
    # usb

pacman/packer
-------------
    # para solucionar el error de firmas al actualizar paquetes
    $ sudo pacman-key --refresh-keys

    # cuando packer requiere variables de entorno a traves de sudo
    $ sudo -k packer ...

    # elimina paquete y dependencias
    $ sudo pacman -Rsnc <package>

    # mostrar los paquetes de base y base-devel
    $ pacman -Ss base | grep "(base[-]*"

    # desbloquear pacman
    $ sudo rm /var/lib/pacman/db.lck

    # programas instalados recientemente
    $ history | egrep "(pacman|packer)" | grep -v vi | grep -v history

    # ver que paquete ha instalado un paquete concreto
    $ packmar -Qi <paquete>
    # muestra informacion de <paquete> y bajo la etiqueta
    # "requerido por:" muestra el paquete que lo instalo

nginx/fastcgi
-------------
    # configurar nginx con /etc/nginx/conf/nginx.conf
    # reiniciar nginx despues de modificar su configuracion
    $ sudo rc.d restart nginx

    # nginx esta configurado para enviar las peticiones 
    # * de localhost/dev al puerto 9000
    # * de localhost/werc al puerto 9001

    # lanzar servicios fastcgi
    $ cgi-fcgi -start -connect localhost:9000 ./hello
    $ cgi-fcgi -start -connect localhost:9001 /usr/sbin/fcgiwrap

    # aqui ./hello es una aplicacion en c compilada con:
    $ gcc -o hello hello.c -lfcgi







