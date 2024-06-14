```
==========================================================================================
 
 ___                              ____            _               ____  _           
|_ _|_ __ ___   __ _  __ _  ___  |  _ \ __ _  ___| | _____ _ __  |  _ \| |_   _ ___ 
 | || '_ ` _ \ / _` |/ _` |/ _ \ | |_) / _` |/ __| |/ / _ \ '__| | |_) | | | | / __|
 | || | | | | | (_| | (_| |  __/ |  __/ (_| | (__|   <  __/ |    |  __/| | |_| \__ \
|___|_| |_| |_|\__,_|\__, |\___| |_|   \__,_|\___|_|\_\___|_|    |_|   |_|\__,_|___/
                     |___/                                                          

                                -= with / avec =-

▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
██ ▄▄ █ ▄▄▀█▀▄▀█ █▀█ ▄▄█ ▄▄▀███ ▄▄▀█ ▄▄▀█ ▄▀███▄▄ ▄▄█ ▄▄█ ▄▄▀█ ▄▄▀█ ▄▄▀█ ▄▄█▀▄▄▀█ ▄▄▀█ ▄▀▄ ██
██ ▀▀ █ ▀▀ █ █▀█ ▄▀█ ▄▄█ ▀▀▄███ ▀▀ █ ██ █ █ █████ ███ ▄▄█ ▀▀▄█ ▀▀▄█ ▀▀ █ ▄██ ██ █ ▀▀▄█ █▄█ ██
██ ████▄██▄██▄██▄█▄█▄▄▄█▄█▄▄███▄██▄█▄██▄█▄▄██████ ███▄▄▄█▄█▄▄█▄█▄▄█▄██▄█▄████▄▄██▄█▄▄█▄███▄██
▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀
===============================================================================================
```
                              In French and English
___
# __English__

## Background
This is a ["infrastructure as code"](https://www.freecodecamp.org/news/infrastructure-as-code-basics/) tool I developed for universal image and container deployment. It supports geospatial (via GDAL) and machine learning (NVIDIA) projects, regardless of the required container type (OCI, like Docker, or Singularity).

Pre-made images from HPC/cloud providers often require customization. This tool offers a simpler approach using bash scripts.

While initially designed for the Digital Research Alliance of Canada (DRAC), this project is easily adaptable to other environments. I hope this proves useful for others! Please feel free to reach out if you encounter any issues.

## Tools for creating/deploying to HPC and Cloud Computing Environments !

This project exists to make it easier to...
1) create a tailored virtual machine using familiar tools like bash, or docker-compose, and 
2) provision a cloud instance and deploy the VM to a cloud. The cloud/HPC combo used in this project both needed .SIF containers.

The current example (see the packer folder) creates VMs capable of running NVIDIA drivers.

## Makefile
Please note that this project uses a `Makefile`. This is how you can execute all of your commands. You may want to open that file up and see what commands are available.

## Setup

### Part One

Please complete the following steps:

If using a university system like the Digital Research Alliance of Canada (DRAC):
- Contact the DRAC's Cloud Team and ask for a Cloud Environment (a faculty member needs to do this)
- Contact the Cloud Team and ask for a "GPU Capable" image "flavor"

If you have commerical access (AWS, Digital Ocean, etc...)
- Install Terraform: `https://www.terraform.io/downloads`
- Install Packer: https://learn.hashicorp.com/tutorials/packer/get-started-install-cli
- Open the Web console for DRAC's cloud environment (https://arbutus.cloud.computecanada.ca).
- Download your `openrc.sh` from your OpenStack provider's web console to the <i>project root</i>.
- Optionally install the OpenStack Command Line Interface (CLI): https://docs.openstack.org/newton/user-guide/common/cli-install-openstack-command-line-clients.html

### Part Two (Terraform)

Look at the `README.md` file located in the `terraform` folder to see how to set that aspect up.

### Part Three (Packer)

Look at the `README.md` file located in the `packer` folder to see how to set that aspect up.

### Part Four (SSH)

Once you've run Packer to create your VM, and then deployed it via Terraform, you can connect to it using `ssh -i ~/.ssh/username@arbutus.computecanada.ca  ubuntu@111.12.95.121`

- The `-i` specifies the ssh key in your `.ssh` folder
- the `ubuntu` is a stand-in for the VM's ssh username (depending on on the OS flavor)

## Appendix:

- See the `https://docs.alliancecan.ca/wiki/Cloud` for more info on how to interact with this cloud.
- See the https://texteditor.com/multiline-text-art/ for the cool ascii font techniques

___
# __Français__

## Arrière-plan
Il s'agit d'un outil que j'ai développé pour déployer universellement des images et des conteneurs, quel que soit le type de conteneur requis (OCI, comme docker-ish ou Singularity). Au lieu d'avoir besoin d'apprendre un autre système de modèles d'images, vous pouvez créer vos environnements via des scripts bash et les déployer sur toutes les plateformes.

Bien que je l'ai conçu à l'origine pour la Digital Research Alliance of Canada (DRAC), ce projet est également facilement adaptable à d'autres environnements. J'espère que cela sera utile à d'autres aussi. Veuillez nous contacter si vous rencontrez des problèmes.

## Outils de création/déploiement sur des environnements HPC et Cloud Computing !

Ce projet existe pour faciliter...
1) créer une machine virtuelle sur mesure à l'aide d'outils familiers comme bash ou docker-compose, et
2) provisionnez une instance cloud et déployez la VM sur un cloud. Le combo cloud/HPC utilisé dans ce projet nécessitait tous deux des conteneurs .SIF.

L'exemple actuel (voir le dossier packer) crée des VM capables d'exécuter des pilotes NVIDIA (pour GPU "virtuel").

## Makefile
Veuillez noter que ce projet utilise un « Makefile ». C'est ainsi que vous exécuterez toutes vos commandes. Vous souhaiterez peut-être ouvrir ce fichier et voir quelles commandes sont disponibles.

## Installation

### Partie un

Veuillez effectuer les étapes suivantes :

Si vous utilisez un système universitaire comme la Digital Research Alliance of Canada (DRAC) :
- Contacter l'Equipe Cloud de la DRAC et demander un Environnement Cloud (un membre du corps professoral doit le faire)
- Contactez l'équipe Cloud et demandez une "saveur" d'image "GPU Capable".

Si vous disposez d'un accès commercial (AWS, Digital Ocean, etc...)
- Installez Terraform : `https://www.terraform.io/downloads`
- Installer Packer : https://learn.hashicorp.com/tutorials/packer/get-started-install-cli
- Ouvrez la console Web de l'environnement cloud de la DRAC (https://arbutus.cloud.computecanada.ca).
- Téléchargez votre `openrc.sh` depuis la console Web de votre fournisseur OpenStack vers la <i>racine du projet</i>.
- Installez éventuellement l'interface de ligne de commande (CLI) OpenStack : https://docs.openstack.org/newton/user-guide/common/cli-install-openstack-command-line-clients.html

### Deuxième partie (Terraform)

Regardez le fichier `README.md` situé dans le dossier `terraform` pour voir comment configurer cet aspect.

### Troisième partie (Emballeur)

Regardez le fichier `README.md` situé dans le dossier `packer` pour voir comment configurer cet aspect.

### Quatrième partie (SSH)

Une fois que vous avez exécuté Packer pour créer votre VM, puis que vous l'avez déployé via Terraform, vous pouvez vous y connecter en utilisant `ssh -i ~/.ssh/username@arbutus.computecanada.ca ubuntu@111.12.95.121`

- Le `-i` spécifie la clé ssh dans votre dossier `.ssh`
- `ubuntu` remplace le nom d'utilisateur ssh de la VM (en fonction de la version du système d'exploitation)

## Annexe:

- Voir le `https://docs.alliancecan.ca/wiki/Cloud` pour plus d'informations sur la façon d'interagir avec ce cloud.
- Voir https://texteditor.com/multiline-text-art/ pour les techniques de police ascii sympas