# Consulting Cloud pour PME — Énoncé simplifié

## Contexte

Vous êtes consultant chez **TechConseil**. Votre client **MediCare+** (PME de services de santé) veut moderniser son IT. L’infrastructure est 100% on‑premises et l’équipe est peu à l’aise avec le cloud.

Votre mission : **proposer une stratégie cloud simple, cohérente et réaliste**.

---

## Le client en bref

- 50 employés, siège à Lyon, agences à Marseille et Paris
- Application métier interne (PHP/MySQL), critique pour l’activité
- Site web vitrine WordPress
- Données sensibles mais **pas** de dossiers médicaux complets
- Un administrateur système à mi‑temps

---

## Infrastructure actuelle (résumé)

- Active Directory + DNS/DHCP sur un serveur Windows
- Application métier + base MySQL + fichiers sur un serveur Windows
- Site web sur un petit serveur Linux
- NAS + sauvegardes manuelles
- VPN inter‑sites

Coût annuel estimé : **~46 000 €**

---

## Problèmes constatés

- Coûts élevés et matériel à renouveler
- Disponibilité limitée, sauvegardes manuelles
- Accès distant difficile pour le télétravail
- Montée en charge compliquée
- RGPD pas assez cadré

---

## Objectifs du client

- Réduire les coûts et la maintenance
- Améliorer disponibilité et collaboration
- Sécuriser et cadrer la conformité RGPD
- Préparer la croissance

---

## Votre mission (livrable attendu)

Vous remettez **un document de recommandation**. Pas besoin d’un pavé : **2 à 3 pages suffisent** si c’est clair.

Le document contient :

### 1. Architecture cible (le cœur du travail)

Pour chaque composant, proposez une cible simple : On‑prem, IaaS, PaaS ou SaaS, avec le provider et la justification.

| Composant | Proposition | Modèle | Provider | Justification courte |
|---|---|---|---|---|
| Identités |  |  |  |  |
| Messagerie + bureautique |  |  |  |  |
| Fichiers partagés |  |  |  |  |
| App métier |  |  |  |  |
| Base de données |  |  |  |  |
| Sauvegardes |  |  |  |  |
| Site web |  |  |  |  |

Ajoutez un **schéma simple** (même à la main) : utilisateurs → services principaux → données.

### 2. Choix du provider

Comparez **2 ou 3 providers** (Azure, AWS, OVHcloud, etc.).

| Critère | Azure | AWS | OVHcloud |
|---|---|---|---|
| Localisation France |  |  |  |
| Services managés (PaaS) |  |  |  |
| Coût estimé |  |  |  |
| Support / simplicité |  |  |  |

Concluez en 4 ou 5 lignes : **le provider retenu et pourquoi**.

### 3. Estimation budgétaire (ordre de grandeur)

Donnez une estimation mensuelle **globale** (pas besoin d’être exact) et expliquez vos hypothèses.

### 4. Points d’attention

Listez 3 à 5 risques majeurs et comment vous les réduisez (ex : migration, sécurité, dépendance fournisseur).

---

## Conseils

- Restez simples et cohérents.
- Mieux vaut une solution sobre et justifiée qu’un catalogue de services.
- Si vous manquez de temps, priorisez l’architecture et le choix du provider.

---

---
---

# Stratégie de Modernisation Cloud — MediCare+

Ce document présente les options stratégiques pour la modernisation de l'infrastructure IT de MediCare+.

---

## 1. Architecture cible et Budgets détaillés

Voici les cinq nuances de Cloud conçues pour répondre aux besoins de flexibilité et de sécurité de l'entreprise.

### Option A : L'Harmonie Microsoft (Azure)
*Le choix du confort absolu. Tout est intégré, sécurisé et familier.*

| Composant | Proposition | Modèle | Provider | Justification |
| :--- | :--- | :--- | :--- | :--- |
| **Identités** | Entra ID | SaaS | Azure | Liaison native avec Windows. |
| **Bureautique** | M365 Business Premium | SaaS | Microsoft | Le standard pour 50 collaborateurs. |
| **Fichiers** | SharePoint / OneDrive | SaaS | Microsoft | Supprime le NAS, accès partout. |
| **App métier** | Azure App Service | PaaS | Azure | Pas d'OS à gérer, idéal pour PHP. |
| **Base de données** | Azure DB for MySQL | PaaS | Azure | Sauvegardes et patchs automatiques. |
| **Sauvegardes** | Azure Backup | PaaS | Azure | Protection contre les ransomwares. |
| **Site web** | Azure App Service | PaaS | Azure | Performance et isolation. |

**Estimation Budgétaire Mensuelle (Azure)**
* **Licences (50 u) :** 1 030 € (M365 Business Premium)
* **Hébergement & Services :** 375 € (App Service, MySQL, VPN)
* **TOTAL : 1 405 € / mois**

---

### Option B : La Puissance Industrielle (AWS)
*Pour une infrastructure modulaire, robuste et prête à encaisser la croissance.*

| Composant | Proposition | Modèle | Provider | Justification |
| :--- | :--- | :--- | :--- | :--- |
| **Identités** | AWS Identity Center | PaaS | AWS | Sécurité granulaire. |
| **Bureautique** | M365 (via direct) | SaaS | Microsoft | On garde les outils habituels. |
| **Fichiers** | Amazon S3 / WorkDocs | PaaS | AWS | Stockage virtuellement infini. |
| **App métier** | AWS Elastic Beanstalk | PaaS | AWS | Déploiement PHP automatisé. |
| **Base de données** | Amazon RDS MySQL | PaaS | AWS | Le standard des bases gérées. |
| **Sauvegardes** | AWS Backup | PaaS | AWS | Politique de rétention centralisée. |
| **Site web** | AWS Amplify | PaaS | AWS | Déploiement rapide pour WordPress. |

**Estimation Budgétaire Mensuelle (AWS)**
* **Licences (50 u) :** 1 030 € (M365 acquis séparément)
* **Hébergement & Services :** 245 € (EC2, RDS, NAT Gateway)
* **TOTAL : 1 275 € / mois**

---

### Option C : L'Agilité Collaborative (Google Cloud - GCP)
*Le choix de la légèreté et du travail en temps réel. Un parfum de modernité.*

| Composant | Proposition | Modèle | Provider | Justification |
| :--- | :--- | :--- | :--- | :--- |
| **Identités** | Cloud Identity | SaaS | Google | Gestion fluide via l'écosystème Google. |
| **Bureautique** | Workspace Bus. Std | SaaS | Google | Collaboration inégalée (Docs/Drive). |
| **Fichiers** | Google Drive (Shared) | SaaS | Google | Recherche documentaire surpuissante. |
| **App métier** | App Engine | PaaS | Google | "Zero-config" pour le code PHP. |
| **Base de données** | Cloud SQL for MySQL | PaaS | Google | Interface intuitive et performante. |
| **Sauvegardes** | Cloud Storage | PaaS | Google | Archivage sécurisé à prix dérisoire. |
| **Site web** | Cloud Run | PaaS | Google | Agilité maximale pour WordPress. |

**Estimation Budgétaire Mensuelle (GCP)**
* **Licences (50 u) :** 575 € (Workspace Business Standard)
* **Hébergement & Services :** 165 € (SQL, App Engine, Réseau)
* **TOTAL : 740 € / mois**

---

### Option D : La Souveraineté (Proxmox / Open Source)
*Pour ceux qui veulent être les seuls maîtres à bord, avec un budget d'artisan.*

| Composant | Proposition | Modèle | Provider | Justification |
| :--- | :--- | :--- | :--- | :--- |
| **Identités** | Keycloak | IaaS | Proxmox | Le standard Open Source (IAM). |
| **Bureautique** | M365 Business Basic | SaaS | Microsoft | Mail pro (Web) à prix réduit. |
| **Fichiers** | Nextcloud | IaaS | Proxmox | Le Cloud privé par excellence. |
| **App métier** | VM Linux (Debian) | IaaS | Proxmox | Environnement PHP sur mesure. |
| **Base de données** | MySQL (sur VM) | IaaS | Proxmox | Performance brute sans surcoût. |
| **Sauvegardes** | Proxmox Backup Serv. | IaaS | Proxmox | Sauvegardes locales et déportées. |
| **Site web** | VM WordPress | IaaS | Proxmox | Isolation complète du site vitrine. |

**Estimation Budgétaire Mensuelle (Proxmox)**
* **Licences (50 u) :** 280 € (M365 Business Basic)
* **Hébergement :** 120 € (Serveur dédié, IP, Backup)
* **TOTAL : 400 € / mois**

---

### Option E : La Recette "MIX" (L'Optimisation Consultante)
*Mélange de la sérénité du mail Microsoft et de l'économie du VPS français.*

| Composant | Proposition | Modèle | Provider | Justification |
| :--- | :--- | :--- | :--- | :--- |
| **Identités** | M365 Identity | SaaS | Microsoft | Sécurité des comptes gérée par MS. |
| **Bureautique** | M365 Business Basic | SaaS | Microsoft | Le mail pro officiel (Teams/Outlook). |
| **Fichiers** | OneDrive / SharePoint | SaaS | Microsoft | Inclus dans les licences bureautiques. |
| **App métier** | Serveur VPS | IaaS | OVH/Scaleway | Serveur virtuel puissant et économique. |
| **Base de données** | MySQL (sur VPS) | IaaS | OVH/Scaleway | Installée sur le même serveur. |
| **Sauvegardes** | Stockage S3 | PaaS | AWS/Azure | Externalisation de sécurité. |
| **Site web** | VPS (Conteneur) | IaaS | OVH/Scaleway | WordPress isolé sur le même VPS. |

**Estimation Budgétaire Mensuelle (Solution MIX)**
* **Licences (50 u) :** 280 € (M365 Business Basic)
* **Hébergement :** 60 € (Gros VPS + Backup distant)
* **TOTAL : 340 € / mois**

---

## 2. Comparaison des Providers

| Critère | Azure | AWS | GCP | OVH (Mix/Proxmox) |
| :--- | :--- | :--- | :--- | :--- |
| **Localisation France** | Oui | Oui | Oui | Oui (Souverain) |
| **Services managés** | Très complets | Industriels | Innovants | Basiques |
| **Coût estimé** | Élevé | Moyen | Modéré | **Très Faible** |
| **Simplicité** | Excellente | Complexe | Intuitive | Expert |

---

---

## Synthèse des Providers : Forces et Faiblesses pour MediCare+

Plutôt que d'imposer un choix unique, voici une analyse des parfums et des aspérités de chaque route possible pour moderniser votre IT.

### 1. Microsoft Azure
Le choix de la **continuité et du confort**. Pour une structure comme MediCare+ déjà imprégnée de l'univers Windows, Azure est une extension naturelle.

* **Forces :**
    * **Intégration native :** Liaison parfaite entre les identités (Entra ID) et les outils de travail Microsoft 365.
    * **Sécurité intégrée :** Les solutions de sauvegarde et de protection (Azure Backup) sont natives et s'activent en quelques clics.
    * **Écosystème connu :** Moins de dépaysement pour l'administrateur système actuel, facilitant la gestion à mi-temps.
* **Faiblesses :**
    * **Coût Premium :** C’est l’une des options les plus onéreuses, pesant lourdement sur le budget annuel.
    * **Éviction (Lock-in) :** Une fois l'infrastructure totalement imbriquée chez Microsoft, la migration vers un autre fournisseur devient un défi complexe.
    * **Complexité de l'interface :** La console Azure peut sembler labyrinthique pour des besoins simples de PME.

---

### 2. AWS (Amazon Web Services)
La **machine de guerre** du Cloud. Idéal si MediCare+ prévoit une croissance technologique forte et a besoin d'une précision chirurgicale.

* **Forces :**
    * **Granularité totale :** Chaque service peut être configuré au millimètre près selon vos besoins spécifiques.
    * **Catalogue immense :** Des milliers de services disponibles pour préparer toute croissance future.
    * **Fiabilité historique :** Une infrastructure éprouvée par les plus grands acteurs mondiaux.
* **Faiblesses :**
    * **Complexité technique :** L'interface est "sèche" et demande une expertise pointue, ce qui peut saturer un admin à mi-temps.
    * **Coûts imprévisibles :** Attention aux frais de transfert de données et de passerelles réseau qui peuvent faire varier la facture mensuelle.
    * **Accompagnement :** Demande un investissement temps important pour maîtriser les concepts de sécurité propres à Amazon.

---

### 3. Google Cloud (GCP)
Le Cloud **agile et visionnaire**. C'est l'option de la fluidité, centrée sur la collaboration moderne et l'intelligence des flux.

* **Forces :**
    * **Simplicité d'usage :** L'interface est sans doute la plus claire et la plus intuitive des géants du Cloud.
    * **Collaboration reine :** L'écosystème Workspace offre une expérience de travail en temps réel inégalée.
    * **Tarification incitative :** Remises automatiques pour l'utilisation prolongée des serveurs, sans engagement complexe.
* **Faiblesses :**
    * **Héritage Entreprise :** Parfois perçu comme moins complet que Microsoft pour les applications Windows très spécifiques.
    * **Réseau d'experts :** Moins d'intégrateurs spécialisés disponibles sur le marché français par rapport à Azure.

---

### 4. Solution Mixte / Proxmox (OVHcloud)
Le choix de la **souveraineté et de l'économie**. On revient à une informatique tactile et locale, très prisée pour la maîtrise des coûts.

* **Forces :**
    * **Coût imbattable :** On ne paie que le matériel physique, ce qui réduit drastiquement les frais fixes.
    * **Souveraineté (RGPD) :** Données stockées en France chez un hébergeur européen, simplifiant la conformité.
    * **Liberté absolue :** Vous n'êtes lié à aucun contrat de licence propriétaire pour l'infrastructure.
* **Faiblesses :**
    * **Charge mentale :** L'administrateur est responsable de tout : mises à jour de sécurité, monitoring et pannes matérielles.
    * **Risque de continuité :** Si l'administrateur quitte l'entreprise, la connaissance de cette installation sur-mesure est difficile à remplacer.
    * **Résilience manuelle :** La haute disponibilité n'est pas "native" ; elle doit être construite et testée manuellement par vos soins.

---

> **Note du consultant :**
> Le choix final pour **MediCare+** dépendra de votre priorité absolue : la **tranquillité d'esprit** (Azure), la **souplesse collaborative** (GCP), la **précision industrielle** (AWS) ou la **liberté budgétaire** (Solution Mix). Chaque option possède son propre charme, mais aussi ses propres exigences.

## 3. Points d'attention (Risques)

1. **Migration :** Risque de coupure lors du transfert. 
   * *Solution :* Maintenir un double hébergement pendant 15 jours pour tester la stabilité.
2. **Sécurité :** Le télétravail multiplie les points d'entrée. 
   * *Solution :* Authentification Multi-Facteurs (MFA) obligatoire pour tous les accès.
3. **Compétences :** Le mode "Mix" ou "Proxmox" demande plus de technicité. 
   * *Solution :* Rédaction d'une documentation rigoureuse des procédures de relance.

---

* **SaaS (Software as a Service) :** Location d'un logiciel prêt à l'emploi. Rien à installer (ex: Microsoft 365).
* **PaaS (Platform as a Service) :** Plateforme prête à accueillir votre code. Le fournisseur gère la maintenance du serveur.
* **IaaS (Infrastructure as a Service) :** Location de composants "nus". Vous construisez tout votre système à l'intérieur.
* **VPS (Virtual Private Server) :** Serveur virtuel privé. Un appartement privé dans un grand immeuble de serveurs : économique et flexible.
* **On-Premises :** Serveurs physiques installés localement dans vos bureaux (ex: à Lyon).

---
