# steamapps-servers
Some Docker images with Steam based dedicated servers.

# Servers

## Counter Strike: Source
### Usage
docker run -p 27015:27015 -p 27015:27015/udp -p 27020:27020/udp --name css-server roemer/css-server

# Development
## Building
### steamcmd
`docker build -t roemer/steamcmd -f steamcmd/Dockerfile .`

### css-server
`docker build -t roemer/css-server -f css-server/Dockerfile .`