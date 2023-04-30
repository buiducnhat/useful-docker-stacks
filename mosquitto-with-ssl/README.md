# Mosquitto docker-compose for quick deploying

## Prequisites

- docker cli
- docker-compose (usually comes with docker)

## Usage

- Clone this repo
- Run `docker-compose up -d` to start the service
- Run `docker-compose down` to stop the service

## Configuration

- Edit `mosquitto.conf` to change the configuration, Some popular configuration can be found in [mosquitto.conf](https://mosquitto.org/man/mosquitto-conf-5.html)
  - user
  - password
  - listener
  - host
  - port
  - persistence
  - log_dest
- Edit `docker-compose.yml` to change the port mapping, volume mapping, etc.

### Using SSL

- If you don't want to use SSL, just comment out the **mqtt**, **websocket** listener sections that having cert files in `./config/mosquitto.conf`
- Store your SSL certificate and key in `./mosquitto/certs/`
  - Default certificate name is `cert.pem`, `cacert.pem`, `private.key` (can be changed in `mosquitto.conf`)

## Author

[Bùi Đức Nhật](https://github.com/buiducnhat)
