<div align="center">

# 🇫🇷 Monitor PLF 2027

**Moniteur open source du chiffrage du projet de loi de finances 2027 pour chaque commune, intercommunalité et département.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub last commit](https://img.shields.io/github/last-commit/gunout/monitor-plf2027)](https://github.com/gunout/monitor-plf2027/commits)
[![GitHub issues](https://img.shields.io/github/issues/gunout/monitor-plf2027)](https://github.com/gunout/monitor-plf2027/issues)
[![GitHub stars](https://img.shields.io/github/stars/gunout/monitor-plf2027?style=social)](https://github.com/gunout/monitor-plf2027/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/gunout/monitor-plf2027?style=social)](https://github.com/gunout/monitor-plf2027/network/members)

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/fr/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/fr/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/fr/docs/Web/JavaScript)
[![API](https://img.shields.io/badge/API-data.gouv.fr-000091)](https://www.data.gouv.fr/api)
[![Backend](https://img.shields.io/badge/backend-none-success)](#)
[![DSFR](https://img.shields.io/badge/design-DSFR-000091)](https://www.systeme-de-design.gouv.fr/)
[![Status](https://img.shields.io/badge/status-ready-brightgreen)](#)

[🚀 Démarrage](#-démarrage-rapide) · [✨ Fonctionnalités](#-fonctionnalités) · [🏷️ Types](#️-types-de-collectivités) · [🛠️ Stack](#️-stack-technique) · [📄 Licence](#-licence)

</div>

---

## 📖 À propos

**Monitor PLF 2027** est un tableau de bord **mono-fichier** qui interroge directement l'[API publique de data.gouv.fr](https://www.data.gouv.fr/api) et affiche en temps réel les données de chiffrage du **projet de loi de finances 2027** pour chaque collectivité territoriale française.

- **34 961 communes**
- **1 230 intercommunalités** à fiscalité propre
- **95 départements**

Le moniteur détaille, pour chacune, les **6 mesures du PLF 2027** qui pèsent sur son budget :

1. **Art. 37** — Contribution progressive à l'effort budgétaire
2. **Art. 35** — Abaissement du taux de FCTVA
3. **Art. 36** — Écrêtement de la fraction de TVA
4. **Art. 84** — Report du reversement du DILICO
5. **Art. 34** — Minoration de la DTCE
6. **CNRACL** — Hausse de la cotisation

Aucun backend, aucun build, aucune dépendance npm. Un fichier HTML, un navigateur, et c'est parti.

> Conçu pour les journalistes, chercheurs, élus locaux et citoyens qui veulent **explorer et comprendre** l'impact du PLF 2027 sur les finances de leur collectivité.

---

## ✨ Fonctionnalités

- 🏘️ **3 types de collectivités** : Communes · Intercommunalités · Départements
- 📊 **6 mesures détaillées** par collectivité
- 🎯 **Filtre par décile** (D1 à D10)
- 🔀 **Tri** : effort total · effort/habitant · nom
- 🔍 **Recherche** par nom, code INSEE, décile
- 📄 **5 vues** : Lignes · Mesures · Analyses · Comparer types · Qualité
- 📥 **Exports** CSV / JSON côté client
- 📊 **Panneau Intelligence** : top 5 efforts, état API, activité récente
- 🎨 **Design DSFR** (Système de Design de l'État)
- 🌙 **Dark mode** persistant
- 📱 **Responsive** : mobile, tablette, desktop
- 🌐 **0 dépendance** à l'exécution (hors CDN)
- 📁 **Chargement local** : glisser-déposer des CSV (fonctionne en `file://`)

---

## 🚀 Démarrage rapide

### Option 1 — Cloner le dépôt

    git clone https://github.com/gunout/monitor-plf2027.git
    cd monitor-plf2027

### Option 2 — Télécharger directement

    curl -O https://raw.githubusercontent.com/gunout/monitor-plf2027/main/plf2027-monitor.html

### Ouvrir le moniteur

    # Linux
    xdg-open plf2027-monitor.html

    # macOS
    open plf2027-monitor.html

    # Windows
    start plf2027-monitor.html

Ou simplement **double-cliquer** sur `plf2027-monitor.html` dans ton explorateur de fichiers.

> ℹ️ L'API `data.gouv.fr` autorise les requêtes cross-origin (CORS `*`) — **aucun serveur local n'est nécessaire**.

---

## 🧭 Utilisation

| Action | Résultat |
|---|---|
| Cliquer sur **▶ CHARGER** | Interroge l'API data.gouv.fr et récupère les 3 CSV |
| Glisser un **CSV** dans la zone de gauche | Charge les données en local (offline) |
| Cliquer sur un **type** (sidebar) | Filtre communes / intercos / départements |
| Choisir un **décile** | Filtre les collectivités par décile de richesse |
| Changer le **tri** | Effort total, effort/habitant, nom |
| `Entrée` dans la recherche | Lance la recherche |
| **📥 Export CSV/JSON** | Télécharge les résultats affichés |
| **🗑️ Effacer** | Réinitialise l'état |

### Exemples de recherche

    Bastides de Lomagne
    200034726
    Carcassonne Agglo
    Mont-Blanc

---

## 🏷️ Types de collectivités

| Type | Nombre | Code | Exemple |
|---|---|---|---|
| 🏘️ **Communes** | 34 961 | INSEE 5 chiffres | `75056` (Paris) |
| 🏛️ **Intercommunalités** | 1 230 | SIREN 9 chiffres | `200035715` (Carcassonne Agglo) |
| 🗺️ **Départements** | 95 | 2–3 caractères | `75`, `2A`, `971` |

---

## 🛠️ Stack technique

| Composant | Technologie |
|---|---|
| **Frontend** | HTML5 + CSS3 (variables, grid, flexbox) |
| **Logique** | JavaScript vanilla (ES2020) |
| **API** | data.gouv.fr/api/1 |
| **Design** | DSFR 1.11.2 (CDN) |
| **Parsing CSV** | Parser maison (détection auto `;` `,` `\t`) |
| **Exports** | Blob API native |
| **Zéro build** | Aucun npm, webpack, ou transpileur |

---

## 📁 Structure du projet

    monitor-plf2027/
    ├── plf2027-monitor.html   ← l'application complète (HTML + CSS + JS)
    ├── README.md              ← ce fichier
    └── LICENSE                ← MIT

---

## 🔧 Personnalisation

### Changer la source API

Ouvre `plf2027-monitor.html`, cherche la constante `API_URL` en haut du `<script>` :

    const API_URL = 'https://www.data.gouv.fr/api/1/datasets/...';

### Ajouter une mesure

Cherche `SIX_MESURES` et ajoute une entrée :

    const SIX_MESURES = [
      { key:'art37', label:'Contribution progressive (art. 37)' },
      // ...
      { key:'nouvelle', label:'Nouvelle mesure' }
    ];

Puis adapte `normalizeRowFromArray()` pour lire la bonne colonne.

### Changer le thème par défaut

    theme: localStorage.getItem('plf2027-theme') || 'dark'  // 'light' par défaut

---

## ⚠️ Limites connues

- Les **données sont des estimations** établies sur le texte déposé le 1ᵉʳ octobre 2026 — la navette parlementaire les modifiera.
- La **contribution définitive** est notifiée par arrêté.
- L'API v1 de data.gouv.fr est **stable** mais moins performante que la v2 pour la recherche.
- Pas de cache persistant : chaque chargement refait les appels réseau.
- Le **niveau de solidité** (établi / étayé / indicatif / ordre de grandeur) n'est pas exposé dans les 3 CSV principaux — il figure dans le PDF de documentation.

---

## 🗺️ Roadmap

- [x] **v1.0** — Moniteur mono-fichier avec 3 types de collectivités
- [ ] **v1.1** — Vue carte de France (effort/habitant par département)
- [ ] **v1.2** — Comparateur commune A vs commune B
- [ ] **v1.3** — URL partageable (`?q=…&type=…&decile=…`)
- [ ] **v1.4** — Export PNG des vues Analyses et Comparer
- [ ] **v2.0** — Version PWA (offline + installable)
- [ ] **v2.1** — Backend FastAPI optionnel pour cache + exports massifs

---

## 🤝 Contribution

Les contributions sont **les bienvenues** !

1. Fork le projet
2. Crée une branche (`git checkout -b feature/ma-fonctionnalite`)
3. Commit tes changements (`git commit -m 'Ajout de ma fonctionnalité'`)
4. Push (`git push origin feature/ma-fonctionnalite`)
5. Ouvre une Pull Request

### Signaler un bug

Ouvre une [issue](https://github.com/gunout/monitor-plf2027/issues) en précisant :

- Le navigateur et sa version
- Les étapes pour reproduire
- Le comportement attendu vs observé

---

## 📄 Licence

Distribué sous licence **MIT**. Voir `LICENSE` pour plus d'informations.

Les **données** affichées proviennent de [data.gouv.fr](https://www.data.gouv.fr) et sont publiées par le cabinet **BP Avocats**. Elles sont soumises à leur propre licence (majoritairement [Licence Ouverte 2.0](https://www.etalab.gouv.fr/licence-ouverte-open-licence)).

> ⚠️ **Avertissement** : ces chiffres sont des **estimations** et ne valent pas consultation. La contribution définitive est notifiée par arrêté.

---

## 🙏 Remerciements

- [data.gouv.fr](https://www.data.gouv.fr) — pour l'API publique
- [BP Avocats](https://bp-avocats.bzh/plf-2027/) — pour le chiffrage et le simulateur public
- [Etalab](https://www.etalab.gouv.fr) — pour l'ouverture des données
- [DSFR](https://www.systeme-de-design.gouv.fr) — pour le design system de l'État
- [Shields.io](https://shields.io) — pour les badges

---

<div align="center">

**⭐ Si ce projet t'est utile, mets-lui une étoile ! ⭐**

[Signaler un bug](https://github.com/gunout/monitor-plf2027/issues) · [Proposer une fonctionnalité](https://github.com/gunout/monitor-plf2027/issues) · [Contribuer](https://github.com/gunout/monitor-plf2027/pulls)

Fait avec 🇫🇷 pour les données publiques françaises.

</div>

---

<div align="center">

### 🇫🇷 Gunout · 2026

![Made in France](https://img.shields.io/badge/Made_in-France-002395?style=flat-square&labelColor=FFFFFF&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA5MDAgNjAwIj48cmVjdCB3aWR0aD0iOTAwIiBoZWlnaHQ9IjYwMCIgZmlsbD0iIzAwMjM5NSIvPjxyZWN0IHdpZHRoPSI5MDAiIGhlaWdodD0iNDAwIiB5PSIxMDAiIGZpbGw9IiNmZmYiLz48cmVjdCB3aWR0aD0iOTAwIiBoZWlnaHQ9IjIwMCIgeT0iNDAwIiBmaWxsPSIjZWQyOTM5Ii8+PC9zdmc+)
![GitHub](https://img.shields.io/badge/GitHub-gunout-181717?style=flat-square&logo=github&logoColor=white)
![Year](https://img.shields.io/badge/2026-ED2939?style=flat-square&labelColor=FFFFFF)

<sub>© 2026 <strong>Gunout</strong> — Tous droits réservés.</sub>

</div>
