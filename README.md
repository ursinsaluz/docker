# Self-Hosted Docker Projects

A collection of self-hosted services and tools running on Docker, orchestrated with Docker Compose and exposed via Traefik.

## Overview

This repository contains configurations for various open-source applications. Each project is contained within its own directory with a `docker-compose.yml` (or `compose.yml`) file.

### Infrastructure

- **Reverse Proxy**: [Traefik](traefik/) handles routing, SSL termination (via Let's Encrypt or mkcert), and load balancing.
- **Network**: All services joined to the external `web` network to be accessible by Traefik.
- **Domains**: Services are typically exposed at `https://<service-name>.docker.localhost` for local development.

## Project List

| Project | Description | Config |
| :--- | :--- | :--- |
| **Appsmith** | Low-code application platform | [Config](appsmith/docker-compose.yaml) |
| **Budibase** | Low-code platform for building business apps | [Config](budibase/compose.yml) |
| **Corteza** | Digital work platform | [Config](corteza/docker-compose.yml) |
| **DocuSeal** | Document signing and processing | [Config](docuseal/docker-compose.yml) |
| **Faceswap** | Deepfakes software | [Config](faceswap/docker-compose.yml) |
| **Forem** | Community platform software | [Config](forem/docker-compose.yml) |
| **Formbricks** | Survey platform | [Config](formbricks/docker-compose.yml) |
| **Home Assistant** | Home automation platform | [Config](homeassistant/compose.yml) |
| **Homepage** | Dashboard for services | [Config](homepage/compose.yml) |
| **Hoppscotch** | API development ecosystem | [Config](hoppscotch/docker-compose.yml) |
| **IT-Tools** | Collection of handy online tools | [Config](it-tools/docker-compose.yaml) |
| **Jitsu** | Data ingestion pipeline | [Config](jitsu/docker-compose.yml) |
| **Kestra** | Workflow orchestration | [Config](kestra/compose.yml) |
| **Maybe** | Personal finance management | [Config](maybe/docker-compose.yml) |
| **n8n** | Workflow automation tool | [Config](n8n/docker-compose.yml) |
| **NocoBase** | No-code database platform | [Config](nocobase/docker-compose.yml) |
| **NocoDB** | Airtable alternative | [Config](nocodb/docker-compose.yml) |
| **Penpot** | Design and prototyping tool | [Config](penpot/docker-compose.yaml) |
| **Portainer** | Container management | [Config](portainer/compose.yml) |
| **PostHog** | Product analytics | [Config](posthog/docker-compose.yml) |
| **Stirling-PDF** | PDF manipulation tools | [Config](stirlingpdf/docker-compose.yml) |
| **Teable** | No-code database | [Config](teable/docker-compose.yaml) |
| **Traefik** | The edge router / reverse proxy | [Config](traefik/docker-compose.yaml) |
| **Twenty** | Open-source CRM | [Config](twenty/docker-compose.yml) |
| **Typebot** | Chatbot builder | [Config](typebotio/docker-compose.yml) |
| **Umami** | Web analytics | [Config](umami/docker-compose.yml) |
| **Vespa** | Search engine and vector database | [Config](vespa/compose.yml) |
| **Windmill** | Developer platform for scripts and UIs | [Config](windmill/docker-compose.yml) |

## Getting Started

1.  **Start Traefik**:
    Ensure the main Traefik instance is running and the `web` network exists.
    ```bash
    docker network create web || true
    cd traefik
    docker compose up -d
    ```

2.  **Run a Project**:
    Navigate to a project directory and start it.
    ```bash
    cd <project-directory>
    docker compose up -d
    ```

3.  **Access the Service**:
    Open your browser and navigate to `https://<project>.docker.localhost` (or the configured domain).

## Notes

- Some projects may require additional `.env` configuration.
- Data is typically persisted in named volumes or local subdirectories (ignored by git).
