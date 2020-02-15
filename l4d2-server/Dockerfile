FROM roemer/steamcmd

# Install the dedicated Left 4 Dead 2 server
RUN /steam-home/steam-cmd/steamcmd.sh +login anonymous +force_install_dir /steam-home/server_l4d2/ +app_update 222860 +quit

# Add Mods
## Metamod
ADD shared-mods/mmsource-1.10.7-git971-linux.tar.gz /steam-home/server_l4d2/left4dead2
## SourceMod
ADD shared-mods/sourcemod-1.10.0-git6462-linux.tar.gz /steam-home/server_l4d2/left4dead2

# Start the server
CMD /steam-home/server_l4d2/srcds_run -game left4dead2 +map c2m1_highway -maxplayers 8
