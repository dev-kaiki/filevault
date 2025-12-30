# FileVault — Secure Upload (Presigned URLs + MinIO/S3)

[![CI](https://github.com/dev-kaiki/filevault/actions/workflows/ci.yml/badge.svg)](https://github.com/dev-kaiki/filevault/actions/workflows/ci.yml)
![Node](https://img.shields.io/badge/node-20%2B-222?logo=node.js)
![NestJS](https://img.shields.io/badge/nestjs-10-222?logo=nestjs)
![MinIO](https://img.shields.io/badge/minio-222?logo=minio)
![Postgres](https://img.shields.io/badge/postgres-16-222?logo=postgresql)
![Docker](https://img.shields.io/badge/docker-ready-222?logo=docker)

Serviço de upload seguro com **links temporários (presigned)**, organização por pastas/tags e auditoria de acesso.

> **Status atual:** repo criado a partir do template (API + Web + Postgres + MinIO no docker-compose).  
> Endpoints prontos: `/health`, `/users` e Swagger `/docs`.  
> A feature de upload entra no roadmap abaixo.

---

## 🎯 Objetivo
Permitir uploads e downloads com segurança, sem expor credenciais:
- gerar **presigned URL** para upload
- validar tamanho/tipo (MIME)
- organizar por cliente/pasta/tag
- registrar auditoria (quem baixou/quando)

---

## ✅ Roadmap (MVP do demo)
- [ ] `POST /files/presign-upload` (retorna URL + key)
- [ ] `GET /files/presign-download/:id`
- [ ] Metadados em Postgres (nome, tamanho, mime, pasta, tags)
- [ ] Regras de validação (limites configuráveis)
- [ ] Auditoria básica (downloads)
- [ ] Tela Web simples para listar arquivos

---

## 🧱 Stack
- **API:** NestJS + Prisma
- **Storage:** MinIO (compatível S3)
- **DB:** Postgres
- **Web:** Next.js (UI de listagem/gestão)

---

## ▶️ Rodar local
### 1) Subir containers
```powershell
corepack enable
corepack prepare pnpm@latest --activate

pnpm install
docker compose up -d
