# FileVault

Secure upload: presigned URLs + storage abstraction

## Links
- Live (Vercel): https://dev-kaiki-filevault.vercel.app
- Swagger (Render): https://dev-kaiki-filevault-api.onrender.com/docs
- Health: https://dev-kaiki-filevault-api.onrender.com/health

## One-click deploy

API (Render Blueprint):
https://render.com/deploy?repo=https://github.com/dev-kaiki/filevault

WEB (Vercel):
https://vercel.com/new/clone?repository-url=https://github.com/dev-kaiki/filevault&project-name=dev-kaiki-filevault&repository-name=filevault&root-directory=apps/web

Vercel ENV:
NEXT_PUBLIC_API_URL=https://dev-kaiki-filevault-api.onrender.com

## Local (Windows)
Run:
powershell -ExecutionPolicy Bypass -File .\dev.ps1