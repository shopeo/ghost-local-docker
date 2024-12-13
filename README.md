# Ghost local docker ssl

## Configuration environment

create a file `.env` or copy the file `.env.example` to `.env` and set the values

```bash
DOMAIN_NAME=example.com
```

## Generate ssl certificate

### Install mkcert on macOS

```bash
brew install mkcert
brew install nss # if you use Firefox
```

### Create a local CA

```bash
mkcert -key-file ./nginx/certs/example.com.key -cert-file ./nginx/certs/example.com.crt example.com
```

### Install root certificate

```bash
mkcert -install
````

## Start container

```bash
docker-compose up -d
```
