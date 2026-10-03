# gcp-ssh — Universal SSH Proxy Deployer (GCP Cloud Shell)

Two-mode SSH proxy deployer for GCP Cloud Shell:

- **Mode 1 — Cloud Run** (no VM quota needed): builds & deploys the SSH-over-WebSocket
  gateway as a Cloud Run service.
- **Mode 2 — Compute Engine**: provisions a full VM (nginx, squid, openssh, docker)
  for heavier VPN use.

## Run (in GCP Cloud Shell)

```bash
chmod +x ssh
./ssh
```

The script checks `gcloud` presence/authentication, enables required APIs, and walks
you through the mode selection.

## Security notes

- Cloud Shell sessions are ephemeral — persist any credentials the script prints.
- Review firewall rules created in Mode 2; restrict source ranges where possible.
