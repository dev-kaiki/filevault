<div align="center">

# filevault

<a href="https://dev-kaiki-filevault.vercel.app"><img src="https://img.shields.io/badge/LIVE%20DEMO-Vercel-111?style=for-the-badge&logo=vercel&logoColor=white"></a>
<a href="https://dev-kaiki-filevault-api.onrender.com/docs"><img src="https://img.shields.io/badge/SWAGGER-API%20Docs-111?style=for-the-badge&logo=swagger&logoColor=white"></a>
<a href="https://github.com/dev-kaiki/filevault"><img src="https://img.shields.io/badge/REPO-GitHub-111?style=for-the-badge&logo=github&logoColor=white"></a>

</div>

## Quick Links
- Live: https://dev-kaiki-filevault.vercel.app
- Swagger: https://dev-kaiki-filevault-api.onrender.com/docs

## Deploy (1-click)
- Deploy API (Render): https://render.com/deploy?repo=https://github.com/dev-kaiki/filevault
- Deploy Web (Vercel): https://vercel.com/new/clone?repository-url=https://github.com/dev-kaiki/filevault

---

# FileVault â€” Secure Upload (Presigned URLs + MinIO/S3)

[![CI](https://github.com/dev-kaiki/filevault/actions/workflows/ci.yml/badge.svg)](https://github.com/dev-kaiki/filevault/actions/workflows/ci.yml)
![Node](https://img.shields.io/badge/node-20%2B-222?logo=node.js)
![NestJS](https://img.shields.io/badge/nestjs-10-222?logo=nestjs)
![MinIO](https://img.shields.io/badge/minio-222?logo=minio)
![Postgres](https://img.shields.io/badge/postgres-16-222?logo=postgresql)
![Docker](https://img.shields.io/badge/docker-ready-222?logo=docker)

ServiÃ§o de upload seguro com **links temporÃ¡rios (presigned)**, organizaÃ§Ã£o por pastas/tags e auditoria de acesso.

> **Status atual:** repo criado a partir do template (API + Web + Postgres + MinIO no docker-compose).  
> Endpoints prontos: `/health`, `/users` e Swagger `/docs`.  
> A feature de upload entra no roadmap abaixo.

---

## ðŸŽ¯ Objetivo
Permitir uploads e downloads com seguranÃ§a, sem expor credenciais:
- gerar **presigned URL** para upload
- validar tamanho/tipo (MIME)
- organizar por cliente/pasta/tag
- registrar auditoria (quem baixou/quando)

---

## âœ… Roadmap (MVP do demo)
- [ ] `POST /files/presign-upload` (retorna URL + key)
- [ ] `GET /files/presign-download/:id`
- [ ] Metadados em Postgres (nome, tamanho, mime, pasta, tags)
- [ ] Regras de validaÃ§Ã£o (limites configurÃ¡veis)
- [ ] Auditoria bÃ¡sica (downloads)
- [ ] Tela Web simples para listar arquivos

---

## ðŸ§± Stack
- **API:** NestJS + Prisma
- **Storage:** MinIO (compatÃ­vel S3)
- **DB:** Postgres
- **Web:** Next.js (UI de listagem/gestÃ£o)

---

## â–¶ï¸ Rodar local
### 1) Subir containers
```powershell
corepack enable
corepack prepare pnpm@latest --activate

pnpm install
docker compose up -d

