# Zeros — Self‑Hosted AI Studio (Production Scaffold)

This repository is a production-ready scaffold for "Zeros": a premium, mobile-first AI studio with a zero-key UX (server holds and manages model services). It provides a full local/dev environment via Docker Compose and pluggable adapters so you can run self-hosted LLMs, image generation, search, and a vector memory store.

Quick start (dev)

1. Copy `.env.example` to `.env` and edit as needed.
2. Run: `docker compose up --build` (or `docker-compose up --build` depending on your Docker version)
3. Visit: `http://localhost:3000`

What's included

- Next.js frontend (TypeScript, Tailwind) with a mobile-first chat UI and image studio page.
- Backend API routes that proxy to local model services (text generation, image, search).
- Docker Compose for local dev with Postgres + pgvector, Redis, model service stubs, Automatic1111 stub, and SearxNG.
- README, model setup docs, and .env.example to guide production deployment.

Production notes

- This scaffold is intended as a starting point. Replace the model stubs with your chosen self-hosted servers (vLLM, text-generation-webui, Automatic1111, etc.) and secure the deployment behind a reverse proxy (Traefik / NGINX) with TLS.
- Use Kubernetes (or VM-based production) for scale. Keep model servers internal — only expose the Next.js frontend or a dedicated API gateway to the public.
- Add authentication, rate limiting, observability (Prometheus/Grafana/Datadog), and backups for production.

Next steps

I will add the remaining production hardening: streaming SSE chat, user accounts and per-user persistent memory, rate limiting, admin dashboard, and CI/CD pipeline. Tell me which to prioritize next or if you want me to push all files now.
