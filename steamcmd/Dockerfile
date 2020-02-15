FROM ubuntu:18.04

# Prepare the system
RUN apt-get update && \
    apt-get install -y nano curl lib32gcc1 lib32tinfo5 && \
    rm -rf /var/lib/apt/lists/*

# Add a separate user
RUN useradd --create-home --home-dir /steam-home --shell /bin/bash --uid 1000 steam \
    && chown -R steam /steam-home

# Switch to that user
USER steam

# Install SteamCMD (https://developer.valvesoftware.com/wiki/SteamCMD)
RUN mkdir /steam-home/steam-cmd && \
    curl -sqL "https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz" | tar zxvf - -C /steam-home/steam-cmd
# Initialize SteamCMD
RUN /steam-home/steam-cmd/steamcmd.sh +quit

# Support for 64-bit systems
# https://www.gehaxelt.in/blog/cs-go-missing-steam-slash-sdk32-slash-steamclient-dot-so/
RUN ln -s /steam-home/steam-cmd/linux32/ /steam-home/.steam/sdk32

# Expose the ports
## Game transmission, pings and RCON
EXPOSE 27015 27015/udp
## SourceTV transmission
EXPOSE 27020/udp
## Client Port
EXPOSE 27005/udp
