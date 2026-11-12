# Workshop JavaScript — TeamManager

**YouCode — Campus Youssoufia | Classe CyphX**  
**Formateur : Tayeb SOUINI**  
**Sprint 2 : consolidation JavaScript | Bonus : Sprint 3**  
**Durée indicative : 4 h 30 + bonus | Travail individuel**

## 1. Contexte

Une entreprise dispose d'une interface de gestion des ressources humaines créée avec HTML et Tailwind CSS. Les fiches des employés sont affichées statiquement, mais les boutons, les filtres et les formulaires ne fonctionnent pas encore.

Ta mission consiste à rendre cette interface dynamique avec JavaScript, à réaliser les opérations CRUD sur des employés contenant des données imbriquées, puis à remplacer les données initiales par un fichier JSON et à conserver les modifications dans le `localStorage`.

> **Règle du workshop :** chaque étape peut être réalisée indépendamment. Si tu bloques, note la difficulté et passe à la suivante. Tu peux utiliser un petit jeu de données temporaire pour tester une fonctionnalité sans attendre que les autres soient terminées.

## 2. Objectifs pédagogiques

- Utiliser variables, conditions, boucles et fonctions.
- Manipuler des tableaux d'objets, des objets imbriqués et des tableaux imbriqués.
- Utiliser `find`, `findIndex`, `filter`, `map`, `reduce` et `forEach`.
- Utiliser les fonctions fléchées, le destructuring et les opérateurs spread/rest.
- Sélectionner, créer, modifier et supprimer des éléments HTML depuis JavaScript.
- Manipuler les événements et les formulaires.
- Valider les saisies, notamment à l'aide d'expressions régulières.
- Réaliser les opérations Create, Read, Update, Delete (CRUD).
- Manipuler JSON et `localStorage`.
- **Bonus Sprint 3 :** charger des données avec `fetch`, `Promise`, `async/await` et gérer les erreurs.

## 3. Starter fourni

```text
teammanager-starter/
├── index.html        # Interface HTML et Tailwind CSS statique
├── app.js            # Tableau initial de trois employés ; logique à développer
├── employees.json    # Dix employés pour l'étape d'import
└── README.md         # Instructions du starter
```

L'interface contient des cartes d'employés, des zones de statistiques, des champs de recherche/filtrage et un formulaire. **Le JavaScript des fonctionnalités est à développer par l'apprenant.**

### Structure des données

```javascript
const employees = [
  {
    id: 1,
    firstName: "Sara",
    lastName: "Alami",
    email: "sara@example.com",
    department: "Développement",
    salary: 9500,
    experience: {
      company: "TechSolutions",
      position: "Frontend Developer",
      years: 3
    },
    skills: [
      { name: "JavaScript", level: "Avancé" },
      { name: "React", level: "Intermédiaire" }
    ]
  }
];
```

Respecte la structure des données pendant toutes les étapes.

## 4. Déroulement du workshop

### Étape 1 — Affichage dynamique (30 min)

**Mission :** remplacer les cartes HTML statiques par des cartes générées depuis le tableau JavaScript.

- Afficher prénom, nom, email, département et salaire.
- Afficher les informations de l'objet `experience`.
- Parcourir et afficher toutes les compétences de `skills`.
- Prévoir un affichage adapté si le tableau est vide.

**Validation :** l'ajout manuel d'un employé dans le tableau, suivi du rendu, affiche une carte supplémentaire sans modification du HTML.

**Compétences observées :** tableaux d'objets, accès aux propriétés imbriquées, boucles, DOM.

### Étape 2 — Recherche et filtres (25 min)

**Mission :** permettre de rechercher et filtrer les employés.

- Rechercher par prénom ou nom, même avec une saisie partielle.
- Ignorer les différences de majuscules/minuscules.
- Filtrer par département.
- Actualiser les cartes sans recharger la page.

**Validation :** seuls les employés correspondants restent affichés ; un résultat vide est géré.

**Compétences observées :** événements, `filter`, conditions, chaînes de caractères.

### Étape 3 — Statistiques RH (25 min)

**Mission :** calculer des indicateurs à partir du tableau.

- Nombre total d'employés.
- Salaire moyen.
- Nombre d'employés ayant au moins trois ans d'expérience.
- Liste des compétences distinctes présentes dans l'entreprise.

**Validation :** les indicateurs correspondent aux données et se mettent à jour après une modification du tableau. Gérer le cas d'un tableau vide.

**Compétences observées :** logique, calculs, `map`, `reduce`, tableaux imbriqués.

### Étape 4 — Ajouter un employé (35 min)

**Mission :** rendre le formulaire d'ajout opérationnel.

- Récupérer les champs personnels et professionnels.
- Construire l'objet `experience`.
- Enregistrer au moins une compétence dans `skills`.
- Générer un identifiant unique.
- Vérifier les champs obligatoires, le format de l'email (regex) et les valeurs numériques.
- Afficher les erreurs près des champs concernés.

**Validation :** un employé valide est ajouté au tableau et apparaît dans l'interface ; un formulaire invalide n'ajoute rien.

**Compétences observées :** formulaires, événements, validation, regex, objets imbriqués.

### Étape 5 — Modifier un employé (30 min)

**Mission :** permettre la modification d'un employé existant.

- Identifier l'employé sélectionné par son `id`.
- Préremplir le formulaire avec ses informations, son expérience et ses compétences.
- Enregistrer les modifications sans créer un nouvel employé.
- Mettre à jour l'affichage.

**Validation :** les données modifiées sont visibles et l'identifiant de l'employé reste inchangé.

**Compétences observées :** `find`, `findIndex`, destructuring, spread, mise à jour d'objets.

### Étape 6 — Supprimer un employé (20 min)

**Mission :** activer la suppression d'un employé.

- Associer le bon employé au bouton Supprimer.
- Demander confirmation.
- Retirer uniquement l'employé sélectionné du tableau.
- Actualiser les cartes et les statistiques.

**Validation :** l'employé ciblé disparaît ; les autres restent inchangés.

**Compétences observées :** événements, `filter`, DOM, gestion des identifiants.

### Étape 7 — Compétences dynamiques (30 min)

**Mission :** permettre l'ajout et la suppression de plusieurs compétences dans le formulaire.

- Ajouter dynamiquement une ligne « nom de compétence + niveau ».
- Supprimer une ligne de compétence avant enregistrement.
- Valider les champs des compétences.
- Construire correctement le tableau `skills` lors de l'ajout ou de la modification d'un employé.

**Validation :** un employé peut posséder plusieurs compétences correctement enregistrées.

**Compétences observées :** DOM, événements, formulaires dynamiques, tableaux imbriqués.

### Étape 8 — Importer 10 employés depuis JSON (25 min)

**Mission :** remplacer les données initiales par les données du fichier `employees.json`.

- Retirer le jeu de trois employés codé en dur comme source principale.
- Charger les dix employés fournis dans le fichier JSON.
- Réutiliser la même logique d'affichage et de calcul.
- Pour cette étape, un import JSON statique dans un environnement compatible est accepté ; le chargement avec `fetch` sera traité dans le bonus.

**Validation :** les dix employés sont affichés sans avoir à écrire leurs cartes dans le HTML.

**Compétences observées :** structure JSON, séparation des données et de l'interface, réutilisation du code.

### Étape 9 — Sauvegarder dans localStorage (25 min)

**Mission :** conserver les données entre deux actualisations de la page.

- Enregistrer le tableau des employés avec `JSON.stringify`.
- Récupérer les données avec `JSON.parse`.
- Au premier démarrage, initialiser le stockage avec les dix employés du JSON.
- Aux démarrages suivants, utiliser les données enregistrées, même si le tableau sauvegardé est vide.
- Mettre à jour le stockage après chaque ajout, modification ou suppression.

**Validation :** après actualisation, les modifications restent présentes et un tableau volontairement vidé ne se remplit pas automatiquement.

**Compétences observées :** JSON, `localStorage`, persistance, initialisation des données.

### Bonus Sprint 3 — Chargement asynchrone

**Mission :** remplacer le chargement statique de `employees.json` par une requête asynchrone.

- Charger les données avec `fetch`.
- Utiliser une promesse et `async/await`.
- Afficher un état de chargement.
- Utiliser `try/catch` pour gérer les erreurs.
- Vérifier le statut HTTP et afficher un message en cas d'échec.
- Conserver la priorité des données déjà présentes dans `localStorage`.

**Validation :** l'application charge les données via un serveur local, sans bloquer l'interface, et affiche une erreur compréhensible si le JSON est inaccessible.

> Pour tester `fetch`, exécute le projet avec un serveur local (par exemple Live Server) plutôt qu'en ouvrant directement le fichier HTML avec `file://`.

## 5. Autoévaluation individuelle

Pour chaque compétence, indique : **0 — non acquis**, **1 — réalisé avec aide**, **2 — réalisé en autonomie**.

| Compétence | Étapes | Niveau (0/1/2) | Blocage ou preuve |
|---|---|---|---|
| Tableaux et objets imbriqués | 1, 4, 7 | | |
| DOM : sélection, création, modification, suppression | 1, 6, 7 | | |
| Événements JavaScript | 2, 4, 6 | | |
| Méthodes de tableaux ES6+ | 2, 3, 5 | | |
| Logique et calculs | 3 | | |
| Formulaires et validation / regex | 4, 5 | | |
| CRUD | 4, 5, 6 | | |
| Destructuring et spread/rest | 5 | | |
| JSON et localStorage | 8, 9 | | |
| Asynchronisme (bonus) | Bonus | | |

**Questions de bilan :**

1. Quelle étape as-tu réalisée sans aide ? Explique ton approche.
2. Sur quelle étape as-tu bloqué et pourquoi ?
3. Quelle différence fais-tu entre modifier un objet JavaScript et modifier un élément HTML ?
4. Comment accèdes-tu à une compétence d'un employé dans un tableau d'objets imbriqués ?
5. Quelle compétence veux-tu retravailler en priorité ? Quelle action concrète vas-tu réaliser ?

## 6. Livrables

- Un dépôt GitHub avec les fichiers du projet.
- Le fichier `employees.json` contenant les dix employés.
- Un `README.md` décrivant les fonctionnalités réalisées et non terminées.
- Le tableau d'autoévaluation complété, avec les blocages rencontrés.

## 7. Critères de réussite et débrief

La réussite n'est pas déterminée uniquement par le nombre d'étapes terminées. Le formateur vérifiera également la compréhension du code, la logique, la capacité à manipuler les données imbriquées, la qualité des validations et l'autonomie.

Lors du débrief, prépare-toi à expliquer une fonctionnalité, à justifier la méthode JavaScript choisie et à réaliser une petite modification en direct.

**Important :** ne copie pas une solution que tu ne comprends pas. Documente tes blocages et poursuis les autres missions : ce workshop sert aussi à identifier les compétences à renforcer.
