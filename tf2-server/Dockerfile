FROM roemer/steamcmd

# Install the dedicated Team Fortress 2 server
RUN /steam-home/steam-cmd/steamcmd.sh +login anonymous +force_install_dir /steam-home/server_tf2/ +app_update 232250 +quit

# Add Mods
## Metamod
ADD shared-mods/mmsource-1.10.7-git971-linux.tar.gz /steam-home/server_tf2/tf
## SourceMod
ADD shared-mods/sourcemod-1.10.0-git6462-linux.tar.gz /steam-home/server_tf2/tf

# Start the server
CMD /steam-home/server_tf2/srcds_run -game tf +map cp_badlands +maxplayers 24
