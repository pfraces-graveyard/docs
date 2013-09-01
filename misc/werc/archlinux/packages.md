# dev home

*   tk  

    libreria para crear interfaces gráficos  
    requerido por **gitk**

*   tcl  

    lenguaje de programación interpretado  
    requerido por **tk** 

# varios

    ? dbus
    ? udev
    ? udisks
    
    > trash-can
    < gerix-wifi-cracker-ng (yaourt)
    
    < bluez		    # audio bluetooth needed?
    < alsa-lib	    # audio bluetooth needed?
    < lame		    # mp3 needed?
    < play		    # mp3 needed?
    < gstreamer	    # codecs backend needed?
    < gstreamer0.10	# codecs backend needed?
    < cddb_get	    # cddb needed?
    
    pacman yaourt # packer mejor?
    pacman feh
    asunder		    # ripper (ogg, mp3, wav, acc, flac)
                # buscar algo mas keyboard-oriented
    cdrkit		    # cd/dvd recording tools
    nxclient	    # xorg remote desktop
    vorbis-tools	# ogg123 (ogg player)
                # oggenc (used by asunder for rip in ogg)
    rtorrent
    mpd + ncmpcpp + mpc
    aircrack-ng-scripts
    
    pkgtools
    - Make sure to run pkgfile --update before use
    - pkgfile includes a "command not found" hook for both zsh and bash.
    This will automatically run pkgfile whenever you run
    a command which the shell cannot find. If you want
    this functionality, set CMD_SEARCH_ENABLED to 1 in
    /etc/pkgtools/pkgfile.conf (or per-user by copying
    that file to ${XDG_CONFIG_HOME}/pkgtools/pkgfile.conf), then
    in your current shell run:
     source /etc/profile
    - An entry has been placed in /etc/cron.daily to run pkgfile --update
    If you do not want this functionality, set UPDATE_CRON=0 ins
    /etc/pkgtools/pkgfile.conf
    
    xnots
    xorg-xfontsel: selector de fuentes para X.org
    xorg-xlsfonts: lista las funetes conocidas por Xorg
    xorg-xfd: juego de caracteres de la fuente elegida
    terminus-font: fuente para lecturas de +8 horas con semigraficos
    ttf-openlogos # fuente de logos open source
    scrot           # captura de pantalla
    htop     # visor de procesos n-curses
    < inkscape (no lo uso)
    < yaourt xampp (sustituido por nginx)
    packer
    qemu qemu-launcher
    unzip
    acpi # informacion de la bateria
    pacgraph # grafico de relaciones de paquetes y dependencias
    xclip # gestion de portapapeles desde consola

# web server
[nginx](https://wiki.archlinux.org/index.php/Nginx)

    fcgi
    php
    php-cgi

# suckless.org
    st-hg
    surf # o uzbl?
    dwm
    tabbed-hg
    dmenu
    9base

## werc
    sudo -k packer -S werc-hg
    # incluye plan9port

# juegos
    < pacman supertuxkart
    < pacman tmw      # the mana world
    < pacman warmux






