# traefikfork3s
Traefik à déployer sur un cluster K3S

Installation de K3S sans Traefik : 

apt update -y 

apt upgrade -y 

apt install curl

curl -sfL https://get.k3s.io | sh -s - --no-deploy=traefik

Dans le fichier ConfigMap.yaml, pensez à remplacer les champs d'adresse e-mail par votre adresse e-mail

Une fois dans le dossier, pour lancer la création de traefik et des ingressroute, tapez la commande :

kubctl apply -f nom-de-votre-dossier-contenant-les-fichiers

Pour vérifier les services sont bien lancés, tapez :

kubctl get services --namespace kube-system

Pour vérifier les pods, tapez :

kubctl get pods --namespace kube-system

Pour avoir les logs de votre traefik 

kubetcl logs nom_de_votre_pods --namespace kube-system 

Pour accèder à l'interface traefik, dans votre navigateur, tapez :

http://traefik.yourdomain.com 

L'accès est proteger par un login/mot de passe qui se trouve dans le fichier Secret.yaml

