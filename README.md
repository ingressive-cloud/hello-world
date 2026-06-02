# HELLOW WORLD@!!!!
This is a small Docker container you can use to test if your Ingress is working. We use it in our documentation.


## Run with Ingressive Kubernetes
This will be shown when you install the Ingressive Controller, click on the Demo App tab, and paste the generated YAML. 

## Run Docker image

Pull and run the published image from GHCR:

```sh
docker run --rm -p 8080:80 ghcr.io/ingressive-cloud/hello-world:latest
```

Then open http://localhost:8080.

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

## Run with Kubernetes - Manual

Install the Ingressive Controller on your Kubernetes cluster on the Ingressive Console. This will be shown as a demo app for you to try. 

If you really want to install manually: 

Clone the repo and change the domain name you wish to use. 
```bash
git clone https://github.com/ingressive-cloud/hello-world
cd hello-world 

nano kube.yaml # Edit your Ingress Hostname
kubectl apply -f kube.yaml

```

## Build locally

```sh
docker build -t hello-world .
docker run --rm -p 8080:80 hello-world
```

