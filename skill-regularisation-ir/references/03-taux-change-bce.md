# Référence 03 — Taux de change BCE : méthodologie officielle

## Source officielle

**Webstat BCE — EXR.M (moyennes mensuelles)**
URL : https://webstat.banque-france.fr
Série : EXR.M.[devise].EUR.SP00.A
Format téléchargeable : CSV (Webstat Export)

> ⚠️ Ne jamais utiliser :
> - Les taux IBKR (taux de transaction, pas taux de référence)
> - Les taux Google Finance
> - Les taux d'une banque commerciale
> Seul le taux BCE Webstat (EXR.M) fait foi pour l'administration fiscale française.

---

## Règle générale : moyenne annuelle

Pour les revenus courants (dividendes, intérêts, PIL), utiliser la **moyenne des 12
taux mensuels de l'année civile**.

```python
# Calcul de la moyenne annuelle
taux_annuel = sum(taux_mensuels) / 12
```

Le taux annuel est exprimé en : **1 EUR = X devises étrangères**
Pour convertir : montant_devise / taux_annuel = montant_EUR

---

## Exception : taux du jour pour les acquisitions de titres

Pour le **prix de revient fiscal** des titres acquis en devises étrangères,
utiliser le **taux BCE du jour de la transaction** (EXR.D — série quotidienne).

Source : EUR-Lex (JOUE) ou data-api.ecb.europa.eu
Format : « Le [date], 1 EUR = X USD — Référence JOUE [C YYYY/NNN/NN] »

> ⚠️ Cette exception est importante pour les plus-values.
> Un taux annuel moyen appliqué au prix d'acquisition peut fausser
> significativement la PV ou MV calculée.

---

## Tableau des taux BCE annuels officiels (1 EUR = X devises)

*(Extraits à compléter avec le fichier Webstat fourni par l'avocat)*

| Année | USD | HKD | JPY | NOK | GBP | CHF |
|---|---|---|---|---|---|---|
| 2020 | 1,1413 | 8,8517 | 121,78 | 10,7248 | 0,8897 | 1,0705 |
| 2021 | 1,1835 | 9,1988 | 129,86 | 10,1634 | 0,8600 | 1,0813 |
| 2022 | 1,0539 | 8,2512 | 138,00 | 10,1015 | 0,8528 | 1,0046 |
| 2023 | 1,0816 | 8,4676 | 151,94 | 11,4243 | 0,8700 | 0,9712 |
| 2024 | 1,0820 | 8,4430 | 163,82 | 11,6268 | 0,8456 | 0,9463 |
| 2025 | 1,1293 | 8,8049 | 168,95 | 11,7171 | 0,8499 | 0,9407 |

> ⚠️ Ces valeurs proviennent du fichier Webstat_Export_fr fourni dans ce dossier.
> Les vérifier et les compléter avec le fichier officiel pour chaque dossier.
> Pour les années ou devises non listées, télécharger le fichier Webstat BCE.

---

## Procédure de vérification du taux

1. Télécharger le fichier Webstat depuis banque-france.fr (série EXR.M)
2. Calculer la moyenne des 12 mois (ex. : cellule AVERAGE en Excel)
3. Arrondir à 4 décimales
4. Documenter la source dans la feuille Légende du tableau Excel

Si l'avocat fournit un fichier CSV Webstat :
→ Lire le fichier, extraire les valeurs mensuelles, calculer la moyenne

---

## Cas particuliers

### Devise non disponible dans Webstat
Si une devise exotique n'est pas dans le fichier BCE standard :
- Vérifier sur data.ecb.europa.eu (interface complète)
- Signaler à l'avocat et documenter la source alternative

### Comptes en CHF (Suisse)
Taux BCE disponible. Pas de spécificité particulière.

### Comptes en GBP (Royaume-Uni)
Taux BCE disponible. Vérifier post-Brexit si la convention FR-UK a évolué.

### Cryptomonnaies
Pas de taux BCE pour les cryptos (BTC, ETH, etc.).
Pour les crypto : utiliser le cours de marché au moment de la transaction,
documenté depuis une source reconnue (CoinGecko, Coinbase, Binance).
Vérifier via Open Legi si l'administration accepte cette méthode.

---

## Distinction revenus du patrimoine vs revenus de placement (LFSS 2026)

Depuis la LFSS 2026 (loi n°2025-1403 du 30/12/2025) :

| Catégorie (CSS) | Exemples | Taux PS 2025 | Taux PS 2026+ |
|---|---|---|---|
| Revenus du patrimoine (L.136-6) | Plus-values mobilières, revenus fonciers | **18,6 %** (rétroactivité 01/01/2025) | 18,6 % |
| Revenus de placement (L.136-7) | Dividendes, intérêts perçus en 2025 | **17,2 %** | 18,6 % |

> ⚠️ Vérifier via Open Legi art. L.136-6 et L.136-7 CSS avant d'appliquer un taux PS.
