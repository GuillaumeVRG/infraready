# Administration Linux - LINUX01 (Section 6.3)

## 1. Service Applicatif (Serveur Web Nginx)
- **Installation :** Automatisée via le playbook Ansible (`playbooks/linux.yml`).
- **Validation :** Le service Nginx écoute sur le port 80 et est actif (`systemctl status nginx`).

## 2. Gestion du Stockage et Disque Virtuel
- **Disque de test :** Ajout d'un disque virtuel additionnel sur la VM `LINUX01`.
- **Système de fichiers :** Formatage en `ext4`.
- **Point de montage :** Monté de manière persistante sur `/mnt/data` via une entrée dans `/etc/fstab`.

## 3. Journaux Système (Logs)
- Consultation des journaux via `journalctl` :
  - Services : `journalctl -u nginx`
  - Système : `journalctl -e`
