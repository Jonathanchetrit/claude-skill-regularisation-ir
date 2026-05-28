# Référence 01 — Types de revenus : qualification et calcul

## § A — Revenus de capitaux mobiliers étrangers (dividendes)

### Qualification
- Art. 120 et s. CGI + convention bilatérale du pays source
- Formulaire 2047 Section 201 + report case 2DC (formulaire 2042)

### Calcul ligne par ligne (2047 Section 201)
| Ligne | Libellé | Calcul |
|---|---|---|
| 200 | Pays | Nom du pays source |
| 201 | Revenu brut en devise | Montant brut avant retenue |
| 202 | Taux BCE annuel | Source : Webstat EXR.M |
| 203 | Revenu net imposable en EUR | Brut EUR − retenue EUR |
| 204 | Taux crédit d'impôt (notice 2047) | USA/UK/KR : 17,6 % ; JP/CN : 11,1 % ; vérifier convention |
| 205 | Crédit d'impôt théorique | Ligne 203 × taux ligne 204 |
| 206 | Retenue à la source effective | Montant retenu par le pays source |
| 207 | Crédit d'impôt retenu | min(ligne 205, ligne 206) |
| 208 | Revenu à reporter en 2DC | Ligne 203 + ligne 207 |

**Vérification Open Legi** : art. 199 ter CGI + notice 2047 de l'année + convention bilatérale

### Particularités par pays
- **USA** : retenue 15 % (convention FR-US) ; taux notice 17,6 % → crédit souvent = retenue
- **Royaume-Uni** : retenue 0 % depuis 2013 (convention FR-UK) → crédit = 0
- **Japon** : retenue 10 % ; taux notice 11,1 %
- **Corée du Sud** : retenue 15 % (convention FR-KR) ; taux notice 17,6 %
- **Chine** : dividendes HKD (Tencent etc.) ; taux notice 11,1 % ; vérifier convention FR-Chine
- **Autres pays** : toujours vérifier la convention via Open Legi

### PIL (Paiements en lieu et place de dividendes)
Même traitement que les dividendes. Souvent généré par prêt de titres (IBKR SYEP).
Reporter dans la même case 2DC.

---

## § B — Plus-values mobilières

### Qualification
- Art. 150-0 A et s. CGI
- Formulaire 2074 (détail) + report case 3VG (formulaire 2042)

### Calcul
```
PV nette = Σ(prix cession − prix revient) pour toutes les cessions de l'année
         − moins-values de l'année
         − moins-values reportables des années antérieures (10 ans max)
```

**Prix de revient** : prix d'acquisition + frais, converti au taux BCE du JOUR de l'acquisition
(pas le taux annuel moyen — exception importante, vérifier Open Legi art. 150-0 D CGI)

### Taux d'imposition
- PFU : 12,8 % IR + PS (vérifier taux PS applicable — voir SKILL.md § 4.1)
- Barème : option globale, après abattements pour durée de détention si titres acquis avant 2018

### Moins-values
- Reportables sur 10 ans (art. 150-0 D CGI)
- S'imputent uniquement sur des PV de même nature
- Vérifier les éventuelles MV des années antérieures via les déclarations existantes

### Actifs étrangers
Même calcul. Taux BCE du jour d'acquisition ET du jour de cession pour chaque transaction.

---

## § C — Produits de placement à revenu fixe (intérêts)

### Qualification
- Art. 124 et s. CGI
- Case 2TR (formulaire 2042)

### Inclut
- Intérêts créditeurs (comptes, obligations, dépôts)
- PIL sur intérêts (prêt de titres SYEP)
- CYEP/SYEP (programme prêt de titres IBKR)
- Intérêts de comptes à terme

### Ne pas inclure en 2TR
- Dividendes (→ 2DC)
- Plus-values (→ 3VG)
- Intérêts débiteurs (non déductibles pour les particuliers)

### Conversion devises
Taux BCE moyen annuel (EXR.M Webstat). Voir `references/03-taux-change-bce.md`.

---

## § D — Actifs numériques (crypto-actifs)

### Qualification
- Art. 150 VH bis CGI (depuis 2019)
- Formulaire 2086 (détail cessions) + report case 3AN (PV) ou 3BN (MV) sur 2042C

### Calcul
```
PV/MV = prix cession − (prix total acquisition × fraction cédée / portefeuille total)
```
Méthode obligatoire : prix moyen pondéré du portefeuille total.

**Attention** : toute cession crypto contre crypto OU crypto contre fiat est un fait générateur.
Les échanges intermédiaires entre cryptos sont imposables.

### Déclaration 3916 bis
Obligation de déclarer les comptes sur plateformes étrangères (Binance, Coinbase US, etc.)
Amende : 750 € par compte non déclaré (à vérifier via Open Legi — art. 1736 VII CGI)

### Vérification Open Legi
Art. 150 VH bis CGI + BOFiP RPPM - Actifs numériques + notice 2086

---

## § E — Traitements et salaires de source étrangère

### Qualification
- Art. 79 et s. CGI
- Formulaire 2047 Section 10 + report case 1AJ (contribuable) ou 1BJ (conjoint)

### Règles
- Revenu net imposable = brut − frais professionnels (déduction forfaitaire 10 % ou réels)
- Élimination double imposition : vérifier la convention bilatérale (exemption avec progressivité
  ou crédit d'impôt)
- Si exemption avec progressivité : le revenu étranger influe sur le taux français même s'il
  n'est pas imposé en France

### Documents sources
- Bulletins de salaire étrangers
- Équivalent W-2 (USA), P60 (UK), ou relevé employeur

---

## § F — Revenus fonciers de source étrangère

### Qualification
- Art. 14 et s. CGI + convention bilatérale
- Formulaire 2044 + report case 4BA (bénéfice) ou 4BB (déficit)

### Règles
- Revenus bruts − charges (intérêts d'emprunt, travaux, taxe foncière, gestion…)
- Convention fiscale : vérifier si imposable en France ou seulement pris en compte
  pour le taux (règle du taux effectif)
- Déficit foncier : imputable sur revenu global à hauteur de 10 700 € / an (art. 156 CGI)

### Vérification Open Legi
Art. 14 CGI + convention bilatérale du pays de situation de l'immeuble

---

## § G — Locations meublées (LMP / LMNP)

### Qualification et régimes
| Régime | Conditions | Formulaire |
|---|---|---|
| LMNP micro-BIC | Recettes ≤ 77 700 € / an | 2042C PRO (case 5ND ou 5NG) |
| LMNP réel simplifié | Recettes > 77 700 € ou option | 2031 + 2042C PRO (5NA/5NK) |
| LMP | Recettes > 23 000 € ET > autres revenus | 2031 + 2042C PRO (5KP/5KR) |

**Vérifier** via Open Legi art. 151 septies CGI (LMP) + art. 50-0 CGI (micro-BIC)

### Particularités
- LMP : déficit imputable sur revenu global sans plafond
- LMNP : déficit reportable 10 ans sur revenus de même nature uniquement
- Amortissements (régime réel) : non déductibles du résultat imposable mais reportables

---

## § H — Revenus de dirigeants

### Sous-types fréquents
| Statut | Nature du revenu | Formulaire | Case |
|---|---|---|---|
| Gérant majoritaire SARL | Rémunération (TNS) | 2042C PRO | 1GB/1HB |
| PDG / DG SAS | Salaire | 2042 | 1AJ/1BJ |
| Associé / actionnaire | Dividendes | 2042 | 2DC |
| Gérant non salarié | Rémunération art. 62 CGI | 2042C PRO | 1GB |

### Cotisations sociales TNS
Pour les gérants TNS : cotisations sociales déductibles du revenu imposable (à vérifier
avec les appels de cotisation URSSAF / SSI)

### Revenus de dirigeants étrangers
Vérifier la convention bilatérale pour la qualification (salaire vs dividende vs tantième)
et le pays d'imposition.
