# NEXUS-SENTINEL-v1.0.0-AUDIT-DE-S-CURIT-SOUVERAIN
Rôle : Alternative fiable aux outils GitHub (CodeQL, Dependabot, Secret Scanning, Branch Protection, GitHub Actions). Philosophie: Multi-moteurs. Preuves > Affirmations. Zéro faux positif. Souverain. Auditable. Architecture: Ingestion -> Analyse (Multi-Moteurs) -> Cross-Check -> Rapport.
markdown

<div align="center">

<!-- Bannière SVG native (fonctionne sur GitHub) -->
<svg width="800" height="180" viewBox="0 0 800 180" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="bgGrad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" stop-color="#0a0a14"/>
      <stop offset="100%" stop-color="#05050a"/>
    </linearGradient>
    <linearGradient id="neonGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#00ff88">
        <animate attributeName="stop-color" values="#00ff88;#00e5ff;#00ff88" dur="4s" repeatCount="indefinite"/>
      </stop>
      <stop offset="100%" stop-color="#00e5ff">
        <animate attributeName="stop-color" values="#00e5ff;#00ff88;#00e5ff" dur="4s" repeatCount="indefinite"/>
      </stop>
    </linearGradient>
  </defs>

  <rect width="800" height="180" fill="url(#bgGrad)" rx="12"/>
  <rect x="1" y="1" width="798" height="178" fill="none" stroke="url(#neonGrad)" stroke-width="2" rx="11" opacity="0.5"/>

  <text x="400" y="80" text-anchor="middle" font-family="ui-monospace, monospace" font-size="42" font-weight="900" fill="url(#neonGrad)">
    NEXUS-SENTINEL
    <animate attributeName="opacity" values="1;0.85;1" dur="2s" repeatCount="indefinite"/>
  </text>
  <text x="400" y="120" text-anchor="middle" font-family="ui-monospace, monospace" font-size="14" fill="#8b9dc3" letter-spacing="4">
    AUDIT DE SÉCURITÉ SOUVERAIN
  </text>
  <text x="400" y="150" text-anchor="middle" font-family="ui-monospace, monospace" font-size="12" fill="#4a5878" letter-spacing="2">
    MULTI-MOTEURS · PREUVES > AFFIRMATIONS · ZÉRO FAUX POSITIF
  </text>
</svg>

<br/>

[![Version](https://img.shields.io/badge/version-1.0.0--OMEGA-00ff88?style=for-the-badge)](#)
[![Python](https://img.shields.io/badge/python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](#)
[![License](https://img.shields.io/badge/license-NEXUS--OPEN--3.0-ff00c8?style=for-the-badge)](#)
[![Status](https://img.shields.io/badge/status-OPERATIONAL-00e5ff?style=for-the-badge)](#)

<br/>

**L'alternative souveraine aux outils de sécurité GitHub.**
**Parce que CodeQL, Dependabot et compagnie ne sont pas des garanties.**

**[⚡ Installation](#-installation) · [🎯 Utilisation](#-utilisation) · [🏗️ Architecture](#️-architecture) · [📊 Ce que ça fait](#-ce-que-ça-fait) · [🔬 Preuves](#-preuves)**

</div>

---

## 🧬 Manifeste

> *« Le code est la seule souveraineté qui ne se délègue pas. »*

**NEXUS-SENTINEL** n'est pas un énième scanner de sécurité. C'est une réponse documentée à un constat simple : **les outils de sécurité natifs de GitHub ont des angles morts**, et ils ne les corrigent pas toujours.

Ce projet existe parce que :

- **CodeQL** a arrêté de détecter les secrets hardcodés en mai 2025.
- **Dependabot** ne vérifie pas la *reachability* et ne détecte pas les packages malveillants.
- **Secret Scanning** rate les secrets non conformes aux regex prédéfinies.
- **Branch Protection** a été contournable pendant 9 mois via `pull_request_target`.
- **GitHub Actions** est vulnérable aux injections de commandes (CVE-2025-49013, CVE-2025-55192).

**NEXUS-SENTINEL** ne remplace pas GitHub. Il comble les trous que GitHub ne bouche pas.

---

## ⚡ Installation

### Prérequis

| Outil | Version minimale | Rôle |
|-------|------------------|------|
| Python | 3.10+ | Runtime principal |
| Git | 2.30+ | Clonage des dépôts |
| Semgrep | 1.50+ | SAST multi-langages |
| Trivy | 0.40+ | Scan de vulnérabilités |
| Gitleaks | 8.0+ | Détection de secrets |
| Bandit | 1.7+ | Sécurité Python |

### Installation en 3 commandes

```bash
# 1. Cloner le dépôt
git clone https://github.com/Aissamohammedi88/NEXUS-SENTINEL.git
cd NEXUS-SENTINEL

# 2. Rendre le script exécutable
chmod +x nexus_sentinel.py

# 3. Installer les dépendances
python3 nexus_sentinel.py setup

C'est tout. Le script installe automatiquement Semgrep, Bandit et les librairies Python. Pour Trivy et Gitleaks, il t'indique les commandes d'installation officielles.
🎯 Utilisation
Audit complet d'un dépôt
bash

python3 nexus_sentinel.py audit https://github.com/user/repo

Sortie attendue :
text

═══════════════════════════════════════════════════════════════════════
🛡️ NEXUS-SENTINEL AUDIT v1.0.0
🎯 Cible : https://github.com/user/repo
═══════════════════════════════════════════════════════════════════════

📥 Ingestion de : https://github.com/user/repo
🔍 Analyse de la structure...
📊 847 fichiers de code détectés
🔧 Langages : python, javascript, yaml
⚙️ 3 workflows GitHub Actions
📦 2 fichiers de dépendances

🔬 Lancement de l'analyse SAST...
 → Semgrep en cours...
 → Bandit en cours...
 → Scan des secrets...

⚙️ Analyse de 3 workflow(s)...
📦 Analyse de 2 fichier(s) de dépendances...

🔄 Déduplication de 47 findings...
✅ 47 → 32 findings après déduplication

═══════════════════════════════════════════════════════════════════════
📊 RÉSUMÉ DE L'AUDIT
═══════════════════════════════════════════════════════════════════════
🎯 Cible : https://github.com/user/repo
⏱️ Durée : 42.31s
📁 Fichiers analysés : 847
🔍 Total findings : 32

 Sévérité      Nombre
 ─────────────────────
 CRITICAL         2
 HIGH             8
 MEDIUM          15
 LOW              7

═══════════════════════════════════════════════════════════════════════

Scan rapide (SAST uniquement)
bash

python3 nexus_sentinel.py scan ./mon-projet --sast-only

Format de sortie personnalisé
bash

python3 nexus_sentinel.py audit https://github.com/user/repo --format md

Formats disponibles : all (défaut), json, md, html.
Historique des audits
bash

python3 nexus_sentinel.py history --target https://github.com/user/repo

🏗️ Architecture
text

┌─────────────────────────────────────────────────────────────────────────┐
│                        NEXUS-SENTINEL CLI                              │
│                       (Python 3.10+)                                   │
└───────────────────────────────┬─────────────────────────────────────────┘
                                │
        ┌───────────────────────┼───────────────────────┐
        │                       │                       │
        ▼                       ▼                       ▼
┌───────────────┐       ┌───────────────┐       ┌───────────────┐
│  INGESTION    │       │   ANALYSE     │       │   RAPPORT     │
│               │       │  (Multi-      │       │  (Preuves)    │
│               │       │   Moteurs)    │       │               │
├───────────────┤       ├───────────────┤       ├───────────────┤
│ Git clone     │       │ Semgrep       │       │ JSON          │
│ API GitHub    │       │ Trivy         │       │ Markdown      │
│ Fichiers      │       │ Gitleaks      │       │ HTML          │
│ Workflows     │       │ Bandit        │       │ SARIF         │
└───────────────┘       │ Custom Rules  │       └───────────────┘
        │               └───────────────┘               │
        │                       │                       │
        │                       ▼                       │
        │               ┌───────────────┐               │
        │               │  CROSS-CHECK  │               │
        │               │  (Déduplication│              │
        │               │   + Priorisation)│            │
        │               └───────────────┘               │
        │                       │                       │
        └───────────────────────┼───────────────────────┘
                                ▼
                    ┌───────────────────┐
                    │   BASE SQLITE     │
                    │   - Audits        │
                    │   - Findings      │
                    │   - Régressions   │
                    └───────────────────┘

📊 Ce que ça fait
Détection de secrets
Pattern	Sévérité
AWS Access Key	CRITICAL
GitHub Token	CRITICAL
Slack Token	CRITICAL
Private Key	CRITICAL
Google API	CRITICAL
Stripe Key	CRITICAL
Analyse SAST
Moteur	Langages couverts
Semgrep	Python, JavaScript, Java, Go, Ruby, PHP, C, C++
Bandit	Python uniquement
Custom rules	Tous (via regex et patterns)
Analyse des workflows GitHub Actions
Règle	Sévérité
Injection de commandes (${{ github.event.* }} dans run:)	CRITICAL
pull_request_target + checkout de la PR	CRITICAL
permissions: write-all	HIGH
Secrets dans run:	HIGH
Aucune section permissions:	MEDIUM
Analyse des dépendances
Moteur	Formats supportés
Trivy	requirements.txt, package.json, Pipfile, poetry.lock, Gemfile, go.mod, pom.xml, Cargo.toml
Cross-check et déduplication

Chaque finding est comparé aux autres basés sur (fichier, ligne, catégorie). Si deux moteurs trouvent le même problème, le plus sévère est conservé. Zéro doublon.
Détection de régressions

Chaque audit est sauvegardé en base SQLite. Au prochain audit du même dépôt, le script compare et signale :

    Les nouveaux findings (régressions)

    Les findings corrigés (améliorations)

🔬 Preuves

NEXUS-SENTINEL est né d'un audit documenté des défaillances de GitHub. Voici les références :
Défaillance	Référence
CodeQL ne détecte plus les secrets hardcodés	Changelog GitHub
Détections non-monotones (21/171 CVE perdues)	arXiv:2605.09876
Dependabot ne fait pas de reachability	The Register
Secret Scanning rate le code source Java	Discussion #191555
Branch Protection contournée 9 mois	QuantCo
CVE-2025-49013 (injection commandes)	INCIBE
CVE-2025-55192 (code injection)	CIRCL
GHSL-2025-038 (contournement approbation)	SecurityLab
42.7% des workflows ont un token sur-privilégié	Mitiga.io
🎯 Philosophie

    Preuves > Affirmations. Chaque finding inclut la source, la ligne, le code, et une référence.

    Multi-moteurs. Ne jamais dépendre d'un seul outil. Croiser les résultats.

    Zéro faux positif. Un finding sans preuve est du bruit. On ne livre que du signal.

    Souverain. Fonctionne offline. Aucune dépendance cloud.

    Auditable. Le code source est ouvert, lisible, modifiable.

🤝 Contribuer

Les contributions sont les bienvenues. Voir CONTRIBUTING.md.

Points d'entrée pour contribuer :

    Ajouter de nouvelles règles de détection (workflows, secrets, patterns)

    Intégrer de nouveaux moteurs (Semgrep rules custom, OSV-scanner, etc.)

    Améliorer la déduplication

    Ajouter des formats de sortie (SARIF complet, PDF)

    Documenter les cas d'usage réels

📜 Licence

NEXUS-OPEN-3.0 — Voir LICENSE

    ✅ Usage personnel et commercial gratuit

    ✅ Modification et distribution autorisées

    ⚠️ Attribution obligatoire : Aissa Mohammedi (DGK)

    ⚠️ Modifications documentées

🧬 Auteur

Aissa Mohammedi (DGK)
github.com/Aissamohammedi88

Héritier du protocole NEXUS. Architecte du système.
<div align="center"><svg width="600" height="40" viewBox="0 0 600 40" xmlns="http://www.w3.org/2000/svg"> <defs> <linearGradient id="endGrad" x1="0%" y1="0%" x2="100%" y2="0%"> <stop offset="0%" stop-color="#00ff88" stop-opacity="0"/> <stop offset="50%" stop-color="#00ff88" stop-opacity="1"/> <stop offset="100%" stop-color="#00ff88" stop-opacity="0"/> </linearGradient> </defs> <line x1="0" y1="20" x2="600" y2="20" stroke="url(#endGrad)" stroke-width="2"/> <text x="300" y="28" text-anchor="middle" font-family="ui-monospace, monospace" font-size="13" fill="#8b9dc3" font-style="italic"> « Ce qui est vérifié ne se cache pas. » <animate attributeName="opacity" values="0.4;1;0.4" dur="4s" repeatCount="indefinite"/> </text> </svg>

Made with 🧬 by Aissa Mohammedi (DGK) · 2026 · NEXUS OPEN SOURCE
</div> ```### Analyse SAST

| Moteur | Langages couverts |
|--------|-------------------|
| Semgrep | Python, JavaScript, Java, Go, Ruby, PHP, C, C++ |
| Bandit | Python uniquement |
| **SpotBugs** | **Java (bytecode)** |
| **PMD** | **Java (source)** |
| Custom rules | Tous (via regex et patterns) |
| Outil | Version minimale | Rôle |
|-------|------------------|------|
| Python | 3.10+ | Runtime principal |
| Git | 2.30+ | Clonage des dépôts |
| Semgrep | 1.50+ | SAST multi-langages |
| Trivy | 0.40+ | Scan de vulnérabilités |
| Gitleaks | 8.0+ | Détection de secrets |
| Bandit | 1.7+ | Sécurité Python |
| **SpotBugs** | **4.7+** | **Sécurité Java (bytecode)** |
| **PMD** | **6.50+** | **Qualité Java (source)** |

