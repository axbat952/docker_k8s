# docker_k8s
ESIEE-IT


# Docker commandes

Docker build -t <tag de l'image > .

docker run -it -p 8080:8080 <tag de l'image > /bin/bash

docker run -it -p 8080:8080 <tag de l'image > /bin/sh -c "ls -l && pwd && ls -l /usr/src/app"


# Construction Dockerfile:
From : <image de base>

Maintainer : <nom de l'auteur>

Env : <variable d'environnement>

Run : <commande à exécuter>

Copy : <fichier source> <fichier destination>

Expose : <port>

Workdir : <répertoire de travail> (équivalent cd <répertoire de travail>)

Entrypoint : <commande à exécuter>

Cmd : <commande à exécuter>


# Docker-compose commandes

docker-compose up

docker-compose up -d

docker-compose up --build

docker-compose up --build -d

docker-compose down

docker-compose ps

docker-compose logs

docker-compose logs -f

docker-compose logs -f <nom du service>

docker-compose exec <nom du service> /bin/bash



# Kubernetes commandes

kubectl create -f <fichier de configuration>

kubectl get pods

kubectl get services

kubectl get deployments

kubectl get nodes

kubectl get all

kubectl describe pod <nom du pod>

kubectl describe service <nom du service>

kubectl describe deployment <nom du deployment>

kubectl describe node <nom du node>

kubectl delete pod <nom du pod>

kubectl delete service <nom du service>

kubectl delete deployment <nom du deployment>

kubectl delete node <nom du node>

kubectl delete all

kubectl logs <nom du pod>

kubectl exec -it <nom du pod> /bin/bash

kubectl apply -f <fichier de configuration>

kubectl scale --replicas=3 deployment/<nom du deployment>

kubectl expose deployment <nom du deployment> --type=NodePort

kubectl expose deployment <nom du deployment> --type=LoadBalancer

kubectl expose deployment <nom du deployment> --type=ClusterIP

kubectl expose deployment <nom du deployment> --type=ExternalName

kubectl expose deployment <nom du deployment> --type=NodePort --port=8080 --target-port=8080

kubectl expose deployment <nom du deployment> --type=NodePort --port=8080 --target-port=8080 --name=<nom du service>

