# Projet Cloud Infra / Cloud Usage

## Déployer l'infrastructure

```bash
pip install python-heatclient python-openstackclient
source IAI3_08_TP-openrc.sh
openstack stack create -t template.yaml -e env.yaml --wait my_stack
```

Pour mettre à jour l'infrastructure :

```bash
openstack stack update -t template.yaml -e env.yaml --wait my_stack
```

Pour supprimer l'infrastructure :

```bash
openstack stack delete my_stack
```

## Interagir avec l'infrastructure

```bash
# Récuperer l'IP des VMs
openstack server list
# Lister les stacks
openstack stack list
# Lister les ressources d'une stack
openstack stack resource list my_stack
```

Se connecter à la VM frontend :

```bash
ssh-keygen -R <IP> # Supprimer l'ancienne clé
ssh frontend@<IP> # Mot de passe : password
```