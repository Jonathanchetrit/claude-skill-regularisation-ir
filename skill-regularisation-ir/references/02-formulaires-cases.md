# Référence 02 — Formulaires et cases

> ⚠️ Les cases et les règles changent d'une année à l'autre.
> Toujours utiliser la notice de l'ANNÉE CONCERNÉE.
> Vérifier via Open Legi ou impots.gouv.fr si notice non fournie par l'avocat.

---

## FORMULAIRE 2042 — Déclaration principale IR

### Cases revenus de capitaux mobiliers
| Case | Libellé | Source |
|---|---|---|
| 2DC | Revenus des actions et parts (dividendes bruts + crédits) | 2047 Sec. 201 ligne 208 + Sec. 260 brut + IFU 2DC |
| 2TR | Produits de placement à revenu fixe et intérêts | PIL + intérêts net + CYEP/SYEP + IFU 2TR |
| 2CK | Crédit d'impôt restituable (retenue FR non imputable) | IFU cases correspondantes |
| 2BH | Revenus soumis à prélèvement forfaitaire libératoire | Rare pour particuliers |

### Cases plus-values mobilières
| Case | Libellé | Source |
|---|---|---|
| 3VG | PV imposables (gains nets) | 2074 / Activity Statements |
| 3VH | Moins-values de l'année | 2074 |
| 3VB | MV antérieures reportables | Déclarations années précédentes |

### Cases crédits d'impôt étrangers
| Case | Libellé | Source |
|---|---|---|
| 8VL | Crédit d'impôt conventionnel — dividendes et intérêts étrangers | 2047 Sec. 201 ligne 207 (somme tous pays) |
| 8PL | Revenus étrangers ouvrant droit au crédit (informatif) | 2047 — net imposable tous pays |
| 8VM | Crédit d'impôt conventionnel — PV étrangères | Convention bilatérale |

### Option barème (case à cocher)
| Case | Libellé | Effet |
|---|---|---|
| 2OP | Option globale pour le barème progressif | S'applique à tous les RCM et PV de l'année |

> ⚠️ L'option 2OP est globale et irrévocable pour l'année. Simuler avant de cocher.

---

## FORMULAIRE 2042C — Complémentaire (revenus exceptionnels et divers)

### Cases actifs numériques (crypto)
| Case | Libellé |
|---|---|
| 3AN | PV sur cessions d'actifs numériques |
| 3BN | MV sur cessions d'actifs numériques |

### Cases LMP / LMNP (BIC)
| Case | Libellé | Régime |
|---|---|---|
| 5NA | Bénéfice LMNP réel (non professionnel) | LMNP réel |
| 5NK | Déficit LMNP réel reportable | LMNP réel |
| 5ND | Bénéfice LMNP micro-BIC | Micro-BIC abatt. 50 % |
| 5NG | Bénéfice LMNP micro-BIC (chambre hôtes) | Micro-BIC abatt. 71 % |
| 5KP | Bénéfice LMP réel (professionnel) | LMP réel |
| 5KR | Déficit LMP imputable sur RG | LMP réel |

### Cases revenus de dirigeants
| Case | Libellé |
|---|---|
| 1GB | Rémunération gérant majoritaire (art. 62 CGI) |
| 1HB | Rémunération gérant majoritaire (conjoint) |

---

## FORMULAIRE 2047 — Revenus encaissés à l'étranger

### Section 201 — Dividendes et revenus assimilés
Structure ligne par ligne : voir `references/01-revenus-types.md` § A

**Règle de consolidation** :
- Une ligne par PAYS (pas par titre)
- Agréger tous les dividendes du même pays sur une seule ligne
- Exception : si taux de retenue différent entre titres du même pays → lignes séparées

**Report vers 2042** :
- Somme de toutes les lignes 208 de la Sec. 201 + Section 260 (brut) → case **2DC**
- Somme de toutes les lignes 207 → case **8VL**
- Somme de toutes les lignes 203 → case **8PL** (informatif)

### Section 260 — Dividendes de source française (si perçus à l'étranger)
- Dividendes de sociétés françaises sur compte étranger
- Taux abattement 40 % si option barème (art. 158 CGI)
- Inclus dans case 2DC au brut

### Section 10 — Traitements et salaires de source étrangère
- Revenu net imposable selon convention
- Si exemption avec progressivité : reporter en case 8TI (taux effectif)

---

## FORMULAIRE 2074 — Plus-values mobilières (détail)

Structure par cession :
| Colonne | Contenu |
|---|---|
| Nature / désignation | Nom du titre |
| Date d'acquisition | Jour / mois / année |
| Date de cession | Jour / mois / année |
| Prix de cession | En EUR (taux BCE du jour de cession) |
| Prix d'acquisition | En EUR (taux BCE du JOUR d'acquisition) |
| PV ou MV | Différence |

Totaux :
- Total PV → case 3VG (formulaire 2042)
- Total MV → case 3VH (formulaire 2042)

---

## FORMULAIRE 2086 — Cessions d'actifs numériques

- Une ligne par cession
- Méthode : PMP (prix moyen pondéré de l'ensemble du portefeuille)
- Report vers 2042C cases 3AN (PV) ou 3BN (MV)
- Vérifier via Open Legi art. 150 VH bis CGI et notice 2086

---

## FORMULAIRE 3916 / 3916 bis — Comptes étrangers

**3916** : comptes bancaires détenus à l'étranger (art. 1649 A CGI)
**3916 bis** : comptes sur plateformes crypto étrangères (art. 1649 bis C CGI)

Informations requises par compte :
- Désignation de l'organisme
- Adresse complète
- Numéro du compte
- Nature du compte (courant, épargne, titres…)
- Période de détention (dates d'ouverture et de clôture, ou "en cours")
- Cotitulaires éventuels

> ⚠️ Une déclaration 3916 par compte ET par année.
> Si le compte existe depuis 5 ans et n'a jamais été déclaré → 5 formulaires 3916.

Amendes : 1 500 € (avoirs ≤ 50 000 €) ou 10 000 € (avoirs > 50 000 €) par compte/an
(art. 1736 IV CGI — vérifier montant via Open Legi, peut avoir évolué)

---

## FORMULAIRE 2044 — Revenus fonciers

- Recettes brutes (loyers encaissés)
- Charges déductibles (intérêts, travaux, assurance, taxe foncière, frais gestion…)
- Résultat net → 4BA (bénéfice) ou 4BB (déficit)

---

## FORMULAIRE 2031 — Résultat BIC (LMP / LMNP réel)

- Liasse fiscale simplifiée (régime simplifié) ou normale
- Résultat → report sur 2042C PRO selon statut LMP/LMNP

---

## Tableau récapitulatif : flux entre formulaires

```
2047 Sec. 201 ──► Ligne 208 (par pays) ──► 2042 case 2DC
2047 Sec. 201 ──► Ligne 207 (par pays) ──► 2042 case 8VL
2047 Sec. 201 ──► Ligne 203 (par pays) ──► 2042 case 8PL
2074            ──► Total PV             ──► 2042 case 3VG
2086            ──► PV crypto            ──► 2042C case 3AN
2044            ──► Résultat foncier     ──► 2042 case 4BA/4BB
2031            ──► Résultat BIC         ──► 2042C PRO
3916            ──► Déclaration annexe (amendes si omise)
```
