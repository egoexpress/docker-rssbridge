# RSS-Bridge Docker Setup

This repository contains a Docker Compose configuration for running RSS-Bridge, a PHP project capable of generating RSS and Atom feeds for websites that don't have one.

## Prerequisites

- Docker and Docker Compose installed
- An external Docker network named `proxy_frontend` (for reverse proxy integration)

## Environment Variables

Create a `.env` file in the same directory as `docker-compose.yml` with the following variables:

```bash
VIRTUAL_HOST=your-domain.com
LETSENCRYPT_HOST=your-domain.com
LETSENCRYPT_EMAIL=your-email@example.com
```

## Usage

1. **Create the external network** (if it doesn't exist):
   ```bash
   docker network create proxy_frontend
   ```

2. **Start the service**:
   ```bash
   docker-compose up -d
   ```

3. **Stop the service**:
   ```bash
   docker-compose down
   ```

## Configuration

- RSS-Bridge configuration files are stored in the Docker volume `config`
- The service automatically restarts unless stopped manually
- The container uses the `rssbridge/rss-bridge:2025-08-05` image

## Reverse Proxy Integration

This setup is designed to work with a reverse proxy (like Nginx Proxy Manager) using the `proxy_frontend` network. The environment variables configure automatic SSL certificate generation via Let's Encrypt.

## Access

Once running, RSS-Bridge will be accessible through your configured domain via the reverse proxy.