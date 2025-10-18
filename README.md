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

## 🧰 Using VS Code tasks

App tasks:

- **hello: up** – `docker compose up -d --build`
- **hello: logs (follow)** – tail logs
- **hello: down** – stop & remove
- **git: sync (hello-site)** – commit + pull --rebase + push

**Run:** `Ctrl/Cmd+Shift+P` → “Tasks: Run Task” → select a task.

### Day-to-day flow (static site)
- Edit `html/index.html` → save → refresh browser (bind mount = instant)
- For image-based deploys, push to GitHub; update tag in Portainer if using immutable tags
