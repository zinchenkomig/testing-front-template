# QuickStart
First things first you need pipx
```bash
sudo apt install pipx
```
Now you can install copier. We use it to make this template work.
```
pipx install copier
```
Now you can initialize your project.
```
mkdir myproject
cd myproject
copier copy https://github.com/zinchenkomig/base-users-template.git .
```
It will ask you to fill data for the project templates.
Now your template is good to go.

## Secrets for Github actions
- `KUBECONFIG` - copy it from the machine where your kuber is located and replace the 127.0.0.1 to the static IP of your kuber machine
- `DOCKER_USERNAME`
- `DOCKER_PASSWORD`

You also need to make a kubernetes secret with your docker credentials:
```
kubectl create secret docker-registry image-secrets --docker-server={{custom_container_registry}} --docker-username=<username> --docker-password=<password>
```