# Procédure de Maintenance et Mises à Jour - InfraReady

## 1. Maintenance Automatise Linux (LINUX01 & OPS01)

Les mises à jour des serveurs Linux sont automatisées à l'aide d'Ansible.

### Précautions avant exécution :
- Réaliser un snapshot VMware de la VM `LINUX01` avant toute mise à jour majeure.
- Vérifier qu'aucun traitement critique n'est en cours.

### Exécution du playbook :
```bash
ansible-playbook -i inventory/hosts.yml playbooks/maintenance.yml
