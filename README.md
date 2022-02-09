Trying to learn how to use k8s using Digital Ocean (DO)

This is a simple flask app that show the hostname. *You could run everything straight from the k8s or helm folders*

I made 3 folders:
- Docker: just the files to make a containerized python app
- K8: added code to get docker file in the cluster
- Helm: (passed linter but not tested) moved k8 to use helm charts

Following the video [here](https://www.digitalocean.com/community/tech_talks/getting-started-with-kubernetes-on-digitalocean)

## Steps
1. Setup container registry on DO
2. build image with `docker build -t <registryUrl>/<imageName>:<tag> .`
2. push image to registry with `docker push <registryUrl>/<imageName>:<tag>`
3. create k8s cluster with `doctl kubernetes cluster create <name> --count 1`
4. Connect the two from the container registry settings
5. add `deployment.yaml` file with `kubectl create -f deployment.yaml`
6. add `service.yaml` file with `kubectl create -f service.yaml`