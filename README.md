# Simple Traefik Proxy

This project sets up a simple Traefik proxy for subdomains with multiple containers. We will use three services: `orders`, `payments`, and `traefik`, each with its own Docker Compose file. These services will be run one by one.

## Prerequisites

- Docker
- Docker Compose

## Setup Instructions

### Step 1: Create Traefik Network

First, create a Docker network for Traefik. This network will be shared by all services.

```sh
docker network create traefik
```


### Step 2: Run Traefik Service

Navigate to the Traefik service directory and run the Docker Compose file

```sh
cd traefik
docker-compose up -d
```

### Step 3: Run Orders Service

Navigate to the Orders service directory and run the Docker Compose file.

```sh
cd ../orders
docker-compose up -d
```

### Step 4: Run Payments Service

Navigate to the Payments service directory and run the Docker Compose file.

```sh
cd ../payments
docker-compose up -d
```

### Directory Structure

Your project directory should look like this:

```sh
.
├── traefik
│   └── docker-compose.yml
├── orders
│   └── docker-compose.yml
└── payments
    └── docker-compose.yml

```


### Accessing Services

Once all services are up and running, you can access them via the following URLs:

- Orders service: http://orders.yourdomain.com
- Payments service: http://payments.yourdomain.com

You can also access the Traefik dashboard (if enabled) at http://localhost:8085/dashboard