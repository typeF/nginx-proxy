# About
Docker-compose file for setting up nginx & letsencrypt based on [nginx-proxy and nginx-proxy-companion](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion)

# Setup

Make sure your DNS accepts CAA record for [letsencrypt](https://letsencrypt.org/docs/caa/)
```
CAA
0 issue letsencrypt.org
```

Replace the DEFAULT_EMAIL and network name variables in docker-compose.yml with your own.

Setup the docker container
```
docker-compose up -d
```

Make sure the networked containers contain the following environment variables:
```
VIRTUAL_HOST=YOUR_DOMAIN.TLD
LETSENCRYPT_HOST=YOUR_DOMAIN.TLD
```

Nginx should correctly reverse proxy requested urls to the corresponding application container.

