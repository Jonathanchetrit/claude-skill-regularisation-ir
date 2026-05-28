---
name: regularisation-ir
description: >
  Skill de régularisation fiscale en matière d'impôt sur le revenu (IR) français,
  pour avocats fiscalistes et conseils fiscaux. Déclencher dès qu'un avocat ou
  conseiller fiscal mentionne une régularisation, une déclaration omise, un client
  n'ayant pas déclaré, des comptes étrangers non déclarés, des revenus non déclarés
  (dividendes, plus-values, crypto, foncier, BIC, salaires, revenus de dirigeants,
  location meublée LMP/LMNP), ou toute demande de mise en conformité fiscale IR
  pour des années passées. Couvre tous les types de revenus, tous pays, toutes
  années prescrites ou non. Produit dans l'ordre : tableau Excel, roadmap ligne par
  ligne, liste des manquants, courrier d'accompagnement à l'administration. Utilise
  systématiquement Open Legi pour vérifier toutes les bases légales. Ne jamais
  démarrer sans que le conseil ait précisé l'impôt concerné et les années à
  régulariser.
---

# Skill : Régularisation IR — Guide opérationnel

## Fichiers de référence — charger selon besoin

| Fichier | Contenu | Quand charger |
|---|---|---|
| `references/01-revenus-types.md` | Qualification et règles de calcul par type de revenu | Phase 1 — dès que les revenus sont identifiés |
| `references/02-formulaires-cases.md` | Formulaires standard, cases 2042/2047/2074/3916/2044/2031 | Phase 3 — lecture des formulaires |
| `references/03-taux-change-bce.md` | Méthodologie taux BCE, source Webstat, règles par devise | Phase 2 — dès qu'une devise étrangère apparaît |
| `references/04-strategie-defense.md` | Pénalités, remise gracieuse, amendes 3916, jurisprudence | Phase 7 — rédaction du courrier |
| `references/05-checklist-documents.md` | Documents requis par type de revenu | Phase 6 — liste des manquants |
| `CONFIG.md` | Informations du cabinet (signataire du courrier, SIREN, barreau) | Phase 7 — en-tête du courrier |

---

## Démarrage

Lorsque le skill est déclenché, commencer systématiquement par recueillir :

1. **L'impôt concerné** : IR (si IFI mentionné → skill IFI distinct)
2. **Les années à régulariser** : de quelle année à quelle année ?
3. **Le profil du client** : résident fiscal français ? célibataire / couple ? parts fiscales ?
4. **Le contexte** : régularisation spontanée, réponse à contrôle, déclaration tardive ?

> ⚠️ Ne jamais supposer les années sans vérification de la prescription.
> Consulter systématiquement l'art. L.169 LPF via Open Legi dès cette étape :
> droit commun = 3 ans ; comptes étrangers = 10 ans ; activités occultes = 6 ans.
> Le conseil valide le périmètre avant de passer à la Phase 1.

---

## PHASE 1 — Analyse des documents

### Règle fondamentale
**Analyser d'abord, calculer ensuite.** Ne jamais produire de chiffres avant d'avoir
lu et compris l'intégralité des documents fournis.

### 1.1 Lire tous les documents fournis

Pour chaque document uploadé (relevés bancaires, Activity Statements, IFU, avis
d'imposition, actes notariés, bulletins de salaire, liasses fiscales, relevés crypto…) :

- Identifier la nature du document
- Identifier la période couverte
- Identifier la devise et le pays d'origine
- Extraire les montants bruts, les retenues à la source, les dates

Si des notices de formulaires sont fournies : les lire en priorité
(elles font référence pour l'interprétation des lignes — voir Phase 3).

### 1.2 Cartographie des revenus

Dresser une cartographie synthétique avant tout calcul :

| Année | Type de revenu | Source / Pays | Devise | Document source | Statut |
|---|---|---|---|---|---|
| 20XX | Dividendes | USA (IBKR) | USD | Activity Statement | ✓ Reçu |
| 20XX | Plus-values | France | EUR | Relevé courtier | ✓ Reçu |
| 20XX | Intérêts | Suisse | CHF | Relevé bancaire | ✗ Manquant |
| … | … | … | … | … | … |

Soumettre cette cartographie à validation avant la Phase 2.

### 1.3 Charger les modules de référence pertinents

Selon les types de revenus identifiés, charger `references/01-revenus-types.md`
(section correspondante) et, si devise étrangère, `references/03-taux-change-bce.md`.

---

## PHASE 2 — Tableau Excel de réconciliation

### 2.1 Structure du tableau

Créer un fichier Excel avec :
- **Une feuille par année** régularisée (ex. : "1. 2020", "2. 2021"…)
- **Une feuille VERIF SOURCES** : détail des calculs avec traçabilité complète
- **Une feuille 0. Synthèse globale** : impôt total par année + total général
- **Une feuille Légende** : sources des taux BCE, références légales, versions

### 2.2 Contenu de chaque feuille annuelle

Pour chaque année, inclure dans le tableau :
- Revenus bruts par type et par devise (avant conversion)
- Taux BCE annuel appliqué (source Webstat officielle)
- Montants convertis en EUR
- Retenues à la source par pays
- Calcul du crédit d'impôt conventionnel (8VL)
- Cases 2042 renseignées avec leur valeur
- Régime d'imposition retenu (PFU ou barème) avec justification
- Impôt IR calculé + prélèvements sociaux

### 2.3 Règles de rigueur Excel

- **Toujours** utiliser les taux BCE officiels (source : Webstat BCE, EXR.M).
  Charger `references/03-taux-change-bce.md` pour la méthode exacte.
- Traçabilité : montant devise brut → ÷ taux BCE → montant EUR → case 2042
- Pas de valeurs en dur sans commentaire explicatif dans la cellule adjacente
- Les formules doivent être vérifiables ligne par ligne

> Le tableau Excel est la **source de vérité** du dossier.
> Tous les documents Word en découlent. Toute correction commence par l'Excel.

---

## PHASE 3 — Analyse des formulaires et des notices

### 3.1 Principe essentiel

Avant de remplir quoi que ce soit, obtenir idéalement :
- Les **notices** des formulaires applicables pour chaque année
- Les **formulaires vierges** ou les modèles Cerfa correspondants

Si les notices ne sont pas fournies : les rechercher via Open Legi ou impots.gouv.fr
et les mentionner explicitement.

### 3.2 Formulaires à analyser selon les revenus

Charger `references/02-formulaires-cases.md` pour le détail complet.

| Revenu | Formulaire principal | Formulaire annexe |
|---|---|---|
| Dividendes / intérêts étrangers | 2042 (2DC, 2TR, 8VL) | 2047 (Section 201) |
| Plus-values mobilières | 2042 (3VG) | 2074 |
| Actifs numériques (crypto) | 2042C (3AN/3BN) | 2086 |
| Revenus fonciers | 2042 (4BA/4BB) | 2044 |
| LMP / LMNP | 2042C PRO (5NA…) | 2031 / liasse BIC |
| Salaires étrangers | 2042 (1AJ/1BJ) | 2047 (Section 10) |
| Revenus de dirigeants (TNS) | 2042C PRO | 2035 (BNC) |
| Comptes étrangers | 3916 / 3916 bis | — |

### 3.3 Lecture des notices

Pour chaque formulaire, relever :
- La définition exacte de chaque ligne / case
- Les conditions d'application des abattements
- Les règles d'imputation des crédits d'impôt étrangers
- Les renvois à d'autres formulaires
- Les éventuelles modifications d'une année sur l'autre

> ⚠️ Les notices changent d'une année à l'autre. Toujours utiliser la notice
> de l'année concernée, pas celle de l'année courante.

---

## PHASE 4 — Vérification légale via Open Legi

Pour chaque revenu, chaque régime, chaque taux ou sanction :

1. Rechercher l'article CGI ou LPF applicable via Open Legi
2. Vérifier la **version en vigueur pour l'année concernée**
3. Identifier les conventions fiscales bilatérales (taux de retenue, crédit d'impôt)
4. Citer la référence exacte dans les documents produits

**Articles à vérifier systématiquement :**
- Régime PFU : art. 200 A CGI
- Plus-values mobilières : art. 150-0 A CGI
- Crédit d'impôt conventionnel : convention bilatérale + notice 2047
- Comptes étrangers : art. 1649 A CGI + art. 1736 IV CGI
- Prescription : art. L.169 LPF
- Remise gracieuse : art. L.247 LPF

> Ne jamais affirmer un taux ou une règle sans citation vérifiée via Open Legi.
> En cas de doute, l'indiquer explicitement.

---

## PHASE 5 — Roadmap déclarative : guide ligne par ligne

### 5.1 Principe

Produire un guide opérationnel complet pour remplir physiquement chaque formulaire,
année par année, ligne par ligne.

### 5.2 Format de la roadmap

Pour chaque année :

```
ANNÉE 20XX — [Régime retenu : PFU 30 % / Barème]

FORMULAIRE 2042 :
  Case 3VG  → [montant] €  [source : feuille Excel "20XX" cellule E12]
  Case 2DC  → [montant] €  [source : Sec. 201 2047 ligne 208 + Sec. 260]
  Case 2TR  → [montant] €  [source : PIL + intérêts]
  Case 2CK  → [montant] €  [source : retenues non imputables]
  Case 8VL  → [montant] €  [source : crédit d'impôt conventionnel]
  Case 8PL  → [montant] €  [informatif]

FORMULAIRE 2047 — Section 201 :
  Ligne 200 (pays) : [pays]
  Ligne 203 (revenu net) : [montant] €
  Ligne 204 (taux notice) : [17,6 % / 11,1 % / autre]
  Ligne 205 (crédit théorique) : [montant] €
  Ligne 206 (retenue effective) : [montant] €
  Ligne 207 (crédit retenu = min 205/206) : [montant] €
  Ligne 208 (revenu + crédit → 2DC) : [montant] €

FORMULAIRE 3916 :
  Compte [N°] — [banque] — [pays] — [ouvert le] — [clôturé le / toujours ouvert]

[Formulaires supplémentaires selon revenus identifiés]
```

### 5.3 Contrôle de cohérence de la roadmap

Avant de finaliser, vérifier que :
- La somme des lignes 208 (Section 201) = case 2DC (déduction faite des Sections 260…)
- Le crédit d'impôt en 8VL = somme des lignes 207 de toutes les sections
- Les montants de la roadmap correspondent exactement à l'Excel

---

## PHASE 6 — Liste des documents et informations manquants

### 6.1 Structure de la liste

**Documents BLOQUANTS** (calcul impossible sans eux) :
| Document manquant | Année(s) | Impact | À demander à |
|---|---|---|---|
| Activity Statement complet 20XX | 20XX | PV et dividendes impossibles à calculer | Client / courtier |
| … | … | … | … |

**Documents SOUHAITABLES** (permettent d'affiner ou de justifier) :
| Document | Année(s) | Usage | À demander à |
|---|---|---|---|
| Certificat médical | Toutes | Remise gracieuse majorations | Médecin traitant |
| Acte d'achat titres | 20XX | Prix de revient (taux jour d'achat) | Notaire / courtier |
| … | … | … | … |

### 6.2 Informations manquantes

Au-delà des documents, lister les informations à confirmer :
- Numéro fiscal à 13 chiffres (obligatoire pour les formulaires)
- Adresse exacte du SIP compétent (domicile du contribuable)
- Dates précises d'ouverture / clôture des comptes étrangers
- Situation familiale exacte (nombre de parts, enfants à charge)

---

## PHASE 7 — Courrier d'accompagnement à l'administration

### 7.0 Prérequis — Lire CONFIG.md

Avant de rédiger le courrier, lire `CONFIG.md` pour récupérer :
- NOM_CABINET, NOM_AVOCAT, TITRE_AVOCAT
- ADRESSE_CABINET, EMAIL_CABINET
- SIREN_CABINET, BARREAU

Ces informations composent le bloc d'identification du cabinet dans l'en-tête.

### 7.1 Structure obligatoire du courrier

**En-tête :**
```
[NOM_CABINET]
[ADRESSE_CABINET]
[EMAIL_CABINET] — [TEL_CABINET]
SIREN : [SIREN_CABINET] — Barreau de [BARREAU]
Signataire : [NOM_AVOCAT], [TITRE_AVOCAT]

À l'attention de Monsieur/Madame le Directeur
Service des Impôts des Particuliers de [ville du contribuable]
[Adresse du SIP]

[Ville], le [date]

Objet : [voir § 7.2]

Pour le compte de : [Nom du contribuable] — N° fiscal : [numéro à 13 chiffres]
```

**Introduction — Contexte et motifs du retard/défaut :**
- Exposé factuel et chronologique de la situation du client
- Explication des raisons du défaut ou retard déclaratif
  (état de santé, incident technique, méconnaissance, situation de vulnérabilité…)
- Qualification de la démarche : **régularisation spontanée** (circonstance atténuante)
- Référence à l'art. L.247 LPF pour la demande de remise

**Développements — Exposé année par année :**
Pour chaque année, une sous-section distincte :
- Nature des revenus déclarés
- Formulaires déposés
- Montant d'impôt dû
- Éléments de justification spécifiques à l'année

**Demande de remise gracieuse :**
- Majorations et intérêts de retard (art. L.247 LPF)
- Amendes 3916 (art. L.247 LPF + art. 1736 IV CGI)
  → Mentionner le taux applicable (1 500 € ou 10 000 € selon seuil 50 k€)
- Arguments individualisés (état de santé, bonne foi, première infraction…)
- Jurisprudence applicable si pertinente (vérifier via Open Legi)

Charger `references/04-strategie-defense.md` pour les arguments et la jurisprudence.

**Conclusion :**
- Rappel du caractère spontané
- Engagement du contribuable à se conformer
- Formule de politesse professionnelle

### 7.2 Formulation de l'objet

Forme correcte :
> Dossier de régularisation spontanée en matière d'impôt sur le revenu [années]
> et de prélèvements sociaux et de comptes bancaires détenus à l'étranger

> ⚠️ Orthographe : « impôt sur le revenu » (singulier, sans majuscule, sans s à revenu)

---

## Règles transversales — Ne jamais violer

1. **Séquence obligatoire** : Phase 1 → 2 → 3 → 4 → 5 → 6 → 7.
   Ne jamais produire de courrier (Phase 7) avant que l'Excel (Phase 2) et la roadmap
   (Phase 5) soient validés.

2. **Vérification légale systématique** : chaque taux, chaque qualification, chaque
   sanction doit être vérifiée via Open Legi avant d'être affirmée.

3. **Source de vérité unique** : l'Excel est la référence. Tout montant dans les
   documents Word en découle. Toute correction commence par l'Excel, puis se propage.

4. **Documents manquants = blocage explicite** : si un document bloquant est absent,
   ne pas produire de calcul approximatif sans le signaler. Lister les hypothèses
   retenues et leurs limites.

5. **Cohérence bout en bout** : à la livraison finale, effectuer le contrôle croisé
   Excel ↔ roadmap ↔ courrier. Tout écart est une erreur à corriger.

6. **Notices de formulaires** : toujours travailler à partir de la notice de l'année
   concernée. Ne pas extrapoler depuis une autre année.

7. **Taux de change** : uniquement les moyennes annuelles Webstat BCE (EXR.M).
   Exception : taux du jour BCE pour les prix d'acquisition de titres.

8. **Terminologie** : « impôt sur le revenu » (jamais « impôts sur les revenus »).
