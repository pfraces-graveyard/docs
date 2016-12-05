Archlinux postinstall
=====================

Utilities

    sudo packer -S --noconfirm \
        git \
        st \
        tmux \
        vim \
        bash-completion \
        downgrade \
        z-git \
        the_silver_searcher \
        numlockx \
        curl

Fonts

    sudo packer -S --noconfirm \
        terminus-font \
        ttf-inconsolata \
        ttf-freefont \
        ttf-arphic-uming \
        ttf-baekmuk
        
i3

    sudo packer -S --noconfirm \
        i3-wm \
        i3status \
        dmenu \
        slock \
        scrot \
        ranger \
        xclip \
        xorg-xkill \
        htop

Chromium

    sudo packer -S --noconfirm  \
        chromium \
        chromium-pepper-flash

Chormium Extensions

*   Adblock Plus
*   Postman
*   Web Developer Form Filler
*   Webpage Screenshot