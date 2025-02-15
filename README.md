# Nginx Kubernetes Pod Deployment

This repository contains Kubernetes configuration files for deploying an Nginx web server as a multi-container Pod. The deployment features a custom `index.html` file fetched from a remote server, liveness probes for monitoring, and persistent log storage using `hostPath` volumes.

## Features

- **Custom `index.html`**: The Nginx server serves a custom `index.html` fetched by an init container from a remote repository
- **Liveness Probe**: Monitors the health of the Nginx container by checking the `/healthz` endpoint
- **Persistent Log Storage**: Nginx logs are stored persistently on the host machine using a `hostPath` volume

## Structure

- **Pod Configuration**: The main Kubernetes Pod configuration is defined in the YAML file, including init containers, volumes, and liveness probes
- **ConfigMap**: Stores the Nginx configuration, ensuring the server correctly serves the custom page and responds to health checks

## Files

- **nginx.yaml**: Default nginx pod
- **nginx2.yaml**: Nginx pod with custom html deployed on this github repo
- **nginx3.yaml**: Liveness probe addition, needed a config map to change nginx internal configuration
- **nginx4.yaml**: Volume addition to store nginx logs