# INSTALL.md — Guide d'installation en 5 minutes
# Skill : Régularisation IR
# Aucune compétence technique requise.

---

## Ce que fait ce skill

Ce skill vous guide pas à pas dans une régularisation IR complète :
il analyse les documents fournis, produit un tableau Excel de réconciliation,
génère une roadmap déclarative ligne par ligne, liste les documents manquants,
et rédige le courrier d'accompagnement au Service des Impôts des Particuliers.

Il interroge systématiquement **Open Legi** pour vérifier chaque règle, taux et
sanction — et signale ses doutes plutôt que d'inventer des réponses.

---

## Étape 1 — Prérequis

- Un compte **Claude.ai** (Pro ou Team recommandé pour les fichiers volumineux)
- Le connecteur **Open Legi** activé :
  → Paramètres → Outils → Rechercher "Open Legi" → Activer

---

## Étape 2 — Configurer votre cabinet

Ouvrez `CONFIG.md` et remplissez vos informations (nom, adresse, SIREN, barreau).
Ces données seront utilisées uniquement dans l'en-tête du courrier au SIP.

---

## Étape 3 — Installer le skill

### Option A — Via un Projet Claude (recommandé)

1. Ouvrez **Claude.ai** → **Projets** → **Nouveau projet**
2. Nommez-le "Régularisation IR" (ou par client : "Régularisation IR — M. Durand")
3. Uploadez directement dans le projet tous les fichiers du skill :
   - `SKILL.md`
   - `CONFIG.md` (rempli)
   - `references/01-revenus-types.md`
   - `references/02-formulaires-cases.md`
   - `references/03-taux-change-bce.md`
   - `references/04-strategie-defense.md`
   - `references/05-checklist-documents.md`
4. Uploadez également les **documents du dossier client** (relevés, IFU, avis…)

### Option B — Par dossier (sans projet)

Dans une nouvelle conversation :
1. Chargez `SKILL.md` + `CONFIG.md` en début de conversation
2. Uploadez les documents du dossier client
3. Lancez avec : "Je souhaite régulariser la situation IR de [client] pour [années]"

---

## Étape 4 — Lancer une régularisation

Exemples de phrases de démarrage :

> *"Mon client M. Dupont n'a pas déclaré ses dividendes américains et un compte
> Suisse entre 2019 et 2022. Il est célibataire, résident français. Régularisation
> spontanée."*

> *"Voici les documents d'une cliente qui a oublié de déclarer ses revenus locatifs
> LMNP depuis 2020. Elle est mariée, 2 parts."*

Claude va alors :
1. Vous demander les informations manquantes
2. Dresser la cartographie des revenus (à valider avant de continuer)
3. Produire l'Excel de réconciliation
4. Générer la roadmap déclarative année par année
5. Lister les documents manquants
6. Rédiger le courrier au SIP

---

## Ce que le skill ne fait pas

- Il ne dépose **pas** les déclarations en ligne (cela reste à faire sur impots.gouv.fr)
- Il ne **signe pas** le courrier à votre place
- Il ne **garantit pas** l'exhaustivité si des documents sont manquants
- Il ne remplace **pas** votre analyse juridique finale

---

## En cas de problème

| Problème | Solution |
|---|---|
| Claude saute une phase | Rappeler : "Reviens à la Phase X avant de continuer" |
| L'Excel contient des erreurs | Corriger dans l'Excel → demander à Claude de mettre à jour la roadmap |
| Open Legi indisponible | Claude le signalera — relancer plus tard ou vérifier manuellement |
| Le courrier manque d'arguments | Préciser le contexte personnel du client (santé, vulnérabilité…) |

---

## Les 7 phases en un coup d'œil

| Phase | Livrable |
|---|---|
| 1 — Analyse documents | Cartographie des revenus (à valider) |
| 2 — Excel | Tableau de réconciliation par année |
| 3 — Formulaires | Lecture des cases et notices |
| 4 — Open Legi | Vérification de toutes les bases légales |
| 5 — Roadmap | Guide ligne par ligne pour remplir les formulaires |
| 6 — Manquants | Liste des documents bloquants et souhaitables |
| 7 — Courrier | Lettre au SIP avec demande de remise gracieuse |

---

*Skill créé pour les avocats fiscalistes et conseils fiscaux.*
*Version 1.0*
