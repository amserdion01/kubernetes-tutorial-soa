# Microservices Kubernetes Setup

This repository contains a simple Kubernetes-based setup for multiple services (User, Post, Notification, UI) plus infrastructure components (Postgres, RabbitMQ). You can deploy them all in one go, or selectively, based on your needs.

## Repository Structure

| File              | Description                                                        |
|-------------------|--------------------------------------------------------------------|
| **`README.md`**   | This file—provides an overview and usage instructions.            |
| **`ingress.yaml`**| Defines an Ingress resource to expose services under specific paths or domain names. Requires an Ingress Controller (NGINX, Traefik, etc.). |
| **`notification.yaml`** | Contains the Deployment, Service, and possibly a ConfigMap for the **Notification** service. |
| **`post.yaml`**   | Contains the Deployment, Service, and possibly a ConfigMap for the **Post** service. |
| **`postgres.yaml`** | Contains a Deployment and Service for **PostgreSQL** (database). |
| **`rabitmq.yaml`**  | (Likely intended as `rabbitmq.yaml`)—Defines a Deployment and Service for **RabbitMQ** (message broker). |
| **`ui.yaml`**     | Contains the Deployment, Service, and environment variables for the **UI** (frontend). |
| **`user.yaml`**   | Contains the Deployment, Service, and possibly a ConfigMap for the **User** service. |

> **Note**: You may rename files to keep naming consistent (for example, `rabbitmq.yaml` instead of `rabitmq.yaml`).

## Prerequisites

1. A running Kubernetes cluster (local or remote).
2. `kubectl` installed and configured to communicate with that cluster.
3. Docker images (for each microservice and the UI) stored in a registry accessible by the cluster—or built locally if using a local Kubernetes setup (e.g., Docker Desktop, minikube, or kind).

## Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/your-account/your-repo.git
cd your-repo
# kubernetes-tutorial-soa
