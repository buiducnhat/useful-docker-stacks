# nginx with ssl docker setup

## Prequisites

- docker cli
- docker-compose (usually comes with docker)

## Usage

- Clone this repo
- Run `docker-compose up -d` to start the service
- Run `docker-compose down` to stop the service

## Configuration

- Edit `nginx.conf` to change the server name, port, etc.
- If you don't want to use SSL, reset the location section in server ssl to non-ssl server (in `nginx.conf`), the after like this:

  ```nginx
  ...
  http {
    server {
        listen 80;
        server_name your.domain;

        location / {
            root /usr/share/nginx/html;
            index index.html index.htm;
            try_files $uri $uri/ /index.html;
        }
    }

    #remove this server listen to 443
  }
  ...
  ```

- Store your SSL certificate and key files in `./certs/`
  - Default certificate name is `cert.crt`, `private.key` (can be changed in `nginx.conf`)

## Author

[Bùi Đức Nhật](https://github.com/buiducnhat)
