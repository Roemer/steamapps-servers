FROM roemer/steamcmd

# Add some additional packages
USER root
RUN dpkg --add-architecture i386;
RUN apt-get update && \
    apt-get install -y mailutils postfix curl wget file bzip2 gzip unzip bsdmainutils python util-linux tmux lib32gcc1 libstdc++6 libstdc++6:i386 libcurl4-gnutls-dev:i386 && \
    rm -rf /var/lib/apt/lists/*
USER steam

# Install the dedicated Left 4 Dead 2 server
RUN /steam-home/steam-cmd/steamcmd.sh +login anonymous +force_install_dir /steam-home/server_l4d2/ +app_update 222860 +quit

# Add Mods
## Metamod
ADD shared-mods/mmsource-1.10.7-git971-linux.tar.gz /steam-home/server_l4d2/left4dead2
## SourceMod
ADD shared-mods/sourcemod-1.10.0-git6462-linux.tar.gz /steam-home/server_l4d2/left4dead2

ENV L4D2_START="+map c2m1_highway +maxplayers 8 +rcon_password admin"

# Start the server
CMD /steam-home/server_l4d2/srcds_run -game left4dead2 $L4D2_START
