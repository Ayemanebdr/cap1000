# CAP 1000

Application web progressive (PWA) pour suivre ton travail (Carrefour + intérim), tes revenus, le plafond de 964 heures et l'échéancier de ta scolarité.

## Ce que contient le dossier

| Fichier | Rôle |
|---|---|
| `index.html` | L'application complète (interface, calculs, stockage) |
| `manifest.webmanifest` | Nom, couleurs et icônes pour l'installation |
| `sw.js` | Service worker : l'app s'ouvre sans connexion |
| `icons/` | Icône iPhone, icônes Android/ordinateur, favicon |

## Mettre en ligne sur GitHub Pages (comme Budjé)

1. Sur GitHub (compte `Ayemanebdr`), crée un dépôt public nommé `cap1000`.
2. Bouton **Add file → Upload files** : glisse **le contenu** du dossier (`index.html`, `manifest.webmanifest`, `sw.js`, `README.md` et le dossier `icons`). Valide avec **Commit changes**.
3. **Settings → Pages** : Source = *Deploy from a branch*, branche `main`, dossier `/ (root)`, **Save**.
4. Après une à deux minutes, l'app est en ligne à l'adresse `https://ayemanebdr.github.io/cap1000/`.

## Installer sur l'iPhone

1. Ouvre l'adresse dans **Safari** (l'installation passe par Safari sur iPhone ; avec iOS récent, Chrome propose aussi « Ajouter à l'écran d'accueil » dans son menu Partager).
2. Bouton **Partager → Sur l'écran d'accueil → Ajouter**.
3. Lance CAP 1000 depuis l'icône : l'app s'ouvre en plein écran et fonctionne hors connexion.

Sur ordinateur (Chrome ou Edge), une icône d'installation apparaît dans la barre d'adresse.

## Où sont tes données

- Elles sont enregistrées **dans le navigateur de l'appareil** (stockage local). Rien n'est envoyé sur un serveur.
- Chaque appareil a ses propres données. Pour passer de l'iPhone à l'ordinateur : **Paramètres → Exporter en JSON**, puis **Importer un fichier** sur l'autre appareil (ou copier/coller la sauvegarde).
- Fais une sauvegarde JSON **avant chaque mise à jour importante** et de temps en temps. Si tu effaces les données de Safari, ou si tu supprimes l'app de l'écran d'accueil, les données locales peuvent disparaître.

## Mettre à jour l'app

Remplace `index.html` dans le dépôt. Pour forcer le rafraîchissement du cache hors connexion, change aussi la ligne `const VERSION='cap1000-v1'` de `sw.js` (par exemple `v2`). Tes données ne sont pas touchées par une mise à jour, mais exporte une sauvegarde avant, par sécurité.

## Utilisation au quotidien

- **+ (bouton central)** : ajouter une mission d'intérim (date, agence, entreprise, heures, taux, montant réel si connu).
- **Carrefour** : valider chaque samedi (8 h par défaut, modifiable), saisir le montant réel de la fiche de paie pour le mois travaillé.
- **Échéancier** :
  - *Simulateur* : crée et compare les propositions (9, 10, 11, 12 mensualités ou montants personnalisés). Ce sont des simulations.
  - *Marquer comme accord accepté* : uniquement après confirmation avec l'école. La mensualité devient alors ton objectif du mois.
  - *Réviser* : accepter une autre proposition conserve les échéances déjà payées (même partiellement) et tous les paiements ; seules les échéances futures non payées sont remplacées, et l'ancienne version reste dans l'historique.
  - *Projection mensuelle* : pour chaque mois, mensualité, Carrefour prévu, intérim nécessaire, heures (taux de référence et prudent), heures par semaine, économies utilisées, cumul d'heures et alerte plafond.
- **Plafond 964 h** : compteur de la période de référence, alertes à 50/70/80/90/95/100 %, projection, périodes successives.
- **Financement** : paiements à l'école, sommes mises de côté, aides extérieures, reste à financer.
- **Autorisation de travail** : règles et démarches, avec les sources officielles consultées le 30/10/2026.

## Données préchargées (modifiables)

- Période : 22/09/2026 → 21/09/2027, plafond 964 h (à confirmer auprès de la préfecture).
- Carrefour : samedis du 26/09 au 24/10/2026 (5 × 8 h = 40 h) ; le 31/10/2026 est « à confirmer ».
- Intérim : 30 h du 5 au 9 octobre et 18 h du 12 au 14 octobre (Iziwork), de 6 h à 12 h chaque jour.
- Agences proposées en raccourci : Domino RH, RAS Intérim, Iziwork (bouton « + Autre agence » dans le formulaire de mission, ou Paramètres → Mes agences d'intérim).
- Total : 88 h, soit 876 h restantes.
- Quatre propositions d'échéancier (A à D) sur 11 000 €, première échéance le 5 novembre 2026 : aucune n'est acceptée.

## Notifications

Les alertes s'affichent dans l'app. Les notifications push sur iPhone demandent iOS 16.4 ou plus, une app ajoutée à l'écran d'accueil, ton autorisation et un serveur d'envoi ; CAP 1000 n'en utilise pas pour que tes données restent sur ton appareil.
