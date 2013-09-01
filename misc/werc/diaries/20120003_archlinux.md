***** ArchLinux *****
    * https://wiki.archlinux.org/index.php/Beginners%27_Guide
    * https://wiki.archlinux.org/index.php/General_Recommendations
***** ArchBang *****
    * http://wiki.archbang.org/index.php?title=Table_of_Contents
    * http://wiki.archbang.org/index.php?title=ArchBang_Document
    * http://willensky.blogspot.com/2010/01/how-to-setup-arch-linux.html
    * https://wiki.archlinux.org/index.php/ArchBang
    * http://archbang.org/
    * http://archvortex.blogspot.com/2011/09/simple-archbang-installation-
      guide.html
    * http://paraisolinux.com/?p=3651
***** OpenBox *****
    * https://wiki.archlinux.org/index.php/Openbox
***** instalacion *****
    * instalar desde cd
          o utc
          o europe/madrid
          o configurar particiones
          o grub en sda
          o root/root
          o pau/pau
          o rc.conf
                # LOCALE=es_ES.utf8
                # KEYMAP=es
                # HOSTNAME=pau.work
Después de instalar archbang como entorno de escritorio lo primero que echo en
falta es:
**** sistema ****
    * no hay telnet (por lo que no puedo conectar a la .0.3) (como puedo
      conectar por ssh evitaré hacerlo por telnet)
    * no hay ssh (para conectar a la .0.3)
    * mi ip es la .0.115 (antes era la .0.26)
**** modo grafico ****
    * el teclado esta en ingles
    * el escritorio ocupa un 80 por ciento de la pantalla
    * solo usa una pantalla (la otra esta en negro)
    * la hora sale en formato 12h
    * firefox nightly
          o muestra los inputs en fondo negro (creo que es por el theme de
            openbox)
          o el menu de la wiki sale al final de la página
***** post instalacion *****
**** todo ****
   1. cambiar teclado grafico
   2. firefox
          o salvar pestañas
          o google como home
          o ocultar toolbars
                # bookmark bar
                # menu bar
          o tab utilities
          o eliminar marcadores por defecto
                # bookmarks toolbar
                # bookmarks menu
          o sync
          o pentadactyl
          o firebug
          o actualizar desde packer y evitar avisos de actualización
          o motores de búsqueda
          o crear carpeta $HOME/downloads y hacer que firefox apunte alli
          o al actualizar a la última versión de nightly no funcionan algunas
            extensiones (pentadactyl, tabutilities)
          o el menu de la wiki sale al final de la página
          o noobs: arrancar sin complementos (-safe-mode sólo funciona si no
            hay un firefox activo, y abre un diálogo previo)
                # he visto que con root se abre normal, talvez desde otro
                  usuario que no sea pau se abra normal también, por lo que
                  podría crear un usuario 'guest' con password 'guest' o
                  '00reset' y que arranquen firefox desde él
   3. copy/paste rxvt
   4. configurar locales
          o man: can't set the locale; make sure $LC_* and $LANG are correct
   5. rankmirrors mirrorlist
   6. actualizar (packer)
   7. instalar vim
   8. sudo no pide password
   9. papelera
  10. configurar impresoras
          o b/n (desarrollo)
          o color (isa)
          o ps
          o pdf
          o raw file
  11. usar terminus como fuente de consola gráfica
  12. instalar ssh
  13. ip fija
  14. aparecer como ansi
  15. configurar teclas de función
  16. configurar semigráficos
  17. cambiar el theme de openbox por un mas claridad
  18. bordes en las ventanas
  19. status bar
          o tray
                # hora en formato 24h
                # color picker
                # notificador gmail
                # bateria / corriente
                # en la segunda pantalla sólo aparece la hora (quiero que
                  aparezca todo el tray repetido)
          o cambiar colores a unos que se integren mejor con el tema de ObConf
          o menu inicio desde icono
  20. conky coherente con openbox theme
  21. wallpapers
  22. combinación de teclas
  23. cambiar de escritorio
  24. instalar htop
  25. resolución pantalla
  26. dual head
  27. activar numlock al inicio
  28. slimlock
          o ampiar el tiempo de inactividad antes de que se vuelva negra la
            pantalla
          o bloquear por inactividad
  29. instalar gvim
          o cambiar a gvim como editor por defecto
          o configurar (g)vim para que se comporte como en el servidor de
            desarrollo
  30. configurar urxvt
          o hacer ilimitado el buffer de urxvt
          o cambiar cursor de subguión a block
  31. login manager (slim)
          o se ha de mantener presionada la combianción de teclas para que
            tenga efecto (quiero que sea immediato)
          o sale entre los 2 monitores
          o cambiar diseño
          o precargar aplicaciones
          o extraños gráficos al hacer lock en pantalla auxiliar
  32. no puedo eliminar ficheros de /usr/share/wallpapers desde file manager
      (Thunar). he de lanzarlo como root?
  33. crear $HOME/.config y guardar $HOME/gtk-3.0 en ella (generada por
      LXAppearance)
  34. scripts al inicio
          o rankmirrors mirrorlist
          o packer -Syu
          o random wallpapers
  35. multimedia
          o imagemagick
          o edición de foto que permita desenfocar (para hacer manuales)
          o gxine / mplayer
          o server-client straming (xiph.org)
          o ogg123
          o mpd + mpc + ncmpcpp
  36. transferencia bluetooth
  37. automount
  38. altavoces bluetooth
  39. rdesktop (con seemless)
  40. cliente ftp
  41. edición pdf (xournal)
  42. todo lists (todo.txt)
  43. xnots
  44. cliente de fax
  45. no se muestran los archivos de escritorio en el escritorio
  46. alsamixer muestra una niebla en todo el interfaz
  47. se usa zathura como visor de pdfs
          o buscar información sobre zathura (es una buena elección?)
          o buscar manual de usuario (parece que usa keybindings e interfaz
            basados en vim)
          o buscar un visor mejor, si lo hay
          o añadir al menú de aplicaciones
  48. instalar nodejs
  49. deshabilitar speaker
  50. fecha y hora en historial de bash
  51. pasos finales
         1. limpiar paquetes no usados
         2. basarse en archlinux
         3. máqina virtual con simulación de red cableada (qemu / openvm)
         4. generar iso
**** done ****
*** cambiar teclado grafico ***
$ echo "setxkbmap es &" >> /home/pau/.config/openbox/autostart
    * como ponerlo generico en lugar de particular del usuario?
    * como hacer para que salgan las eñes?
          o no salen en
                # en urxvt
          o sí salen en
                # firefox
                # leafpad (text editor)
*** firefox ***
comando: firefox-nightly
    * config
          o salvar pestañas
          o google como home
    * view
          o ocultar toolbar menu
          o ocultar toolbar bookmark
    * addons
          o tab utilities
                # la extensión new tab homepage no se encuentra disponible
                  para mi versión de firefox
                # configurarlo para que actue como new tab homepage [config >
                  tabs > tab utilities options...]
    * xpi (desde sitio web)
          o pentadactyl (latest)
          o firebug (latest)
    * eliminar marcadores por defecto
          o bookmarks toolbar
          o bookmarks menu
    * sync
          o requiere tener el código de activación, así que lo debo
            recuperar desde el portátil y enviármelo por correo
          o ya tengo el correo en pau.fraces@gmail.com (buscar "firefox sync")
          o método: merge
          o ha separado los que tenía en local con los que vienen del servidor
            con una barra horizontal
    * actualizar desde packer y evitar avisos de actualización
          o http://bbs.archbang.org/viewtopic.php?pid=5397#p5397 "per AUR, the
            last (Arch) update to this came on September 29th so as far as
            pacman is concerned you're up to date. This doesn't help you when
            you have FF telling you to update :-)"
"I'd love to hear what others think but IMO you have a couple of options""1)
disable the check that goes out (edit > preferences > advanced > update) and
wait for a pacman update""2) uninstall the pacman version, install your own and
treat FF like it's own rolling release""I think the reason the update fails
outside of pacman is that it's installed as root but launched as a user so your
permissions are stopping it from updating. I guess a third option would be to
launch it as root and let it update that way"
Empiezo por la opción 1 aunque creo que será mejor usar la opción 2:
    * uninstall the pacman version, install your own and treat FF like it's own
      rolling release
    * pentadactyl
          o documentar comandos
                # http://dactyl.sourceforge.net/help/pentadactyl/index.xhtml
                # http://dactyl.sourceforge.net/help/pentadactyl/buffer.xhtml
                # http://dactyl.sourceforge.net/help/pentadactyl/insert.xhtml
                # http://dactyl.sourceforge.net/help/pentadactyl/marks.xhtml
                # http://dactyl.sourceforge.net/help/pentadactyl/gui.xhtml
          o cómo guardar en favoritos seleccionando carpeta?
                # :dia addbookmark
                # :dia ad[tab]
          o cómo administrar los motores de búsqueda?
                # :dia searchengines
                # :dia se[tab]
                      # añadir keyword para acceder rápidamente desde los
                        desplegables de pentadactyl
                # http://mycroft.mozdev.org/search-engines.html (servicio web
                  para añadir search engines)
          o error al hacer :tabattack
===al actualizar a la última versión de nightly no funcionan algunas
extensiones (pentadactyl, tabutilities)=====
    * https://wiki.archlinux.org/index.php/Downgrading_Packages
"You may be able to downgrade the package trivially by visiting /var/cache/
pacman/pkg on your system and seeing if the older version of the package is
stored there. (If you have not run pacman -Scc recently, it should be there).
If the package is there, you can install that version using pacman -U /var/
cache/pacman/pkg/pkgname-olderpkgver.pkg.tar.gz"
De lo que deduzco:
    * limpiar la cache de pacman
$ pacman -Scc
    * instalar un pkgbuild
$ pacman -U package.tar.gz
    * no encuentro el paquete de firefox en /var/cache/pacman/pkg
          o no se guardan en la cache los paquetes de aur?
    * cambiar a firefox del repositorio extra y comprobar si funciona el :
      tabattack
          o como las versiones de extra son estables, llevan más tiempo
            disponibles por lo que seguramente habrán actualizaciones
            disponibles de las extensiones
$ pacman -Ss firefox
> local/firefox-nightly 11.0a1-1 [32,03 MB]
>     Standalone web browser from mozilla.org, nightly build
$ sudo pacman -Rscn firefox-nightly
> Se quitará (2): firefox-nightly-11.0a1-1 [32,03 MB]  mime-types-8-1 [0,05
MB]
$ sudo pacman -S firefox
> Objetivos (3): hunspell-1.3.2-1 [0,18 MB]  mime-types-8-1 [0,01 MB]
>                firefox-8.0-1 [11,72 MB]
>
> Dependencias opcionales para hunspell
>     perl: for ispellaff2myspell
    * funcionan las extensiones
    * sigue sin funcionar :tabattack
He tenido que cambiar el lanzador super+w desde obkey para que lanzara firefox
en lugar de firefox-nightly.
    * el menú de la wiki aparece correctamente
          o al actualizar a ff9 vuelve a aparecer al final de la página
          o http://www.mail-archive.com/debian-bugs-dist@lists.debian.org/
            msg970652.html
          o al actualizar a ff10 vuelve a aparecer correctamente y funciona :
            tabattack
===crear carpeta $HOME/downloads y hacer que firefox apunte alli=====
$ mkdir $HOME/downloads
    * Firefox > Menu > Preferences > General > save files to
          o estaba apuntando a $HOME/Downloads
          o supongo que al no existir la carpeta, preguntaba dónde guardar los
            ficheros cada vez
          o se ha creado la carpeta pero en minúsculas
          o se ha hecho que esa propiedad apunte a /home/pau/downloads
*** copy/paste en rxvt ***
    * de urxvt a otras aplicaciones?
         1. select text to copy
         2. middle mouse button (wheel en mouse; left+right en touchpad) to
            paste
    * de otras aplicaciones a urxvt?
         1. ^c to copy
         2. shift+insert to paste
*** configurar locales ***
    * https://wiki.archlinux.org/index.php/Locale
    * "To enable a locale, uncomment the name of the locale in the file /etc/
      locale.gen"
$ sudo cp /etc/locale.gen /etc/locale.gen.original
$ sudo sed -i 's/#es_ES.UTF-8 UTF-8/es_ES.UTF-8 UTF-8/' /etc/locale.gen
$ sudo locale-gen
> Generating locales...
>   en_US.UTF-8... done
>   es_ES.UTF-8... done
> Generation complete.
    * "To define the system-wide locale used on the system, add the specified
      locale to the /etc/rc.conf file"
    * "The system wide locale will be updated after rebooting the system."
*** rankmirrors mirrorlist ***
$ sudo mv /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.original
$ sudo rankmirrors -n 5 /etc/pacman.d/mirrorlist.original | sed -nr '/^[^#]/p'
> ~/mirrorlist
$ sudo mv ~/mirrorlist /etc/pacman.d/mirrorlist
Para ver el progreso podemos abrir otro terminal y monitorear el mirrorlist de
la carpeta de usuario
$ tail -F ~/mirrorlist
*** actualizar (packer) ***
$ sudo packer -Syu
    * cómo hacer para que no pregunte?
$ man packer
> --noconfirm
>     Perform commands without confirmation from the user.
Actualización automatizada
$ sudo packer -Syu --noconfirm
    * cómo hacer para registrar errores?
*** instalar vim ***
$ packer -S --noconfirm vim
*** sudo no pide password ***
    * https://wiki.archlinux.org/index.php/Sudo
    * http://administratosphere.wordpress.com/2007/07/19/the-wheel-group/
$ sudo -l
> User pau may run the following commands on this host:
>     (ALL) NOPASSWD: ALL
$ sudo grep -Rn "NOPASSWD" /etc
> /etc/sudoers.d/g_wheel:1:%wheel  ALL=(ALL) NOPASSWD: ALL
> /etc/sudoers:78:# %wheel ALL=(ALL) NOPASSWD: ALL
$ sudo cat /etc/sudoers.d/g_wheel
> %wheel  ALL=(ALL) NOPASSWD: ALL
$ groups
> lp wheel log network video audio optical storage power users
    * debería eliminar la carpeta /etc/sudoers.d/ y configurar todo desde /
      etc/sudoers ?
    * esta configuración viene por defecto con archbang?
*** papelera ***
    * http://pages.stern.nyu.edu/~marriaga/software/libtrash/
    * http://www.vicente-navarro.com/blog/2008/01/24/la-libtrash-la-papelera-
      de-la-linea-de-comandos/
    * http://islaserver.com/articulos/sistemas/borrado-seguro-con-libtrash.html
    * http://stillstup.blogspot.com/2008/09/where-did-all-my-disk-space-go-
      hidden.html
*** configurar impresoras ***
    * usados
          o http://www.taringa.net/posts/linux/7974523/Imprimir-a-PDF-en-
            ArchLinux.html
    * información adicional
          o https://wiki.archlinux.org/index.php/CUPS
[Taringa PDF]
'"Para imprimir a PDF necesitas instalar cups-pdf que lo sirve para crear una
impresora virtual"'
# pacman -S cups-pdf
$ packer cups-pdf
> Objetivos (4): openslp-1.2.1-3 [0,26 MB]  cups-1.5.0-1 [2,07 MB]
>                ghostscript-9.04-5 [10,41 MB]  cups-pdf-2.6.1-1 [0,02 MB]
>
> Dependencias opcionales para cups
>     php: for included phpcups.so module
>     ghostscript: for non-PostScript printers to print with CUPS to convert
>     PostScript to raster images
>     foomatic-db: drivers use Ghostscript to convert PostScript to a printable
>     form directly
>     foomatic-db-engine: drivers use Ghostscript to convert PostScript to a
>     printable form directly
>     foomatic-db-nonfree: drivers use Ghostscript to convert PostScript to a
>     printable form directly
>     xdg-utils: xdg .desktop file support
>
> Dependencias opcionales para ghostscript
>     texlive-core: needed for dvipdf
>     gtk2: needed for gsx
>
> To use cups-pdf, restart cups and visit the cups
> web interface at http://localhost:631/''
>
> You can now add a "Virtual Printer (PDF Printer)"
> and use the Postscript/Generic postscript color
> printer driver.
>
> Note that cups-pdf has a configuration
> file in /etc/cups. The default location for
> pdf output is /var/spool/cups-pdf/$username.
"Ahora hay que iniciar cups para crear la impresora"
# /etc/rc.d/cups start
"Y agregarlo a los DAEMONS en /etc/rc.conf"
DAEMONS=(... cups ...)
"Con cups instalado e iniciado pasamos a la configuración de la impresora. En
un navegador web ir a
'">http://localhost:631"''
"Administracion > Añadir impresora""Te va a pedir el usuario y contraseña de
root""Seleccionas CUPS-PDF (Virtual PDF Printer)""Ahora podes ponerle nombre y
descripción que quieras"
    * Nombre: pdf
    * Descripción: Virtual PDF Printer
    * Ubicación: localhost
    * Conexión: cups-pdf:/
"Ahora en marca seleccionar Generic""En modelo Generic CUPS-PDF Printer
(en)""Ahora clic en Cambiar opciones predeterminadas y listo ya tenes la
impresora a PDF"
    * Page Size: A4
Ahora creo un enlace simbólico para tener la carpeta de pdfs impresos en el
home
$ ln -s /var/spool/cups-pdf/pau $HOME/pdf-printer
    * thunar abre los documentos pdf con firefox
    * instalar un visor de pdfs (o únicamente xournal)
    * como se cambian las aplicaciones por defecto en thunar?
    * documentar cómo se añade la oki es4140
    * añadir la impresora de isa
Al ir a imprimir después de reiniciar, no aparecen las impresoras gestionadas
por cups
$ /etc/rc.d/cupsd status
> [STOPPED]
    * como el cups lo hemos puesto que arranque en background (con la @) no ha
      mostrado error en el arranque
          o dónde se guardan los logs de arranque de demonios?
Supongo que puede ser debido a que el demonio se llama cupsd y en el rc.conf
consta cups, así que lo cambio y pruebo
    * al reiniciar no ha pasado de las opciones de la bios
          o error del grub?
          o guarda grub algún log de errores?
Despues de reiniciar (con cupsd en el rc.conf)...
$ /etc/rc.d/cupsd status
> [STARTED]
    * compruebo que aparezcan las impresoras desde firefox y en efecto aparecen
      y funcionan correctamente
*** usar terminus como fuente de consola gráfica ***
    * https://bbs.archlinux.org/viewtopic.php?id=51539
    * "The relevant parts of my .Xdefaults are follows. You don't need the
      entire font line thingie."
urxvt*font: xft:Terminus
urxvt*boldFont: xft:Terminus
    * "Terminus is terminus-font in community."
Así que ...
$ sudo packer -S --noconfirm terminus-font
> Updating font cache... done.
> Note: terminus-font is in /usr/share/fonts/local/

$ cp ~/.Xdefaults ~/.Xdefaults.original
$ sed -i 's/xft:DejaVu Sans Mono-10/xft:Terminus/' ~/.Xdefaults
*** instalar ssh ***
    * https://wiki.archlinux.org/index.php/Secure_Shell
$ packer -S openssh
> Optional dependencies for openssh
>     x11-ssh-askpass: input passphrase in X without a terminal
$ sudo cp /etc/ssh/ssh_config /etc/ssh/ssh_config.original
$ sudo sed -i 's/#   Protocol 2,1/Protocol 2/' /etc/ssh/ssh_config
$ sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.original
$ sudo sed -i 's/#PermitRootLogin yes/PermitRootLogin no/' /etc/ssh/sshd_config
    * seguridad adicional https://wiki.archlinux.org/index.php/Using_SSH_Keys
    * arrancar al inicio
add sshd to the "DAEMONS" section of your /etc/rc.conf
Aunque lo he añadido con '@' para que arranque en background
    * arranque manual
$ rc.d {start|stop|restart} sshd
    * conectar a servidor ssh
$ ssh -p port user@server-address
    * conectando a la .0.3 por primera vez
$ ssh 192.168.0.3
> The authenticity of host '192.168.0.3 (192.168.0.3)' can't be established.
> RSA key fingerprint is 60:2d:3a:63:c8:ad:7c:5f:b2:14:65:6a:b3:a9:d9:84.
> Are you sure you want to continue connecting (yes/no)?
  yes
> Warning: Permanently added '192.168.0.3' (RSA) to the list of known hosts.
> Connection closed by 192.168.0.3
    * una vez que tenenos el fingerprint en el cliente ya podemos conectar con
      el usuario que queramos
$ ssh reset@192.168.0.3
*** ip fija ***
    * right-click sobre networkmanager
    * IPv4 Settings
    * Method: Manual
    * Addresses > Add
          o Address: 192.168.0.26
          o Netmask: 255.255.255.0
          o Gateway: 192.168.0.8
    * DNS servers: 208.67.222.222, 208.67.220.220
    * documentar método por ficheros de configuración en lugar de aplicación
      gráfica
*** aparecer como ansi ***
Después de haber configurado la conexión manualmente definiendo la .0.26 como
mi ip y las DNSs de opnDNS sigo apareciendo como scoansi.
Esto es debido a que la variable $REMOTEHOST aparece en blanco al conectar por
ssh
    * http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=64222
    * http://www.netexpertise.eu/en/ssh/environment-variables-and-ssh.html
    * http://www.thinkplexx.com/learn/howto/security/ssh/setting-ssh-remote-
      host-environment-variables-interactive-shell
Después de leer el primero de los enlaces opto por hacer un poco de
scripting...
script: /usr/script/i4remotehost
#!/bin/bash

remote_host=$REMOTEHOST

if test "$remote_host" == ""
then
    remote_ip=$(echo $SSH_CLIENT | awk '{print $1}')
    remote_host=$(sed -nr "/$remote_ip/p" /etc/hosts | awk '{print $2}')
fi

echo $remote_host
Luego en el /etc/bash.bashrc.local llamamos al script
export REMOTEHOST=$(i4remotehost)
Y listo! Los que entran por telnet mantienen la variable como la tenian y los
que entren por ssh setearán la variable correctamente
Al hacerlo en el /etc/bash.bahrc.local en lugar de en el $HOME/.profile lo
definimos en un único lugar del sistema, en vez de en cada usuario
*** configurar teclas de función ***
Antes de haber configurado la ip...Las teclas de función están bien
configuradas para ansi, pero en el servidor aparezco como scoansi. Supongo que
al hacer que mi ip vuelva a ser la .0.26 ya funcionarán sin tener que hacer
export TERM=ansi
    * sólo funcionan las [Fx > F5] pero siguen sin funcionar las [F1 - F5]
    * estoy enviando códigos diferentes a los que envio desde el portátil?
    * acaso desde el portátil tampoco van?
    * El termcap modificado redefine el comportamiento de xterm no de ansi
    * cómo hacer para que no afecte a Raúl?
    * hay algún afectado más si se redefine ansi?
    * de momento para poder ir trabajando y no afectar a nadie, voy a poner en
      los .profiles que el $REMOTEHOST Pau use el $TERM xterm
    * con $TERM=xterm tampoco funciona
    * supongo que el arch de casa envia otros keybindings, así que crearé una
      entrada nueva en el termcap para urxvt con los keybindings requeridos y
      modificaré los .profiles para aparecer como urxvt
    * nota: al ir a modificar veo que los valores que necesito, son los que
      aparecían en el termcap original (antes de hacer las modificaciones para
      el portátil) en la entrada xterm
    * termcap/$TERM urxvt no funciona correctamente: vim tira un error diciendo
      que no tiene la capacidad cm
    * puebo con termcap/$TERM rxvt y arreglado!
    * modificados los .profile de:
          o reset
          o resdis
          o global
          o rescon
case "$REMOTEHOST" in
"Raul")
    export TERM=ansi
    ;;
"Pau")
    i4term.rxvt && exit
    ;;
*)
    export TERM=scoansi
    ;;
esac
/usr/script/i4term.rxvt
#!/bin/bash

SCRIPT_PATH=/usr/script

TERM=rxvt luit -g2 "CP 437"
/usr/script/i4term.xterm
#!/bin/bash

SCRIPT_PATH=/usr/script

TERM=xterm luit -g2 "CP 437"
    * encontrar una solución más correcta
    * hay documentación de las modificaciones hechas en el termcap?
    * buscar las referencias usadas cuando hice la modificación de xterm
    * hay un fichero con los códigos enviados por los terminales afectados: /
      usr/resdis/desarrollo/programa/keybindings.txt
    * completar ese documento con los keybindings del portátil
    * poner el documento en una ubicación mas genérica
    * copiar el contenido del documento en este artículo de la wiki
    * copiar el contenido del termcap en este artículo de la wiki, con las
      entradas usadas:
          o scoansi
          o ansi (raúl)
          o xterm (pau portátil)
          o rxvt (pau reset)
*** configurar semigráficos ***
    * Después de configurar los locales y reiniciar podemos obtener los
      semigráficos haciendo desde el servidor (.0.3):
$ luit -g2 "CP 437"
    * comprobar que sea un tema de locales
    * automatizar para que se lanze el comando desde .profile, únicamente
      cuando yo entre
    * ya que luit se ha de ejecutar en cada servidor talvez se puede probar
      konwert desde el cliente
*** cambiar el theme de openbox por un mas claridad ***
    * openbox right-click menu > User Interface Settings (LXAppearance)
          o controles
                # se cambia Turquoise Nights II
                # por Taqua
          o Tema de iconos
                # se cambia clarity
                # por GNOME
                # a que afecta esto?
    * el texto seleccionado aparece con un fondo con muy poco contraste
          o se cambia Taqua por Simple-Red
    * openbox right-click menu > openbox config > GUI config tool (ObConf)
          o tema
                # se cambia Turquoise Nights Ob
                # por Mars
                # comprobar que éstos themes vienen con el paquete openbox-
                  themes
          o Márgenes
                # se cambian los 4 a 0px
    * openbox right-click menu > tint2 config > edit tint2rc
          o sección: CLOCK, variable: time1_format
                # se cambia %a %b %d, %r
                # por %a %b %d, %H:%M
    * por estas modificaciones o por actualizar o por otra causa de la que no
      soy consciente aparecen dos iconos de red en el tray
          o https://bbs.archlinux.org/viewtopic.php?id=123642
                # leyendo el artículo pruebo a comentar la linea del nm-applet
                  de autostart y listo!
                # desde dónde se carga el applet?
    * Hacer que el color del theme Mars de ObConf coincida con el de Simple-Red
      de LXAppearence
sudo sed -i 's/b0381e/990000/g' /usr/share/themes/Mars/openbox-3/themerc
    * En /usr/share/themes se encuentran varios temas instalados por defecto.
          o Se pueden desinstalar mediante pacman?
          o qué paquete los instala?
    * Hacer que el color de la status bar coincida con el de Simple-Red de
      LXAppearence (#990000)
sed --in-place 's/b0381e/990000/gi' $HOME/.config/tint2/tint2rc
    * También lo he cambiado en .conkyrc
    * Porqué los ficheros de configuración se llaman
      foo
      rc
 ?
    * http://www.linuxquestions.org/questions/linux-newbie-8/what-does-rc-
      stand-for-31758/
*** bordes en las ventanas ***
    * Hecho al cambiar de tema mediante ObConf
*** status bar ***
===tray=====
==hora en formato 24h======
    * Hecho al cambiar el tint2rc, sección: CLOCK, variable: time1_format
==color picker======
    *     o recuerdo tener algun post sobre este tipo de programas en
            favoritos, así que me voy a "administrar marcadores" y busco
            "color picker"
                # https://bbs.archlinux.org/viewtopic.php?id=106205
                # http://www.reddit.com/r/linux/comments/chxdo/
                  elicit_a_nice_gtk_color_picker_with_nifty/?sort=top
Leyendo los artículos me decanto por gpick
    * http://code.google.com/p/gpick/
$ packer -Ss gpick
> aur/gpick-svn 140-1
>     An advanced color picker
> aur/gpick 0.2.3-1
>     Advanced color picker written in C++ using GTK+ toolkit
$ packer -S gpick
> warning: gpick is flagged out of date
    * porqué packer no requiere sudo?
$ packer -S gpick-svn
Para ejecutarlo
$ gpick
Para que aparezca en el system tray
    * gpick > edit > preferences
          o main
                # system
                      # single instance
                # system tray
                      # minimize to system tray
                      # close to system tray
                      # start in system tray
Para que al soltar el click se copie el color seleccionado en el clipboard
    * gpick > edit > preferences
          o picker
                # floating picker click behaviour
                      # copy to clipboard
Para que arranque al inicio
    * se debe añadir al autostart
Con esta configuración
    * siempre tendremos el icono del gpick en el tray
    * left-click
          o mientras lo mantenemos pulsado aparece una ventana con un zoom de
            donde está el ratón y el valor del color sobre el que está
          o al soltar guarda el valor en el clipboard
    * right click
          o podemos abrir la ventana principal, que contiene más información
            y desde donde podemos configurarlo
==checkgmail======
$ packer -Ss gmail
> aur/checkgmail-svn 47-1
>     An alternative Gmail Notifier for Linux and other *nix systems
$ packer -S checkgmail-svn
> Dependencias opcionales para checkgmail-svn
>     perl-crypt-simple
>     perl-gtk2-sexy
>     perl-crypt-blowfish
>     perl-freezethaw
>     perl-digest-md5
>     perl-mime-types
>     perl-compress-zlib
Luego al ejecutar checkgmail se abre un cuadro de preferencias
    * username: pau.fraces@gmail.com
    * password:
    * save password (as plain text):
    * language: español
    * command to execute on clicking the tray icon (use %u to represent the
      gmail web address): firefox %u
    * check inbox for mail every: 120 secs
    * feed address: mail.google.com/mail/feed/atom
    * use custom mail icon:
    * use custom no mail icon:
    * use custom error icon:
    * show new mail popup for: 6 secs
Mientras el cuadro se abre, aparece lo siguiente en la consola
$ checkgmail
> sh: ifconfig: no se encontró la orden
> Possible unintended interpolation of @2 in string at (eval 32) line 1.
> Warning: Crypt::Simple not found ...
> Warning: Crypt::Blowfish not found ...
> Warning: FreezeThaw not found ...
>
> CheckGmail requires the above packages for password encryption
> Please download and install from CPAN (http://search.cpan.org) if you want to
use this feature ...
>
> Warning: Gtk2::Sexy not found ...
>
> CheckGmail uses Gtk2::Sexy for clickable URLs in mail messages
> Please download and install from CPAN (http://search.cpan.org) if you want to
use this feature ...
El icono aparece cortado (como si cada icono tuviese un tamaño máximo
asignado y el icono de checkgmail lo superase)
El icono que aparece es el de error. Al posicionarnos encima aparece un tooltip
que dice:
"Error: 501 Protocol scheme 'https' is not supported (LWP::Protocol::https not
installed)"
    * acabar de instalar / configurar para que funcione
    * es posible guardar la contraseña con algo de encriptación o con
      permisos especiales que bloqueen la lectura?
          o dónde se guarda esta contraseña?
    * lanzarlo al inicio
$ packer -S checkgmail
> :: checkgmail y checkgmail-svn están en conflicto. ¿Quitar checkgmail-svn?
s
> Objetivos (9): checkgmail-svn-47-1 [removal]  perl-crypt-blowfish-2.12-4
>                perl-crypt-simple-0.06-5  perl-freezethaw-0.5001-2
>                perl-io-socket-ssl-1.54-1  perl-lwp-protocol-https-6.03-1
>                perl-mozilla-ca-20120118-1  perl-net-ssleay-1.42-2
>                checkgmail-1.13-7
> ¿Continuar con la instalación? s
> Dependencias opcionales para checkgmail
>     perl-gtk2-sexy
$ checkgmail
> sh: ifconfig: no se encontró la orden
> Possible unintended interpolation of @2 in string at (eval 42) line 1.
> Warning: Gtk2::Sexy not found ...

> CheckGmail uses Gtk2::Sexy for clickable URLs in mail messages
> Please download and install from CPAN (http://search.cpan.org) if you want to
use this feature ...
$ packer -S perl-gtk2-sexy
    * después de configurar la contraseña se conecta correctamente a gmail
    * se añade el comando en el autostart para que arranque al inicio
===cambiar colores a unos que se integren mejor con el tema de ObConf=====
    * requiere instalar algun color picker
          o se ha elegido gpick
    * documentar modificaciones en tint2rc
    * las modificaciones generan pérdida de pixels en los iconos del tray
===menu inicio desde icono=====
;gpick
      color picker
;thunar
      file manager
;geeqie
      visor de imágenes
;scrot
      capturas de pantalla
*** conky coherente con openbox theme ***
    * documentar modificaciones en .conkyrc
*** wallpapers ***
    * https://wiki.archlinux.org/index.php/Nitrogen
    * http://deviantdark.deviantart.com/art/GNU-Linux-Distros-Wallpapers-
      80233488
Ubicados en /usr/share/wallpapers
    * Ha desaparecido al configurar el dualhead
    * Lo he reconfigurado con nitrogen
    * Cómo se configura con jutsus secretos (linea de comandos / ficheros de
      configuración) ?
*** combinación de teclas ***
    * centralizar todas las que se puedan
    * documentar obkey
    * eliminar Alt+F2 Run dialog
    * cambiar Alt+F3 Dmenu por Alt+p
    * mantener conky actualizado
*** cambiar de escritorio ***
    * Comportamiento por defecto: Al hacer mouse-scroll sobre el escritorio, se
      cambia de escritorio
    * cómo se hace con combinación de teclas?
          o con ctrl+alt+der> nos podemos desplazar al escritorio de la
            izquierda o derecha
          o cómo se hace para ir a uno en concreto?
                # con ctrl + [F1 - F4] nos movemos a los escritorios [1 - 4]
*** instalar htop ***
$ packer -Ss htop
> extra/htop 0.9-3 [0,05 MB]
>     Interactive process viewer
> aur/htop-svn 133-1
>     Svn-version of the popular system monitor
> aur/htop-vi 0.9-1
>     Interactive process viewer patched for vi style scroll keys
$ packer -S htop-svn
> ==> ERROR: Se produjo un error en build()
$ sudo packer -S htop-svn
> ==> ERROR: Se produjo un error en build()
$ packer -Rscn htop-svn
> packer: Option `-Rscn' is not valid
    * cómo se desinstalan paquetes totalmente mediante packer?
$ packer -S htop
*** resolución pantalla ***
    * usados
          o http://en.wikipedia.org/wiki/Color_depth
          o http://www.aocmonitorap.com/hongkong_eng/monitor_231.php
          o http://nouveau.freedesktop.org/wiki/CodeNames
          o http://nouveau.freedesktop.org/wiki/FeatureMatrix
          o http://bbs.archbang.org/viewtopic.php?id=14
          o http://wiki.archbang.org/index.php?title=Xorg_Desperate_Mode_Guide
          o https://wiki.archlinux.org/index.php/Nouveau
          o https://wiki.archlinux.org/index.php/Xorg
          o http://nouveau.freedesktop.org/wiki/TroubleShooting
          o https://wiki.archlinux.org/index.php/Mkinitcpio
    * información adicional
          o http://nouveau.freedesktop.org/wiki/InstallNouveau
          o http://nouveau.freedesktop.org/wiki/Randr12
          o http://bbs.archbang.org/viewtopic.php?id=1384
Identificar la gráfica
$ lspci | grep VGA
> 01:00.0 VGA compatible controller: nVidia Corporation GT218 [GeForce 210]
(rev a2)
Según la página de codenames ésta gráfica pertenece a la NV50 family:
    * NVA8 (GT218)
          o GeForce 8400 GS (rare)
          o GeForce 205, 210, G 210(M), 305M, 310(M)
          o Quadro FX (380 LP, 380M), NVS (300, 2100M, 3100M)
En la página de features aparece como hecha la funcionalidad de dual head
mediante RAndR 1.2
[Color depth]
    * 24-bit = 16 million color
[AOC]
    * Recommended Resolution: 1920×1080@60Hz
    * Display Colours: 16.7M
===Primer intento (fallido)=====[Desperate mode guide]
    * "Remove all shipped video drivers w/ AB"
$ sudo pacman -Rscn xf86-video-apm xf86-video-ark xf86-video-ast \
  xf86-video-ati xf86-video-chips xf86-video-cirrus \
  xf86-video-dummy xf86-video-fbdev xf86-video-glint \
  xf86-video-i128 xf86-video-i740 xf86-video-intel \
  xf86-video-mach64 xf86-video-mga xf86-video-neomagic \
  xf86-video-nv xf86-video-r128 xf86-video-rendition\
  xf86-video-s3 xf86-video-s3virge xf86-video-savage \
  xf86-video-siliconmotion xf86-video-sis xf86-video-sisusb \
  xf86-video-tdfx xf86-video-trident xf86-video-tseng \
  xf86-video-v4l xf86-video-vesa xf86-video-vmware \
  xf86-video-voodoo xf86-video-xgi xf86-video-xgixp \
  ati-dri intel-dri mach64-dri mga-dri r128-dri \
  savage-dri sis-dri tdfx-dri xf86-video-geode
    * "install your appropriate video driver"
$ sudo pacman -S xf86-video-nouveau
>   ==> make sure you use KernelModeSetting (KMS)
>   ==> see http://wiki.archlinux.org/index.php/Nouveau#KMS for more
> Dependencias opcionales para xf86-video-nouveau
>     nouveau-dri:    experimental gallium3d features
    * Antes de configurar hago backup de la configuración original
$ sudo cp -R /etc/X11/xorg.conf.d/ /etc/X11/xorg.conf.d.original/
    * Dejo que xorg haga su configuración automática (a ver que pasa)
$ sudo Xorg -configure
> Fatal server error:
> Server is already active for display 0
===Segundo intento (fallido)=====
    * Vale, pues tendré que hacerlo como dicen en la desperate guide (aunque
      saltándome los pasos que ya he hecho)
   1. Go in another tty (for example tty2) Ctrl + Alt + F2
   2. login as root
   3. ejecutar los siguientes comandos (y rezar)
$ init 3
$ Xorg -configure
$ cp /root/xorg.conf.new /etc/X11/xorg.conf
$ su - pau
$ startx
    * El problema de la pantalla a 80% sólo pasa con la pantalla pinchada por
      dvi
    * La pantalla pinchada por vga muestra el 100% (aunque con una resolución
      de pena)
===Tercer intento (fallido)=====
$ su
    * Hacemos un poco de limpieza (con posibilidad de liarla todavía más
      parda)
$ rm /root/xorg.conf.new
$ rm /etc/X11/xorg.conf
$ cd /etc/X11/xorg.conf.d
$ rm 10-synaptics.conf 20-gpudriver.conf 50-vmmouse.conf 50-joystick.conf
$ pacman -Rscn xf86-input-synaptics xf86-input-vmmouse xf86-input-acecad xf86-
input-aiptek xf86-input-joystick
    * xf86-input-synaptics es necesario para usar el touchpad del laptop
    * xf86-input-joystick es necesario para usar el joystick
    * para que sirve xf86-input-evdev y xf86-input-void?
          o xf86-input-evdev se explica en [ArchWiki Xorg]
[ArchWiki Nouveau]
    * "let Xorg to load nouveau instead of nvidia by creating the file /etc/
      X11/xorg.conf.d/20-nouveau.conf, and input the following content"
Section "Device"
  Identifier "Nvidia card"
  Driver "nouveau"
EndSection
"Kernel Mode-Setting (KMS) is required by the Nouveau driver. As the system
boots, the resolution will likely change when KMS initializes the display
driver. Simply installing the Nouveau driver should be enough to get the system
to recognize and initialize it in "Late Start" mode""Users may prefer the early
start method as it does not cause the annoying resolution change part way
through the boot process""With late start KMS will be enabled when other kernel
modules are loaded. You will see the text "Loading modules" and the size of the
text may change, possibly with an undesirable flicker""Using other framebuffer
drivers (such as uvesafb) will conflict with KMS. If this is the case, remove
all "vga=" options from your kernel commandline in /boot/grub/menu.lst""Early
start will start KMS as early as possible in the boot process, when the
initramfs is loaded. Here is how to do this with the official packages"
1. Add "nouveau" to the MODULES array in /etc/mkinitcpio.conf
MODULES="... nouveau ..."
2. Re-generate boot image
$ mkinitcpio -p
 e.g. linux>
"Always make sure you won't have nomodeset in GRUB's menu.lst/menu.cfg kernel
line, since Nouveau needs kernel mode-setting in order to run successfully""If
experiencing troubles with nouveau leading to rebuild nouveau-drm several times
for testing purposes, do not add nouveau to the initramfs. It is too easy to
forget to rebuild the initramfs and it will just make any testing harder. Just
use late start until you are confident the system is stable. There might be
additional problems with initramfs if you need a firmware for the nv50 family"
==salvaculos======
$ pacman -S xf86-video-vesa
$ Xorg -configure
$ cp /root/xorg.conf.new /etc/X11/xorg.conf
$ reboot
==limpiar el salvaculos======
$ pacman -Rscn xf86-video-vesa
$ rm /root/xorg.conf.new /etc/X11/xorg.conf
    * probar si son necesarios todos los pasos del salvaculos
    * mover los .original (como /etc/X11/xorg.conf.d.original) a un directorio
      /home/pau/original/ poniendo el árbol completo bajo él para saber
      dónde restaurar
===Cuarto intento (conseguido!!)=====
    * analizar detenidamente la documentación de archforums sobre Xorg y los
      enlaces que en ella se encuentran ya que contienen mucha información
      valiosa
[ArchWiki Xorg]
This step is OPTIONAL and should not be done unless you know what you are doing
This step is NOT OPTIONAL if using dual monitors or the nouveau driver
"First, create a new config file, such as /etc/X11/xorg.conf.d/10-
monitor.conf""Insert the following code into the config file mentioned above"
Section "Monitor"
    Identifier    "Monitor0"
EndSection

Section "Device"
    Identifier    "Device0"
    Driver        "vesa" #Choose the driver used for this monitor
EndSection

Section "Screen"
    Identifier    "Screen0"  #Collapse Monitor and Device section to Screen
section
    Device        "Device0"
    Monitor       "Monitor0"
    DefaultDepth  16 #Choose the depth (16||24)
    SubSection "Display"
        Depth     16
        Modes     "1024x768_75.00" #Choose the resolution
    EndSubSection
EndSection
Según las especificaciones del monitor, el snippet anterior y el snippet de
nouveau; elimino /etc/X11/xorg.conf.d/20-nouveau.conf y creo /etc/X11/
xorg.conf.d/20-monitor.conf con el siguiente snippet
Section "Monitor"
    Identifier    "Monitor0"
EndSection

Section "Device"
    Identifier    "Nvidia card"
    Driver        "nouveau"
EndSection

Section "Screen"
    Identifier    "Screen0"
    Device        "Nvidia card"
    Monitor       "Monitor0"
    DefaultDepth  24
    SubSection "Display"
        Depth     24
        Modes     "1920x1080_65.00"
    EndSubSection
EndSection
    * reinicio y vuelve a fallar, así que me muevo al tty2
$ sed -n '/] (EE)/p' /var/log/Xorg.0.log | sed 's/^\^*\] //' | tail
> (EE) [drm] failed to open device
> (EE) No devices detected
[Nouveau TrobleShooting]
1. Xorg fails to start with "(EE) [drm] failed to open device"
"Your DDX does not work with your current kernel and/or libdrm. There are at
least three possible reasons for this: the nouveau DRM kernel module is not
loaded, a version mismatch between the Nouveau DRM and libdrm, or KMS being
disabled""First check, that lsmod command lists nouveau. If not, do modprobe
nouveau to load the nouveau DRM kernel module, and check the kernel log for
possible errors"
$ lsmod | sed -n '/nouveau/p'
> nouveau               651392  2
$ sudo modprobe nouveau
> WARNING: All config files need .conf: /etc/modprobe.d/modprobe.conf.pacnew,
it
> will be ignored in a future release
Comparando modprobe.conf con modprobe.conf.pacnew veo que el bueno es
modprobe.conf ya que el otro sólo contiene comentarios
    * quién crea moprobe.conf.pacnew?
$ sudo rm /etc/modprobe.d/modprobe.conf.pacnew
"If the kernel module nouveau is loaded according to lsmod command, but there
are no kernel messages about nouveau at all, then most likely Nouveau KMS is
disabled. This prevents the driver to work at all."
$ sed -n '/nouveau/p' /var/log/kernel.log
>
No hay mensajes en el log del kernel por lo que debo tener el kernel mode
setting (KMS) desactivado
"Possible places to disable KMS are: "
    * "kernel command line with: nomodeset, drm.modeset=0, nouveau.modeset=0 or
      similar"
    * "modprobe.conf or modprobe.d/ adding the module options drm modeset=0 or
      nouveau modeset=0"
    * "initramfs carrying the above module options"
$ sed -n '/nomodeset/p' /boot/grub/menu.lst
> kernel /boot/vmlinuz-linux root=/dev/disk/by-uuid/0248b57c-1d8e-438d-8fa6-
2008b0
> 99e0d8 loglevel=3 ro quiet resume=/dev/disk/by-uuid/a5deacf4-9611-4e8a-8c5b-
a7da
> 3663d1ea   nomodeset

$ sudo cp /boot/grub/menu.lst /boot/grub/menu.lst.original
$ sudo sed -i 's/   nomodeset//' /boot/grub/menu.lst
$ sudo reboot
    * rock&roll!!
Al reiniciar ya tengo la resolución que toca, lo único que muestra el log de
Xorg es que no se usará el driver dri para renderizar 3d, el cual probaré mas
adelante
$ sed -n '/] (EE)/p' /var/log/Xorg.0.log | sed 's/^\^*\] //' | tail
> (EE) AIGLX error: dlopen of /usr/lib/xorg/modules/dri/nouveau_dri.so failed
(/us
> r/lib/xorg/modules/dri/nouveau_dri.so: cannot open shared object file: No
such f
> ile or directory)
> (EE) AIGLX: reverting to software rendering
    * Early start
1. Add "nouveau" to the MODULES array in /etc/mkinitcpio.conf
MODULES="... nouveau ..."
2. Re-generate boot image
$ sudo mkinitcpio -p
 e.g. linux>
[ArchWiki Mkinitcpio]"The -p switch specifies a preset to utilize; most kernel
packages provide a related mkinitcpio preset file, found in /etc/mkinitcpio.d
(e.g. /etc/mkinitcpio.d/linux.preset for linux). A preset is a predefined
definition of how to create an initramfs image instead of specifying the
configuration file and output file every time.""For version 3.x kernels, please
use the linux preset:"
# mkinitcpio -p linux
Hacemos las comprobaciones pertinentes
$ ls /etc/mkinitcpio.d
> example.preset  linux.preset
$ uname -r
> 3.1.0-4-ARCH
Y al lio
$ mkinitcpio -p linux
> ==> Building image from preset: 'default'
>   -> -k /boot/vmlinuz-linux -c /etc/mkinitcpio.conf -g /boot/initramfs-
linux.img
> ==> ERROR: Unable to write to path: `/boot/initramfs-linux.img'
> ==> Building image from preset: 'fallback
>   -> -k /boot/vmlinuz-linux -c /etc/mkinitcpio.conf -g /boot/initramfs-linux-
fallback.img -S autodetect
> ==> ERROR: Unable to write to path: `/boot/initramfs-linux-fallback.img'

$ sudo !!
> ==> Building image from preset: 'default'
>   -> -k /boot/vmlinuz-linux -c /etc/mkinitcpio.conf -g /boot/initramfs-
linux.img
> ==> Starting build: 3.1.0-4-ARCH
>   -> Parsing hook: [base]
>   -> Parsing hook: [udev]
>   -> Parsing hook: [autodetect]
>   -> Parsing hook: [pata]
>   -> Parsing hook: [scsi]
>   -> Parsing hook: [sata]
>   -> Parsing hook: [filesystems]
>   -> Parsing hook: [usbinput]
> ==> Generating module dependencies
> ==> Creating gzip initcpio image: /boot/initramfs-linux.img
> ==>
Image generation successful
> ==> Building image from preset: 'fallback'
>   -> -k /boot/vmlinuz-linux -c /etc/mkinitcpio.conf -g /boot/initramfs-linux-
fallback.img -S autodetect
> ==> Starting build: 3.1.0-4-ARCH
>   -> Parsing hook: [base]
>   -> Parsing hook: [udev]
>   -> Parsing hook: [pata]
>   -> Parsing hook: [scsi]
>   -> Parsing hook: [sata]
>   -> Parsing hook: [filesystems]
>   -> Parsing hook: [usbinput]
> ==> Generating module dependencies
> ==> Creating gzip initcpio image: /boot/initramfs-linux-fallback.img
> ==> Image generation successful
*** dual head ***
    * usados
          o http://nouveau.freedesktop.org/wiki/
            Randr12?action=show&redirect=Randr12Howto
    * información adicional
          o https://bbs.archlinux.org/viewtopic.php?pid=652861
          o http://wiki.debian.org/XStrikeForce/HowToRandR12
[Nouveau Rand12HowTo]"Randr 1.2 is used by Nouveau. No need to explicitly
enable it, and you cannot disable it""Randr 1.2 does not use multiple Screen
sections, so if you have those you have to remove them from your
xorg.conf""When Randr12 is enabled, you can check the current Randr12
configuration with with xrandr -q"
Ejecuto la orden
$ xrandr -q
>
Screen 0: minimum 320 x 200, current 1920 x 1080, maximum 8192 x 8192
> DVI-I-1 connected 1920x1080+0+0 (normal left inverted right x axis y axis)
476mm x 268mm
>    1920x1080      60.0*+
>    1680x1050      60.0
>    1280x1024      75.0     72.0     60.0
>    1440x900       59.9
>    1280x960       60.0
>    1152x864       75.0
>    1024x768       75.1     72.0     70.1     60.0
>    832x624        74.6
>    800x600        72.2     75.0     60.3     56.2
>    640x480        72.8     75.0     66.7     60.0
>    720x400        70.1
> HDMI-1 disconnected (normal left inverted right x axis y axis)
> VGA-1 connected 1920x1080+0+0 (normal left inverted right x axis y axis)
476mm x 268mm
>    1920x1080      60.0*+

>    1680x1050      60.0
>    1280x1024      75.0     72.0     60.0
>    1440x900       59.9
>    1280x960       60.0
>    1152x864       75.0
>    1024x768       75.1     72.0     70.1     60.0
>    832x624        74.6
>    800x600        72.2     75.0     60.3     56.2
>    640x480        72.8     75.0     66.7     60.0
>    720x400        70.1
"Change the Monitor identifiers in your xorg.conf to the identifiers which
"xrandr" reports and add a LeftOf/RightOf to one of the Monitor sections"
       Section "Monitor"
         Identifier   "DVI-D-0"
         ...
       Section "Monitor"
         Identifier   "VGA-0"
         ...
         Option "LeftOf" "DVI-D-0"
Todas las modificaciónes relativas a dual head las he hecho en
/etc/X11/xorg.conf.d/20-monitor.conf
/etc/X11/xorg.conf.d/20-monitor.conf
Section "Monitor"
    Identifier    "DVI-I-1"
EndSection

Section "Monitor"
    Identifier    "VGA-1"
    Option "RightOf" "DVI-I-1"
EndSection

Section "Device"
    Identifier    "nvidia G210"
    Driver        "nouveau"
EndSection

Section "Screen"
    Identifier    "Screen0"
    Device        "nvidia G210"
    DefaultDepth  24
    SubSection "Display"
        Depth     24
    EndSubSection
EndSection
*** activar numlock al inicio ***
    * https://wiki.archlinux.org/index.php/Activating_Numlock_on_Bootup
"In the file /etc/slim.conf find the line"
#numlock             on
"and remove the #"
    * el numlock queda activado
          o la luz de indicador queda apagada (empieza encendida, al pulsar  se
            apaga y luego se vuelve a encender :S)
*** ampliar el tiempo de inactividad antes de que se vuelva negra la pantalla
***
    * http://bbs.archbang.org/viewtopic.php?id=363
    * https://wiki.archlinux.org/index.php/Display_Power_Management_Signaling
Trasteando para activar el numlock desde el inicio me he topado con la
configuración de slim
/etc/slim.conf
/etc/slimlock.conf
Como no sé para qué sirve slimlock.conf lo he curioseado y he visto las
siguientes lineas
$ cat /etc/slimlock.conf
>
dpms_standby_timeout            60
> dpms_off_timeout                600

>
> wrong_passwd_timeout            2
> passwd_feedback_x               50%
> passwd_feedback_y               10%
> passwd_feedback_msg             Authentication failed
> show_username                   1
> show_welcome_msg                0
Como al cronometrar lo que tarda la pantalla en apagarse me daba 60 segundos,
voy a cambiar el valor de
dpms_standby_timeoutde 60 a 300 y así comprobaré si esto es lo que afecta al
tiempo de inactividad
    * buscar docuentación de slim donde se expliquen estos dos ficheros de
      configuración
Sin reiniciar no ha tenido efecto el cambio, así que reinicio
    * se puede reiniciar únicamente el slim?
    * añadir los ficheros de configuración de slim al menú de openbox
Resulta que slimlock es una aplicación aparte de slim que usa slim.conf para
mostrar el mismo theme en la pantalla de bloqueo
    * https://bbs.archlinux.org/viewtopic.php?id=119420&p=1
"Note: the 'slimlock' package is out of date, and not maintained by me. Please
use 'slimlock-git' instead"
$ pacman -Qs slimlock
> local/slimlock 0.10.1-1 [0,13 MB]
>     Unholy screen locker based on SLiM.
    * cómo se consultan los paquetes instalados desde packer? (-Qs no
      funciona)
    * cambiar slimlock por slimlock-git
    * desde que he hecho cambios en slim.conf y slimlock.conf no se oscurece la
      pantalla
          o con 90 no lo hace a los 90 segundos
          o con 120 no lo hace a los 120 segundos
          o lo he vuelto a poner a 60 y tampoco lo hace a los 60 segundos como
            hacía
          o como los únicos cambios que recuerdo desde que funcionaba hasta
            que no lo hace son las mods en estos dos archivos y slimlock.conf
            ahora sigue como estaba al principio, supongo que el fallo es
            debido al cambio en slim.conf para que se active el numlock al
            inicio
    * después de que el led del numlock se quede encendido o de que se
      desbloquee, la pantalla se oscurece rápidamente
          o voy a poner el valor de dpms_standby_timeout a 90 para probar si
            tiene efecto después de que la luz del numlock quede encendida
                # no tiene efecto después de la luz encendida
                # no tiene efecto después de desbloquear
    * no sé cuándo empieza atener efecto, pero a partir de entrar en
      funcionamiento sí que usa el parámetro modificado, así que lo dejaré
      con un valor de 300 segundos
Se ha guardado una copia de los archivos slim.conf y slimlock.conf en el estado
en el que vienen con la distribución
/etc/slim.conf.original
/etc/slimlock.conf.original
*** instalar gvim ***
$ packer -Ss vim-gtk
> aur/vim-gtk 7.3.-3
>     Modified from extra/gvim, compiled with gtk2 ui, without deps on vi/vim,
>     ruby and desktop utils.
$ packer -S vim-gtk
> Objetivos (1): python-3.2.2-1 [9,44 MB]
>
> Dependencias opcionales para python
>     tk: for tkinter
>     sqlite3
> :: vim-gtk y vim están en conflicto. ¿Quitar vim? [s/N]
  s
> Se quitará (1): vim-7.3.353-1 [2,21 MB]
>
> Objetivos (1): vim-gtk-7.3.223-3 [5,09 MB]
A continuación salen muchos mensajes diciendo que tal o cual fichero existe en
el sistema de archivos, por lo que deduzco que no se ha instalado correctamente
$ echo $?
> 1
Así que paso a la opción del repositorio extra
$ packer -Ss gvim
> extra/gvim 7.3.353-1 [1,03 MB]
>     Vi Improved, a highly configurable, improved version of the vi text
editor
>     (with advanced features, such as a GUI)
$ packer -S gvim
> :: gvim y vim están en conflicto. ¿Quitar vim? [s/N]
  s
> Se quitará (1): vim-7.3.353-1 [2,21 MB]
>
> Objetivos (3): libyaml-0.1.4-1 [0,08 MB]  ruby-1.9.3_p0-1 [3,07 MB]
>                gvim-7.3.353-1 [1,03 MB]
    * gvim se ha instalado
    * declararlo como editor por defecto
    * ponerlo disponible en el menú principal
    * He hecho que Thunar abra los documentos de texto simple con gvim
      haciéndo boton derecho sobre un fichero de texto plano y modificando la
      aplicación en propiedades > abrir con
    * Los accesos directos a editar ficheros desde el menú de openbox
      especifican una aplicación en concreto (por ejemplo: sudo leafpad /etc/
      rc.conf) y se deberían cambiar desde obmenu
===lanzador de aplicaciones=====
    * https://wiki.archlinux.org/index.php/Openbox
Se puede buscar (o crear si no se encuentra) una aplicación que asociara
aplicaciones a tipos de fichero, por ejemplo permitiendo expresiones regulares
sobre la salida del comando file
$ file $HOME/DOC
> DOC: ASCII English text

$ file /etc/rc.conf
> /etc/rc.conf: ASCII text
El programa deberia aplicar las expresiones regulares a la salida del comando
file excluyendo el nombre del fichero
$ file $HOME/DOC | sed --regexp-extended 's/^[^:]+: //'
> ASCII English text

$ file /etc/rc.conf | sed --regexp-extended 's/^[^:]+: //'
> ASCII text
Así se podría asociar la expresion regular '^ASCII' al programa gvim
[Arch OpenBox]"Because Openbox and the applications you use with it are not
well-integrated you might run into the issues with your browser. Your browser
may not know which program it is supposed to use for certain types of files""A
package in the AUR called gnome-defaults-list contains a list of file-types and
programs specific to the Gnome desktop. The list is installed to /etc/gnome/
defaults.list.""Open this file with your text-editor. Now you can replace a
given application with the name of the program of your choosing. For example,
totem <=> vlc or eog <=> mirage. Save the file to ~/.local/share/applications/
defaults.list.""Another way of setting file associations is to install package
perl-file-mimeinfo from the repository and invoke mimeopen like this: "
mimeopen -d /path/to/file
"You are asked which application to use when opening /path/to/file: "
Please choose a default application for files of type text/plain
       1) notepad  (wine-extension-txt)
       2) Leafpad  (leafpad)
       3) OpenOffice.org Writer  (writer)
       4) gVim  (gvim)
       5) Other...
"Your answer becomes the default handler for that type of file. Mimeopen is
installed as /usr/bin/perlbin/vendor/mimetype."
===configurar (g)vim para que se comporte como en el servidor de
desarrollo=====
    * Añadir la siguiente configuración a
/usr/share/vim/vimfiles/archlinux.vim
" own configuration

syntax on

set ignorecase
set smartcase

set autoindent
set expandtab
set smarttab
set tabstop=4
set shiftwidth=4

noremap   :s/^[ ]/#/
noremap   :s/^#/ /

highlight OverLength ctermbg=yellow ctermfg=white guibg=#592929
match OverLength /\%>79v.\+/
*** configurar urxvt ***
===cambiar cursor de subguión a block=====
    * http://www.mail-archive.com/rxvt-unicode@lists.schmorp.de/msg00300.html
"when you are at normal mode it change to a block-style (the default cursor of
urxvt)"
En
$HOME/.Xdefaultshay una linea que especifica el uso del cursor con guión bajo
URxvt*cursorUnderline:                  true
Como según dice la cita, el bloque es el comportamiento por defecto, elimino
esa linea
También aprovecho para eliminar el molesto parpadeo del cursor eliminando la
linea
 URxvt*cursorBlink:                              true
    * al abrir otro terminal ya aparece el cursor de bloque
===hacer ilimitado el buffer de urxvt=====
    * https://bbs.archlinux.org/viewtopic.php?id=57823
    * http://www.fiveanddime.net/man-pages/rxvt.1.html
urxvt*saveLines:            10000
Además comentan otras opciones que encajan con el comportamiento que espero de
él
URxvt*scrollTtyOutput:      false
URxvt*scrollWithBuffer:     true
URxvt*scrollTtyKeypress:    true
"Scroll when output come but not when you go back in to the buffer (with mouse
scroll or shift pgup)"
"Scroll back to the end on key press (on program stop running and prompt is
back it go back to the end too)"
Voy a probar de poner el parámetro de lineas de buffer a 0 con la esperanza de
que se haga ilimitado
    * con 0 no guarda ninguna linea en el buffer
"rxvt.saveLines number: Causes rxvt to save number lines in he scroll back
buffer instead of the default 64"
    * lo dejo en 10000 de momento
          o encontrar otra solución
===colores=====
    * Comparar colores de .Xdefaults con colores de un .Xdefaults sin
      especificación de color
          o Determinar que combinación de ambos es más cómoda de leer
===archey al inicio=====
$ cat ~/.bashrc
> alias ls='ls --color=auto

> [ ! "$UID" = "0" ] && archbey -c cyan
> [  "$UID" = "0" ] && archbey -c red
===otras opciones...=====
Aparte de la configuración de colores hay unos cuantos parámetros para urxvt
especificados especificados en ese archivo que parecen interesantes, así que
los listo para una futura revisión
/home/pau/.Xdefaults {sección}
URxvt*geometry:                                 80x25
URxvt*foreground:                               grey80
URxvt*borderLess:                               false
URxvt*depth:                                    32
URxvt*background:                               rgba:0000/0000/0000/dddd
URxvt*scrollBar_right:                          true
URxvt*font:                                     xft:Terminus
URxvt*scrollColor:                              #111111
URxvt*saveLines:                                10000
URxvt*scrollTtyOutput:                          false
URxvt*scrollWithBuffer:                         true
URxvt*scrollTtyKeypress:                        true
*** login manager (slim) ***
    * https://wiki.archlinux.org/index.php/SLiM
    * http://slim.berlios.de/themes_howto.php
$ cat $HOME/.xinitrc
> #!/bin/bash
> exec ck-launch-session dbus-launch openbox-session
    * no puedo comprobar si el problema del respawn en tty1 sigue existiendo,
      ya que no puedo cambiar a tty1 con ctrl+alt+F1
          o quién captura esta pulsación de teclas? openbox?
[archlinux]"To share a wallpaper between SLiM and your desktop, rename the used
theme background, then create a link from your desktop wallpaper file to the
default SLiM theme:"
# mv /usr/share/slim/themes/default/background.jpg{,.bck}
# ln -s /path/to/mywallpaper.jpg /usr/share/slim/themes/default/background.jpg
    * Vaya forma mas buena de hacer backup de un fichero!!
          o Esto ha de ir al blog
$ sudo cp /usr/share/slim/themes/archbang{,.original}
$ sudo ln -s /usr/share/wallpapers/archlinux.png /usr/share/
wallpapers/.current.png
Vuelvo a configurar el wallpaper para que cargue .current.png, el cual siempre
apuntará al wallpaper actual (así voy preparando el terreno para los
wallpapers aleatorios)
$ sudo rm /usr/share/slim/themes/archbang/background.png
$ sudo ln -s /usr/share/wallpapers/.current.png /usr/share/slim/themes/
archbang/background.png
*** rdesktop (con seemless) ***
Comando rdesktop para abrir un escritorio remoto que ocupe el 80% de la
pantalla
$ rdesktop -u pau -p 00reset -d RESETCONTROL -g 80% 192.168.0.27
> bash: rdesktop: no se encontró la orden
$ packer -S rdesktop
> Objetivos (2): libao-1.1.0-1 [0,04 MB]  rdesktop-1.7.0-2 [0,10 MB]
$ rdesktop -u pau -p 00reset -d RESETCONTROL -g 80% 192.168.0.27
> Autoselected keyboard map es
> WARNING: Remote desktop does not support colour depth 24; falling back to 16
Como obtiene la resolución de los 2 monitores el ancho de la ventana excede
las dimensiones de un monitor, así que le paso la resolución deseada, la cual
quiero que sea menor que la de un monitor
http://es.wikipedia.org/wiki/Archivo:Vector_Video_Standards2.svg
    * cómo incrustar imágenes de internet en la wiki?
    * resolución monitor: 1920x1080 (HD 1080)
    * resolución para windows: 1024x768 (XGA)
$ rdesktop -u pau -p 00reset -d RESETCONTROL -g 1024x768 192.168.0.27
    * configurar aplicaciones para que actuen seemless
*** cliente ftp ***
    * Instalación
$ packer -S lftp
    * Uso
$ lftp user@host
===thunar=====
Menú > Ir > Abrir lugar (^l): Ponemos una ruta ftp (probado en dmz con
usuario:client):
    * se muestran los ficheros
    * no se pueden eliminar ficheros
          o si se eliminaban, sólo hacía falta actualizar (^r) para ver los
            cambios
    * se pueden copiar a una carpeta local abriendo otra ventana de thunar y
      arrastrando
$ ps -ef | grep ftp
> pau       1026     1  0 10:22 ?        00:00:00 /usr/lib/gvfs/gvfsd-ftp --
spawner :1.2 /org/gtk/gvfs/exec_spaw/3
    * buscar información sobre gvfs
    * cómo se cierra la conexión con el ftp?
*** se usa zathura como visor de pdfs ***
    * https://bbs.archlinux.org/viewtopic.php?id=115118&p=1
    * http://pwmt.org/projects/zathura/
    * http://doc.pwmt.org/zathura/
    * http://slashraul.wordpress.com/2011/01/21/zathura/
    * cómo hacer zoom? [slashraul]
"Most of the time when viewing pdf’s I would like to do zoom to width. You
can do that by simply using the key ‘s’"
    * cómo imprimir?
:print
    * cómo imprimir un rango de páginas?
*** instalar nodejs ***
packer -S nodejs
    * ejemplo: chat
$ cat /home/pau/dev/nodejs/chat.js
#!/usr/bin/node

net = require('net');

var sockets = [];
var s = net.Server(function(socket) {
    sockets.push(socket);

    socket.on('data', function(d) {
        for (var i = 0; i < sockets.length; i++) {
            sockets[i].write(d);
        }
    });
});

s.listen(8000);
*** deshabilitar speaker ***
    * http://willensky.blogspot.com/
    * https://wiki.archlinux.org/index.php/Disable_PC_Speaker_Beep
    * https://wiki.archlinux.org/index.php/Kernel_modules#Blacklisting
    * en /etc/rc.conf
          o sección modules
                # !pcspkr
    * aún teniendo esta linea en rc.conf, el módulo se carga al inicio
$ lsmod | grep pcspkr
> pcspkr                  1375  0
    * eliminando el módulo, se deshabilita el speaker hasta el siguiente
      reinicio
$ sudo rmmod pcspkr
    * como evitar que se cargue al inicio?
[ArchBang]
    * -/etc/modprobe.d/modprobe.conf: add the following lines to disable beep
          o blacklist snd_pcsp
          o blacklist pcspkr
[Blacklisting]"Create a .conf file inside /etc/modprobe.d/ and append a line
for each module you want to blacklist, using the blacklist keyword. If for
example you want to prevent the pcspkr module from loading"
$ cat /etc/modprobe.d/nobeep.conf
> # Do not load the pcspkr module on boot
> blacklist pcspkr
Mirando lo que hay en /etc/modprobe.d, encuentro que ya está hecho, sólo hay
que 'habilitarlo' (parece que alguna actualización lo 'rompió'):
$ ls /etc/modprobe.d
> modprobe.conf.pacsave
$ cat /etc/modprobe.d/modprobe.conf.pacsave
> alias floppy off
> blacklist fd0
> blacklist floppy
> blacklist ipv6
> blacklist bcma
> blacklist pcspkr
> blacklist snd_pcsp
Por lo que lo renombro y listo!
$ sudo mv /etc/modprobe.d/modprobe.conf{.pacsave,}
*** fecha y hora en historial de bash ***
$ HISTTIMEFORMAT='[%F %T] ' history
    * Lamentablemente la fecha y hora que se muestra de los comandos lanzados
      anteriormente es la actual, como si no tuviera registro de fecha y hora
      hasta que se setea la variable de entorno $HISTTIMEFORMAT
    * en que fichero se deben poner las variables de entorno genéricas? (en
      opensuse las pongo en /etc/bash.bashrc.local)
*** dmenu ***
    * En obkey aparece dmenu con la combinación de teclas Alt+F3 lanzando el
      comando "~/.config/dmenu/dmenu-bind.sh"
$ cat ~/.config/dmenu/dmenu-bind.sh
> #!/bin/bash
> exe=`dmenu_path | dmenu_run -nb '#000000' -nf '#FFFFFF' -sb '#FFFFFF' -sf
'#000000'` && eval "exec $exe"
    * dmenu_path no existe así que lo insatalamos
$ packer -Ss dmenu-path
> aur/dmenu-path-c 0.1-2 (17)
>     dmenu_path C rewrite. 2-4x faster on cache hits, 10-20x faster on
>     cache misses
    * se cambia el comando para que siga el estilo común
$ cat ~/.config/dmenu/dmenu-bind.sh
> #!/bin/bash
> exe=`dmenu_path | dmenu_run -nb '#990000' -nf '#FFFFFF' -sb '#FFFFFF' -sf
'#990000' -fn 'Terminus-15'` && eval "exec $exe"
    * se cambia la combinación de teclas a alt+p (igual que los settings por
      defecto en dwm)
***** actualizaciones *****
**** pacman ****
*** eliminar manualmente fichero ***
*** firmas de paquetes ***
    * https://wiki.archlinux.org/index.php/Pacman-key
    * https://bbs.archlinux.org/viewtopic.php?pid=1040457
    * https://wiki.archlinux.org/index.php/Package_signing
$ sudo pacman-key --init
$ curl https://www.archlinux.org/{developers,trustedusers}/ |
> awk -F\" '(/pgp.mit.edu/) {sub(/.*search=0x/,"");print $1}' |
> xargs sudo pacman-key --recv-keys
    * He tenido que fusionar pacman.conf con pacman.conf.pacnew para poder
      actualizar y he activado la opcion de firmas así que no se si el script
      de arriba es necesario
    * También he habilitado el puerto 11371 para la descarga de claves, aunque
      he visto que se pueden usar workarounds para usar otros puertos. Tampoco
      sé si es necesario hacer esto
    * La clave ha sido usar el pacman.conf.pacnew y habilitar la opcion de
      firmas por friquear. En otras instalaciones, probar esta opción primero
