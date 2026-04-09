# OKD Prod Nginx

This repository contains the OKD/OpenShift manifests for a small `nginx` "hello world" application.

It defines the resources needed to deploy the app in the `nginx-hello` namespace:

- `Namespace.yaml` creates the project/namespace
- `ConfigMap.yaml` provides the static `index.html` content served by nginx
- `Deployment.yaml` runs the unprivileged nginx container and mounts the HTML content
- `Service,.yaml` exposes the deployment internally on port 80
- `Route.yaml` exposes the service externally with OpenShift Route TLS settings

The manifests also include Argo CD sync-wave annotations so they can be applied in a sensible order during deployment.
