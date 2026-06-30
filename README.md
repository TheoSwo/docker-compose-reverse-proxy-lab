PREFACE: I used Claude to help me with this simple project, I am very new and am still learning


# Docker Compose Reverse Proxy Lab

A small multi-container project demonstrating Nginx as a reverse proxy in front of an isolated backend service, deployed across two networked Linux VMs.

## Architecture

- VM1 and VM2 connected via a private host-only network with static IPs
- VM2 runs the Docker Compose stack:
  - nginx: public-facing reverse proxy, exposed on port 8080
  - backend:  Python HTTP server, not exposed to the host, only reachable inside the Docker network
- Verified end-to-end connectivity from VM1 to the proxied service on VM2

## Run that thang

```bash
docker compose up -d
curl http://localhost:8080
```
