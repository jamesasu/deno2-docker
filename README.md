# Deno 2 Test

> Just a quick setup of Deno 2.0.0 in Docker

# Setup

The steps I used to create this docker image:

## 1. Create `Dockerfile` with the following content:

```Dockerfile
FROM denoland/deno:2.0.0
EXPOSE 1993
WORKDIR /app
USER deno
COPY . .
```

## 2. Create `compose.yml` file with the following content:

```yaml
services:
  app:
    build: .
    volumes:
      - .:/app
```

## 3. Build

```bash
docker compose build
```

## 4. Run the container with bash prompt:

```bash
docker compose run app bash
```

## 5. Init a new Deno 2 project:

```bash
deno init
```

## 6. Exit the container:

```bash
exit
```

## 7. Update `Dockerfile` and `compose.yml` with the contents of what you see in the latest commit of this repo.