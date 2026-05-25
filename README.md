# HELLOW WORLD@!!!!
This is a small Docker container you can use to test if your Ingress is working. We use it in our documentation.


## Run with Ingressive
This will be shown when you install the Ingressive Controller, just copy and paste the example Ingress demo.

## Run it for some other reason

Pull and run the published image from GHCR:

```sh
docker run --rm -p 8080:80 ghcr.io/ingressive-cloud/hello-world:latest
```

Then open http://localhost:8080.

Any path works — nginx falls back to `index.html` for every request, so `http://localhost:8080/anything/here` serves the same page.

To run a specific commit instead of `latest`:

```sh
docker run --rm -p 8080:80 ghcr.io/ingressive-cloud/hello-world:sha-<commit-sha>
```

## Run with Docker Compose

```yaml
services:
  hello-world:
    image: ghcr.io/ingressive-cloud/hello-world:latest
    ports:
      - "8080:80"
```

Save as `compose.yaml` and run:

```sh
docker compose up
```

## Build locally

```sh
docker build -t hello-world .
docker run --rm -p 8080:80 hello-world
```

