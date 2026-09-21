# EasyPanel deployment - remove.workflowfree.com

This package is a static client-side application served by Nginx.
No database, Node.js runtime, PHP, or application backend is required.

## EasyPanel

1. Create/select project `remove_watermark`.
2. Add service: **App**.
3. Connect this Git repository.
4. Build method: **Dockerfile**.
5. Dockerfile path: `Dockerfile`.
6. Internal/container port: **80**.
7. Deploy.
8. In Domains, add `remove.workflowfree.com` and route it to port 80.
9. DNS: create an A record for `remove` pointing to the EasyPanel server IP.
10. Let EasyPanel provision HTTPS/Let's Encrypt after DNS resolves.

## Health check

The container exposes:

`GET /healthz` -> HTTP 200 `ok`

Docker also performs an internal health check every 30 seconds.

## Update workflow

Push changes to the configured branch, then redeploy in EasyPanel. `index.html`
and `main.js` are configured as no-cache to reduce stale-version issues during active development.

## Production URL

https://remove.workflowfree.com/
