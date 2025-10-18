# Hello Site (Static Example)

Simple static site served by Nginx and managed via Docker + Caddy.

## 📁 Structure

hello-site/
├── html/
│ └── index.html
├── dockerfile
└── compose.yaml

## 🚀 Run Locally
```bash
docker compose up -d


Then visit http://localhost:8080

## ☁️ Deploy

Deployed via the Hetzner host, routed through Caddy at https://hello.graspingai.com

Updates flow through GitHub Actions:

1. Push to main

2. GitHub builds → pushes image to GHCR

3. Portainer redeploys with latest image

## 🔧 Notes

Live-edit supported via bind mount (html:/usr/share/nginx/html)

CI workflow: .github/workflows/docker.yml


---

## 💻 4. `/srv/apps/Webster` → `aaronk83/webster`

### `.gitignore`
```gitignore
.DS_Store
*.log
node_modules/
dist/
.vscode/
.env
__pycache__/
*.pyc

