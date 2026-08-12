# 🎉 724events — Débogage d'une application React

> Débogage et fiabilisation du site vitrine one-page de l'agence événementielle **724events**. Correction de bugs guidée par les tests unitaires, nettoyage de la console, renforcement de l'accessibilité et rédaction d'un cahier de recette.

## 🚀 Démo / lancement

> ⚠️ Le projet n'est pas déployé en ligne. Pour tester le site, suivez la section [Installation](#-installation) pour le lancer en local (`yarn start`, port 3000).

## 🎯 Contexte du projet

724events est une agence événementielle dont le nouveau site vitrine, développé en **React**, comportait plusieurs bugs avant sa mise en ligne. Le projet part d'une base de code fournie par OpenClassrooms, accompagnée d'une note de l'ancien développeur listant une partie des anomalies.

**Mission :** reprendre le code existant, **identifier et corriger les bugs** (dont certains non documentés), en s'appuyant sur la **suite de tests** comme boussole, sans jamais modifier les tests. Puis **rédiger un cahier de recette** au format Gherkin pour valider le bon fonctionnement du site.

## 🛠️ Technologies utilisées

- **React 18** — composants fonctionnels, hooks et Context API
- **Create React App** (`react-scripts`) — configuration et serveur de développement
- **Sass** — préprocesseur CSS
- **Jest** & **React Testing Library** — tests unitaires et d'intégration
- **ESLint** — analyse statique et qualité de code
- **Yarn** — gestionnaire de paquets
- **Git / GitHub** — versioning

## ✨ Fonctionnalités du site

- ✅ **Carrousel** des événements à la une, triés par date décroissante, avec pagination cliquable
- ✅ **Section "Nos réalisations"** : liste filtrable par catégorie, pagination et modale de détail
- ✅ **Formulaire de contact** avec message de confirmation en modale
- ✅ **Footer** affichant la dernière prestation (l'événement le plus récent)
- ✅ Chargement des données via une **API locale** (`fetch` sur `events.json`) partagée par un **contexte** React

## 🐛 Travail réalisé

**Bugs corrigés** (4 de l'énoncé + 2 trouvés en plus) :

- 🐛 **Mois décalé** : `getMonth()` est indexé à 0, l'objet des mois de 1 à 12 → passage en tableau aligné à 0
- 🐛 **Confirmation du formulaire** : appel manquant à `onSuccess()` dans le cas de succès
- 🐛 **Filtre inopérant** : ternaire identique des deux côtés + `onChange()` appelé sans sa valeur
- 🐛 **Carrousel à l'envers** : comparateur de tri inversé (croissant au lieu de décroissant)
- 🐛 **Frame vide en fin de carrousel** *(bonus)* : index bornant à `length` au lieu de `length - 1`
- 🐛 **Dernière prestation absente** *(bonus)* : donnée `last` jamais fournie par le contexte

**Améliorations complémentaires :**

- ♿ **Accessibilité** renforcée (navigation clavier du filtre, `aria-label`, `aria-selected`) — score Lighthouse **91/100**
- 🧹 **Console** entièrement nettoyée (clés React, styles inline, données `undefined`)
- 🧪 **Tests unitaires** ajoutés et **immutabilité** respectée (tri sur une copie)
- 📋 **Cahier de recette** rédigé au format Gherkin (Given / When / Then)

## 📐 Structure du projet

```text
724events/
├── src/
│   ├── components/       # Briques d'affichage : Button, EventCard, Field, Select, Logo…
│   ├── containers/       # Briques avec logique : Slider, Events, Form, Modal…
│   ├── contexts/         # DataContext — chargement et partage des données
│   ├── helpers/          # Fonctions utilitaires (ex. Date/getMonth)
│   ├── pages/            # Home — assemblage de la page
│   ├── App.js            # Enveloppe l'application dans le DataProvider
│   └── index.js          # Point d'entrée de l'application
├── public/
│   └── events.json       # Données des événements
├── package.json
└── README.md
```

## 🎓 Compétences travaillées

- **Débogage** méthodique d'une application React existante
- Utilisation des **tests unitaires** comme outil de diagnostic (Jest, React Testing Library)
- Compréhension du **state**, des **props**, des **callbacks** et de la **Context API**
- Manipulation de données : tri (`.sort()`), filtrage (`.filter()`), **immutabilité**
- **Accessibilité** web (navigation clavier, attributs ARIA) et audit **Lighthouse**
- Rédaction d'un **cahier de recette** au format Gherkin

## 📦 Prérequis

- **Node.js** (version 16.14.2 ou supérieure ; projet testé avec Node 24)
- **Yarn**

## 🚀 Installation

```bash
git clone https://github.com/leaspadea/724events.git
cd 724events
yarn install
```

Puis lancer le site en développement :

```bash
yarn start
```

Le site est accessible sur `http://localhost:3000`.

## 🧰 Scripts disponibles

| Commande        | Description                                          |
|-----------------|------------------------------------------------------|
| `yarn start`    | Lance le serveur de développement (port 3000)        |
| `yarn build`    | Génère la version de production dans `/build`         |
| `yarn test`     | Lance les tests avec Jest (mode watch)               |
| `yarn lint`     | Analyse le code avec ESLint                          |
| `yarn format`   | Formate le code avec Prettier                        |

## 👤 Auteur

**Léa Spadea** — Étudiante Intégratrice Web @ OpenClassrooms
🔗 [LinkedIn](https://www.linkedin.com/in/lea-spadea/) · 💻 [GitHub](https://github.com/leaspadea)

## 📄 Licence

Ce projet est sous licence **MIT**. Voir le fichier `LICENSE` pour plus de détails.

---

*Projet réalisé dans le cadre de la formation Intégrateur Web (RNCP niveau 5) chez OpenClassrooms.*
