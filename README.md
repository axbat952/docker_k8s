# docker_k8s
ESIEE-IT

# ip Docker
172.18.112.1

# Docker commandes

Docker build -t <tag de l'image > . (construction de l'image)

docker run -d -p 8080:80 axbat952/nginx_esiee:v3 (démarrage du container en mode démon)

docker run -it -p 8080:8080 <tag de l'image > /bin/bash (démarrage du container en mode interactif)

docker run -it -p 8080:8080 <tag de l'image > /bin/sh -c "ls -l && pwd && ls -l /usr/src/app" 

docker run -v <répertoire source> :<répertoire destination> <tag de l'image > (démarrage du container avec un répertoire partagé)

docker run -v ${PWD}:/usr/share/nginx/html -d -p 8880:80 axbat952/nginx_esiee:v5 (démarrage du container avec un répertoire partagé)

docker tag nginx_perso axbat952/nginx_esiee:v1 (tag de l'image)

docker push <tag de l'image > (envoi de l'image sur le hub)

docker pull <tag de l'image > (récupération de l'image depuis le hub)

docker images (liste des images)

docker ps (liste des containers en cours d'exécution)

docker ps -a (liste des containers en cours d'exécution et arrêtés)

docker stop <id du container> (arrêt du container)

docker rm <id du container> (suppression du container)

docker rmi <id de l'image> (suppression de l'image)

# Construction Dockerfile:
From : <image de base> (ex: ubuntu, debian, centos, nginx, node, python, php, mysql, postgres, redis, mongo, tomcat, jenkins, ...)

Maintainer : <nom de l'auteur> (optionnel)

Env : <variable d'environnement> (optionnel)

Run : <commande à exécuter> (ex: apt-get update, apt-get install -y <package>, ...)

Copy : <fichier source> <fichier destination> (ex: index.html /usr/share/nginx/html/index.html)

Expose : <port> (ex: 80, 8080, 3306, 5432, 6379, 27017, 8080, 8081, ...)

Workdir : <répertoire de travail> (équivalent cd <répertoire de travail>) (ex: /usr/share/nginx/html)

Entrypoint : <commande à exécuter> (ex: nginx, node, python, php, mysql, postgres, redis, mongo, tomcat, jenkins, ...)

Cmd : <commande à exécuter> 


# Docker-compose commandes

docker-compose up (démarrage des containers)

docker-compose up -d (démarrage des containers en mode démon)

docker-compose up --build (reconstruction des images et démarrage des containers)

docker-compose up --build -d (reconstruction des images et démarrage des containers en mode démon)

docker-compose down (arrêt des containers)

docker-compose ps (liste des containers en cours d'exécution)

docker-compose logs (affichage des logs des containers)

docker-compose logs -f (affichage des logs des containers en mode suivi)

docker-compose logs -f <nom du service> (affichage des logs du service en mode suivi)

docker-compose exec <nom du service> /bin/bash (connexion au container en mode interactif)



# Kubernetes commandes

kubectl create -f <fichier de configuration>

kubectl get pods (liste des pods)

kubectl get services (liste des services)

kubectl get deployments (liste des deployments)

kubectl get nodes (liste des nodes)

kubectl get all (liste de tous les éléments)

kubectl describe pod <nom du pod> (détails du pod)

kubectl describe service <nom du service> (détails du service)

kubectl describe deployment <nom du deployment> (détails du deployment)

kubectl describe node <nom du node> (détails du node)

kubectl delete pod <nom du pod> (suppression du pod)

kubectl delete service <nom du service> (suppression du service)

kubectl delete deployment <nom du deployment> (suppression du deployment)

kubectl delete node <nom du node> (suppression du node)

kubectl delete all --all (suppression de tous les éléments)

kubectl logs <nom du pod> (affichage des logs du pod)

kubectl exec -it <nom du pod> /bin/bash (connexion au pod en mode interactif)

kubectl apply -f <fichier de configuration> (création ou mise à jour d'un élément)

kubectl scale --replicas=3 deployment/<nom du deployment> (mise à l'échelle du deployment)

kubectl expose deployment <nom du deployment> --type=NodePort (exposition du deployment)

kubectl expose deployment <nom du deployment> --type=LoadBalancer

kubectl expose deployment <nom du deployment> --type=ClusterIP

kubectl expose deployment <nom du deployment> --type=ExternalName

kubectl expose deployment <nom du deployment> --type=NodePort --port=8080 --target-port=8080 (exposition du deployment sur le port 8080)

kubectl expose deployment <nom du deployment> --type=NodePort --port=8080 --target-port=8080 --name=<nom du service> (exposition du deployment sur le port 8080 avec un nom de service)

