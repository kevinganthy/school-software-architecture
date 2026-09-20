---
title: Théorie et généralités sur les architectures logicielles
duration: 10 minutes
description: 
---

# {{ page.title }}

⏱️ Durée estimée : {{ page.duration }}

> {{ page.description }} 

## Objectifs pédagogiques

- **Distinguer** les caractéristiques, avantages et limites d'architecture logicielle.
- **Identifier** les anti-patterns d'architecture les plus courants
- **Sélectionner** une architecture adaptée à partir de scénarios et de besoins métiers.

---

## Pourquoi plusieurs architectures ?

Une cabane de jardin, une maison individuelle et un gratte-ciel ont tous des fondations, mais pas les mêmes contraintes ni les mêmes coûts.

![Différentes architectures](./assets/foundation.jpeg)

---

En logiciel, c'est pareil : on choisit une architecture en fonction des contraintes :

- Scalabilité / Charge (combien d'utilisateurs simultanés ?)
- Taille et organisation de l'équipe (2 dev vs 50 dev)
- Time-to-market / Budget (faut-il sortir le produit en 2 semaines ou en 2 ans ?)
- Complexité métier & Résilience (si un composant tombe, comment doit réagir le système ?)

---

## Panoramique express des grands modèles

⚠️ On ne rentre pas dans les détails d'implémentation, on se concentre sur les problèmes résolus et les compromis à faire avec chaque architecture.

### Monolithe

> Le classique MVC : Tout le code (front, back, BDD) dans un seul projet/déploiement.

---

👍👍👍 Avantages : Simple à développer, rapide à déployer au début, facile à tester.

👎👎👎 Inconvénients : Devient un capharnaüm si le projet grossit, scalabilité verticale obligatoire.

### Microservices

> L'application est découpée en petits services autonomes spécialisés (ex: Paiement, Auth, Catalogue...) qui communiquent entre eux ou avec le client.

![Microservices](./assets/microservices.png)

---

👍👍👍 Avantages : Équipes indépendantes, déploiements isolés, scalabilité horizontale et ciblée.

👎👎👎 Inconvénients : Complexité réseau, devops lourd, consistance des données difficile.

---

Une alternative est le **Service Oriented Architecture (SOA)**, qui est un peu plus centralisé et moins orienté "micro" que les microservices.

### Architecture orientée événements (Event-Driven)

> Les composants communiquent en émettant et en réagissant à des événements.

![Event-Driven](./assets/event-driven.png)

---

👍👍👍 Avantages : Découplage fort entre les services, haute réactivité en temps réel, excellente tolérance aux pannes (asynchronisme).

👎👎👎 Inconvénients : Complexité architecturale accrue, traçabilité des données/flux difficile, cohérence éventuelle à gérer.