FROM roemer/steamcmd

# Install the dedicated Counter Strike: Source server
RUN /steam-home/steam-cmd/steamcmd.sh +login anonymous +force_install_dir /steam-home/server_css/ +app_update 232330 +quit

# Add Mods
## Metamod
ADD shared-mods/mmsource-1.10.7-git971-linux.tar.gz /steam-home/server_css/cstrike
## SourceMod
ADD shared-mods/sourcemod-1.10.0-git6462-linux.tar.gz /steam-home/server_css/cstrike
## Damage Report
ADD css-server/mods/gem_damage_report-1.1.13.smx /steam-home/server_css/cstrike/addons/sourcemod/plugins/gem_damage_report.smx 

# Start the server
CMD /steam-home/server_css/srcds_run -game cstrike +map de_dust -maxplayers 12
