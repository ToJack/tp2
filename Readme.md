# TP 2 : Docker/Kubernetes

## Instructions
Le TP s'appuie sur [un autre repo Github](https://github.com/cours-ece/simple-java-hello-world).
Les réponses aux questions posées dans cet énoncé sont attendues dans un fichier **answers.md** situé dans le repo mentionné ci-dessus.

Le TP doit être réalisé individuellement

## Rappels
* installer l'auto completion
* doc docker
* doc docker-compose
* doc kubernetes

### Docker
* Concepts
  * Building
  * Shipping
  * Running
* [Docker doc reference](https://docs.docker.com/reference/)
  * Dockerfile
  * docker-compose.yml
  * command line 

### Kubernetes
* Orchestrateur
* Ressources
* Kind
  * Node
  * Pods
  * Service
  * Namespace
  * Secret
* Probes
* AKS

### Ce qu'on ne va pas voir
* Logging
* Monitoring
* Alerting
* Rolling update - Pas sur pour celui la
* Helm
* Service Mesh

### Gitflow
![Gitflow diagram](https://stxnext.com/media/filer_public_thumbnails/filer_public/d4/41/d4414c91-483b-4904-9c1b-fc92c899678c/gitflow.png__1011x520_q85_crop_subsampling-2_upscale.png "Gitflow diagram")


## 0 : Description du projet
Tout au lond de ce tp, nous allons nous baser sur le projet situé dans le répertoire app de ce repo. Cette application est composée d'un front qui fait essentiellement office de passe-plat vers le back qui lui réalise les actions.
L'application renvoie différentes informations sur:
* les hostname des back et front
* l'url appelée
* l'heure d'appel
* l'environement dans lequel l'app à été déployée

L'application peut être requêtée sur :
* n'importe quelle path
* ou sur le path /write

Un appel sur le path /write, engendrera une écriture de l'argument passé en paramètre dans un fichier de log situé dans le container back.

## 1 : Docker


* Faire une pull request comme d'hab + donner un nombre à chaque personnes / table

### 1.1 : 

* Ecrire un dockerfile
* Build
* Créer un compte sur docker hub
* Ship
* Run
* Run with parameter (port, interactive, 

## 2 : Docker Compose
- link between app
- volume, network
- named volume, named network
- up, down, logs (-f), -d, 
- --scale worker=2 (to 10 after)
each time, see logs 

## 3 : Kubernetes

### 2.0 : Configurer Kubernetes pour se connecter au cluster
Diviser la classe en 7 groupes de 4 personnes, puis attribuer un chiffre de 1 à 7 à chaque groupe.
Dans la suite de la consigne du tp, le nombre qui vous sera attribué sera nommé {NB}.

* [Installer kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-binary-using-curl)
* [Configurer Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/#configure-kubectl) en utilisant le fichier situé dans kube/config.zip
```bash
cd kube
unzip config.zip
# Le mot de passe est au tableau
```
* [Configurer l'autocompletion](https://kubernetes.io/docs/tasks/tools/install-kubectl/#enabling-shell-autocompletion)

* Configurer le cluster à pointer
```bash
kubectl config use-context ece{NB}
```

* Vérifier que la configuration fonctionne correctement
```bash
```

* connect to kube cluster
* list env
* list node / get system info / os

### 2.1 : Naviguer dans l'aide de Kubernetes

### 2.X : Idée en vrac
```bash
# Récupérer les infos du cluster
kubectl cluster-info
# Lister les nodes
kubectl get node
# Récupérer l'OS et le kernel de chaque noeud
kubectl get node -o wide
# Lister les pods
kubectl get pod
```

* list pods
* créer fichier conf yaml
* déployer pod
* déployer service
* a chaque fois, lister les objets qui ont été crées