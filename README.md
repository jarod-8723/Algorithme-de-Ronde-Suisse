# 🏸 Ronde Suisse — Badmin'potes

Interface web de gestion de tournoi en ronde suisse, conçue pour le tournoi **Badmin'potes** du **7 juillet** organisé par le club **ASLB**.

---

## 🎯 Contexte

Ce projet a été développé spécifiquement pour l'occasion, afin de remplacer la gestion manuelle du tirage au sort et du suivi des scores. L'objectif : un outil simple, utilisable sans installation, directement depuis un navigateur.

---

## 🚀 Utilisation

Double-cliquer sur `ronde_suisse.html` pour ouvrir l'interface dans le navigateur. Aucune installation, aucun serveur requis.

> ⚠️ Une connexion internet est nécessaire au premier chargement pour récupérer la librairie de lecture Excel (SheetJS). Elle est ensuite mise en cache par le navigateur.

---

## ✨ Fonctionnalités

### 1. 📂 Import des joueurs
- 📄 Import du fichier `.xlsx` de la liste des joueurs (format export du club)
- 🔍 Détection automatique de la colonne `Nom`
- 🖱️ Glisser-déposer ou sélection via l'explorateur de fichiers

### 2. 👥 Sélection des joueurs
- ✅ Chaque joueur est cliquable pour le marquer absent (exclu du tirage)
- 🔘 Boutons tout sélectionner / tout désélectionner

### 3. 🎲 Tirage de la ronde
- 📊 Groupement des joueurs par niveau de points
- 🔀 Formation aléatoire des équipes en doubles (2v2)
- ⚔️ Appariement des équipes au sein d'un même groupe
- 💤 Gestion automatique des exemptés si le nombre de joueurs n'est pas divisible par 4 — les joueurs exemptés reçoivent +1 point et ne sont pas exemptés deux fois de suite
- 💾 Export de la ronde en `.txt`

### 4. ⏰ Ajout d'un retardataire
- ➕ Disponible avant chaque ronde
- 📐 Le joueur est intégré avec `⌊ moyenne des points actuels ⌋` pour rester compétitif

### 5. 🏆 Saisie des scores
- 👆 Clic sur l'équipe gagnante pour chaque match
- 📈 Barre de progression — le bouton de validation reste désactivé tant que tous les matchs ne sont pas renseignés

### 6. 📋 Classement
- 🔄 Tableau mis à jour après chaque ronde
- 🗑️ Suppression définitive d'un joueur en cours de tournoi (abandon, départ anticipé)
- 💾 Export du classement en `.txt`

---

## 📁 Format du fichier Excel

Le fichier est conçu pour être compatible directement avec l'export de la liste des inscrits généré par **Badnet**, le logiciel de gestion de compétition qui s'interface avec **Poona** — le logiciel fédéral de la FFBaD (Fédération Française de Badminton). C'est via Poona que les clubs déclarent leurs tournois et gèrent les inscriptions ; Badnet en exporte la liste des participants au format `.xlsx` avec les colonnes H/F, Licence, Nom, Club, Cat, Simple, Double, Mixte, Pts.

L'outil ne lit que la colonne **`Nom`** (insensible à la casse) et ignore toutes les autres. La ligne d'en-tête peut se trouver sur n'importe quelle ligne parmi les 5 premières du fichier — ce qui correspond au format Badnet qui inclut une ligne de titre "BadNet" avant l'en-tête réel.

---

## 🛠️ Stack technique

| Composant | Détail |
|---|---|
| Interface | HTML / CSS / JavaScript vanilla |
| Lecture Excel | [SheetJS](https://sheetjs.com/) v0.18.5 (CDN) |
| Dépendances | Aucune (hors SheetJS) |
| Compatibilité | Tout navigateur moderne (Chrome, Firefox, Edge, Safari) |

---

## ⚠️ Limites connues

- 🔁 Pas de sauvegarde persistante — un rechargement de la page remet le tournoi à zéro
- 💻 Conçu pour un usage sur un seul appareil (pas de multijoueur temps réel)

---

*🏸 Projet réalisé pour le tournoi Badmin'potes — ASLB, juillet 2025.*
