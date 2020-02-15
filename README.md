# steamapps-servers
Some Docker images with Steam based dedicated servers.

# Servers

## Counter Strike: Source
### Usage
docker run -p 27015:27015 -p 27015:27015/udp -p 27020:27020/udp --name css-server roemer/css-server

## Left 4 Dead 2
### Usage
docker run -p 27015:27015 -p 27015:27015/udp -p 27020:27020/udp --name l4d2-server roemer/l4d2-server

## Team Fortress 2
## Usage
docker run -p 27015:27015 -p 27015:27015/udp -p 27020:27020/udp --name tf2-server roemer/tf2-server

# Development
## Building
### steamcmd
`docker build -t roemer/steamcmd -f steamcmd/Dockerfile .`

### css-server
`docker build -t roemer/css-server -f css-server/Dockerfile .`

### l4d2-server
`docker build -t roemer/l4d2-server -f l4d2-server/Dockerfile .`

### tf2-server
`docker build -t roemer/tf2-server -f tf2-server/Dockerfile .`
