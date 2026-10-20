<div align="center">

# 🚀 InfraReady — Automatisation, Supervision & Sécurité SI
### Projet Fil Rouge - Administration Systèmes Linux & Windows (Bachelor 3 Cybersécurité)

<p align="center">
  <img src="https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white" alt="Ansible">
  <img src="https://img.shields.io/badge/Windows_Server-0078D6?style=for-the-badge&logo=windows&logoColor=white" alt="Windows Server">
  <img src="https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white" alt="Ubuntu">
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white" alt="Prometheus">
  <img src="https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white" alt="Grafana">
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white" alt="GitHub Actions">
</p>

</div>

---

## 📌 Présentation du Projet
**InfraReady** est une plateforme d'infrastructure virtualisée hybride (Linux / Windows) conçue pour standardiser les configurations, automatiser le déploiement et assurer la supervision proactive des services informatiques de l'entreprise.

Ce dépôt centralise l'ensemble des scripts, playbooks Ansible, configurations de supervision et documents techniques réalisés dans le cadre du projet.

---

## 🏗️ Architecture Technique
L'infrastructure repose sur un laboratoire virtualisé interconnecté sur le réseau local `192.168.50.0/24`[cite: 15] :

| Machine | Système d'Exploitation | Rôle Principal | Adresse IP |
| :--- | :--- | :--- | :--- |
| **OPS01** | Ubuntu Server 24.04 LTS | Contrôleur Ansible, Git, Prometheus & Grafana[cite: 15] | `192.168.50.30`[cite: 15] |
| **LINUX01** | Ubuntu Server 24.04 LTS | Services Linux, Node Exporter, Maintenance `apt`[cite: 15] | `192.168.50.20`[cite: 15] |
| **WIN-DC01** | Windows Server 2025 | Active Directory Domain Services (AD DS), DNS[cite: 15] | `192.168.50.10`[cite: 15] |

---

## 🔒 Sécurité & Gestion des Secrets
* **Ansible Vault :** Les identifiants sensibles et paramètres de connexion WinRM sont chiffrés (`group_vars/windows.yml`)[cite: 19, 20]. Aucun mot de passe en clair n'est présent sur le dépôt[cite: 20].
* **CI/CD :** Un workflow GitHub Actions (`.github/workflows/validate.yml`) valide automatiquement la syntaxe YAML et les playbooks à chaque `push`[cite: 16, 19].

---

## 📂 Structure du Dépôt
```text
infraready/
├── .github/workflows/     # Pipeline CI/CD (Validation syntaxique)
├── docs/                  # Documentation technique, procédures et incidents
├── group_vars/            # Variables chiffrées (Ansible Vault)
├── inventory/             # Inventaire dynamique/statique des hôtes
├── monitoring/            # Configurations Prometheus & Dashboards Grafana
├── playbooks/             # Playbooks Ansible (Linux, AD & Maintenance)
└── scripts/               # Scripts utilitaires d'administration
