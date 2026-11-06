# TP5 Traefik : Reverse Proxy et Load Balancing

Déroulé et réponses du TP : [load-balancing-tp.md](load-balancing-tp.md)

## Prérequis

Docker, Docker Compose v2, curl. Ports 80, 443 et 8080 libres.

## Lancement

Certificat HTTPS local (une seule fois, non versionné) :

```bash
winget install FiloSottile.mkcert
mkcert -install
mkcert -cert-file certs/app1.pem -key-file certs/app1-key.pem app1.localhost
```

Démarrage :

```bash
docker network create frontend
docker compose up -d
```

## Accès

| Service | URL |
|---|---|
| Dashboard Traefik | http://localhost:8080/dashboard/ |
| App 1 | http://app1.localhost et https://app1.localhost |
| App 2 | http://app2.localhost |

## Arrêt

```bash
docker compose down
```
