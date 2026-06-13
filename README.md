# 🛡️ POC "Cyber Limited" : Conception & Durcissement d'une Infrastructure Sécurisée
> **Projet de Fin de Cycle | Sécurité Périmétrique & Défense en Profondeur**

## 📝 Présentation du Projet
L'objectif de ce Proof of Concept (POC) était de concevoir, déployer et sécuriser l'infrastructure complète d'une entreprise fictive nommée **Cyber Limited**. Ce projet met en œuvre une stratégie de défense en profondeur combinant filtrage réseau, détection d'intrusions et durcissement système (Hardening).

## 🏗️ Architecture du LAB (Virtualisation VMware)
L'infrastructure repose sur un réseau segmenté et isolé (VMnet2) comprenant 5 actifs majeurs :
*   **Passerelle de Sécurité** : Pare-feu **pfSense** assurant le filtrage et le routage sécurisé.
*   **Serveur de Services (Ubuntu)** : Hébergement de l'IDS **Snort** et des services critiques.
*   **Contrôleur de Domaine** : **Windows Server 2019** pour la gestion IAM.
*   **Endpoints** : Postes clients Windows 10 et Ubuntu pour la validation utilisateur.

## 🛠️ Réalisations Techniques & Sécurité

### 1. Filtrage & Pare-feu (pfSense)
*   **Segmentation Réseau** : Mise en place de règles de filtrage de paquets (Incoming/Outgoing) pour isoler le LAN du WAN.
*   **Contrôle ICMP** : Limitation des flux de diagnostic pour réduire la visibilité du réseau face à la reconnaissance externe.

### 2. Détection d'Intrusions (Snort IDS)
*   **Analyse en Temps Réel** : Installation et configuration de **Snort** sur la passerelle Ubuntu pour inspecter le trafic.
*   **Règles de Détection** : Création de règles personnalisées pour identifier les comportements suspects (ex: scan de ports, requêtes ICMP anormales).
*   **Validation** : Preuve de concept par génération d'alertes instantanées lors d'un test de pénétration simulé. <ref doc="Realisation-dun-POC (1).pdf" page="13">Alertes Snort</ref>

### 3. Durcissement des Systèmes (Hardening)
*   **Linux (Ubuntu)** : Activation du firewall applicatif **UFW** et mise en œuvre de **Fail2ban** pour contrer les attaques par force brute SSH. <ref doc="Realisation-dun-POC (1).pdf" page="18">Configuration Fail2ban</ref>
*   **Windows Server** : Déploiement de **GPO** (Group Policy Objects) pour restreindre les privilèges locaux et durcir la configuration du Pare-feu avancé.

## 🛡️ Tests de Sécurité (Pentest de Validation)
Pour certifier l'étanchéité de l'infrastructure, j'ai réalisé :
*   **Scans de vulnérabilités (Nmap)** : Confirmation de la fermeture des ports non essentiels.
*   **Attaques par force brute** : Validation du bannissement automatique par Fail2ban.
*   **Simulation DoS** : Test de résistance aux inondations de requêtes (Ping Flood).

## ✅ Résultats
*   Une infrastructure 100% opérationnelle et résiliente face aux vecteurs d'attaque courants.
*   Mise en place d'une visibilité totale sur les alertes réseau.
*   Production d'une documentation technique reproductible pour le déploiement sécurisé.

---
[📄 Consulter le Rapport Technique Complet (PDF)](./docs1/POC_CyberLimited_Franck_DEFFO.pdf)
