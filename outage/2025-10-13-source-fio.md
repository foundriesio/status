## 2025-10-13 source.foundries.io outage

Our [git service](https://source.foundries.io) was unreachable from 17:32UTC to 18:25UTC.

### Timeline of Events

- **17:30 UTC** - Clean up operation from prior migration was performed to remove old resources.
- **17:32 UTC** - We notice source.foundries.io is offline
- **17:36 UTC** - Service is temporarily restored
- **17:40 UTC** - Service goes offline again
- **17:41 UTC** - We observe the GKE Ingress has a "local" LetsEncrypt certificate. This is causing CloudFlare to not proxy traffic to our service.
- **18:02 UTC** - Certificate from previous backup is recovered while we debug CertManager
- **18:15 UTC** - Certificate from previous backup is applied
- **18:25 UTC** - Certificate change propagtes to GKE Ingress
- **18:36 UTC** - Fix to CertManager configuration is applied


## Root cause

While cleaning up an old NFS server in production, the git server "deployment"
mistakenly deleted. This was quickly noticed and fixed. However, during that
time, the TLS certificates for the service were overwritten to use a local,
self-signed certificate. The original certificate was restored from backup and
applied.

The main difficulty faced was debugging cert-manager to understand what it was
doing. We have fixed that issue, succesfully generated a new certificate, and
are deploying changes to prevent this issue in the future.
