# 📊 Claude Skill — Régularisation IR

> Workflow complet de régularisation fiscale IR en 7 phases.  
> Du tableau Excel au courrier au SIP, avec vérification systématique sur Légifrance.

---

## Le problème que ce skill résout

Une régularisation IR complète, c'est : analyser des dizaines de documents, convertir des devises, remplir des formulaires spécifiques à chaque année, rédiger un courrier argumenté et demander la remise gracieuse. Des heures de travail, avec un risque d'erreur à chaque étape.

Ce skill guide Claude à travers **7 phases structurées**, dans le bon ordre, avec vérification sur Légifrance à chaque règle citée — et un blocage explicite si un document manque.

---

## Les 7 phases et leurs livrables

| Phase | Ce que Claude produit |
|---|---|
| **1 — Analyse** | Cartographie des revenus par année et par type (à valider avant de continuer) |
| **2 — Excel** | Tableau de réconciliation avec taux BCE, crédits d'impôt, cases 2042 |
| **3 — Formulaires** | Lecture des notices Cerfa année par année |
| **4 — Open Legi** | Vérification de toutes les bases légales applicables |
| **5 — Roadmap** | Guide ligne par ligne pour remplir chaque formulaire |
| **6 — Manquants** | Liste des documents bloquants et souhaitables |
| **7 — Courrier** | Lettre au SIP avec demande de remise gracieuse (art. L.247 LPF) |

---

## Types de revenus couverts

Dividendes et intérêts étrangers · Plus-values mobilières · Crypto (2086) · Revenus fonciers · LMP / LMNP · Salaires étrangers · Revenus de dirigeants · **Comptes étrangers non déclarés (3916 / 3916 bis)**

---

## Ce que ça donne concrètement

Vous uploadez les relevés IBKR, les avis d'imposition et un relevé UBS et vous tapez :
> *"M. Dupont, dividendes américains et compte suisse non déclarés de 2019 à 2022. Résident français, célibataire. Régularisation spontanée."*

Claude analyse, cartographie, calcule, génère l'Excel, la roadmap et le courrier — en vous demandant votre validation à chaque étape clé.

---

## Installation

### Prérequis

- Compte [Claude.ai](https://claude.ai) — abonnement **Pro ou Team** recommandé (pour les fichiers volumineux)
- Connecteur **Open Legi** activé : Paramètres → Outils → Open Legi → Activer

### En 3 étapes

**1. Téléchargez** ce repo (bouton Code → Download ZIP)

**2. Remplissez** `CONFIG.md` avec les informations de votre cabinet (utilisées uniquement pour l'en-tête du courrier au SIP)

**3. Créez un Projet dans Claude.ai par dossier client**
   - Ouvrez Claude.ai → Projets → Nouveau projet → "Régularisation IR — [Nom client]"
   - Uploadez dans le projet : `SKILL.md`, `CONFIG.md`, et tous les fichiers du dossier `references/`
   - Uploadez également les **documents du client** (relevés, IFU, avis d'imposition...)
   - Lancez avec un brief client

> Le fichier `INSTALL.md` contient le guide complet avec des exemples de briefs de démarrage.

---

## Contenu du repo

```
skill-regularisation-ir/
├── README.md                         ← Vous êtes ici
├── SKILL.md                          ← Instructions pour Claude (7 phases)
├── CONFIG.md                         ← À remplir : cabinet (pour le courrier SIP)
├── INSTALL.md                        ← Guide d'installation détaillé
└── references/
    ├── 01-revenus-types.md           ← Qualification et calcul par type de revenu
    ├── 02-formulaires-cases.md       ← Cases 2042 / 2047 / 2074 / 3916...
    ├── 03-taux-change-bce.md         ← Méthode Webstat BCE, règles par devise
    ├── 04-strategie-defense.md       ← Pénalités, remise gracieuse, arguments
    └── 05-checklist-documents.md     ← Documents requis par type de revenu
```

---

## Limites importantes

- Ce skill **ne dépose pas** les déclarations sur impots.gouv.fr — cela reste à faire manuellement
- Il ne garantit pas l'exhaustivité si des documents sont manquants (il le signale explicitement)
- Les calculs doivent être **relus et validés** avant envoi au SIP
- **La responsabilité professionnelle reste celle de l'avocat ou du conseil**

---

## Licence

[MIT](./LICENSE) — Utilisation libre, y compris commerciale. Citez la source si vous partagez.
