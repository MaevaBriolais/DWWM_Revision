# Recap des journées

---

> **Note**
>
> Drives des dossiers communs & privés

|                                  Lien Drive / Utiles                                   |
| :------------------------------------------------------------------------------------: |
|   [Commun](https://drive.google.com/drive/folders/1wejsBzAh7XXAs3vILtkEtySmOM_eji-B)   |
|   [Privé](https://drive.google.com/drive/folders/1aKS-GDpFbZ3I-WOsLD7jLKwvS0Efvvuq)    |
|        [Wild Code School Workshop](https://wildcodeshool-workshop.netlify.app/)        |
| [Remote-projects-demo](https://github.com/WildCodeSchool-2024-02/Remote-projects-demo) |

---

## Saison 4️⃣

### :calendar: 27/05/2024

:package: _Récap du jour_

Les bases de la POO

Ce matin, nous avons vu la `POO` (Programmation Orientée Objet).

Nous avons vu plein de chose :

-   Les classes (en PascalCase)
    -   `class MyClass {}`
-   Les méthodes (en camelCase)
    -   `sayHello() {}`
-   Les propriétés publiques & privées
    -   `this.name = "John"`
    -   `this.#lastname = "Doe"`
-   Les constructeurs
    -   `constructor(name, lastname) { this.name = name; this.#lastname = lastname; }`
-   super
    -   `super(name, lastname)`
    -   permet d'appeler le constructeur de la classe parente

![poo](./assets/super.png)

-   Les getters & setters
    -   `getName() { return this._name }` | `setName(name) { this._name = name }`
-   Les héritages
    -   `class MyClass extends MyOtherClass {}`

```js
// Création d'une classe
class Obj = {
	constructor(param1, param2) {
		// this fait référence à l'instance
		this.param1 = param1;
		this.param2 = param2;
	}
	method1() {
		return this.param1;
	}
	method2() {
		return this.param2;
	}
}
```

### 💡 Ce qu'il faut retenir !

Au lieu de répéter le même code pour créer plusieurs objets, nous pouvons créer une classe et créer des `instances` de cette classe.

### 😭 Avant

```js
const student = {
	name: "Julie",
	campus: "Berlin",
	age: 30,
	isGratuated: true,
	skills: ["JS", "React"],
	sayHello: function () {
		return "Hello, my name is " + this.name;
	},
};

const student1 = {
	name: "Marc",
	campus: "Lisbonne",
	age: 34,
	isGratuated: true,
	skills: ["Python"],
	sayHello: function () {
		return "Hello, my name is " + this.name;
	},
};
```

### 😍 Après

```js
class Student {
	constructor(name, age, skills, isGraduated) {
		this.name = name;
		this.age = age;
		this.skills = skills;
		this.isGraduated = isGraduated;
	}

	sayHello() {
		return "Hello, my name is " + this.name;
	}
}

const student = new Student("Julie", 30, ["JS", "React"], true);
const student1 = new Student("Marc", 34, ["Python"], true);
```

Nous pouvons définir une propriété privée avec le signe `#`.

```js
class Cat {
	#age;
	constructor(name, age, race) {
		this.name = name;
		this.#age = age;
		this.race = race;
	}

	getAge() {
		return this.#age;
	}

	setAge(age) {
		this.#age = age;
	}

	talk() {
		return "Meow...... (" + this.name + " says)";
	}
}

const cat1 = new Cat("Biscotte", 5, "non défini");
const cat2 = new Cat("Gaïa", 11, "européenne");

cat1.getAge(); // 5
cat1.setAge(6); // nouvelle valeur, age = 6
cat1.getAge(); // 6
cat1.age; // undefined
```

:link: _Liens utiles_

-   [JS with classes](https://docs.google.com/presentation/d/1pkrVtNGHeCGO7nkiUVgTmGenkZ58jZp1mzsss6Lc_jI/edit#slide=id.p)
-   [WildCodeSchool-2024-02/JS-RemoteFR-CrewDragon-Heracles](https://github.com/WildCodeSchool-2024-02/JS-RemoteFR-CrewDragon-Heracles)

---

### :calendar: 24/05/2024

:package: _Récap du jour_

Harmonia est un framwork maison, il possède l'architecture MVC.

Je ne vais pas faire un récap, car le cours est assez long et je ne veux pas répéter la documentation.

:bulb: Ce qu'il faut retenir (quand même)

### Dossier App

-   `config` : [permet de setup toute l'application](https://documentation-harmonia.vercel.app/docs/basics/backend/src/app)
-   `controllers` : [Les controleurs une position très importante dans notre framework](https://documentation-harmonia.vercel.app/docs/basics/backend/src/controllers)
-   `routers` : [Ce dossier permet d'organiser toutes les routes de notre application](https://documentation-harmonia.vercel.app/docs/basics/backend/src/router)
-   `services` : contient les services de l'application (helpers)

![route](./assets/routes.png)

Vu autrement :
![route](./assets/route2.png)

:link: _Liens utiles_

-   [Harmonia - Introduction](https://docs.google.com/presentation/d/1ToH8W1j794O9yumvQ12NLZx4hZvHsjnyCfmdROor5iY/edit#slide=id.g1fa0b9efc78_0_366)
-   [Harmonia - Documentation](https://documentation-harmonia.vercel.app/)

---

### :calendar: 23/05/2024

:package: _Récap du jour_

Merise: Et oui, maintenant dans votre `devlodex` vous avez un nouveau mot !

Merise est une méthode de conception de base de données relationnelles.

Nous avons appris à faire un **MCD** (Modèle Conceptuel de Données) et un **MLD** (Modèle Logique de Données) & un **MPD** (Modèle Physique de Données).

Les relations et les cardinalités sont très importantes dans la conception d'une base de données et surtout, ils n'ont plus de secret pour vous !

![image](https://media.tenor.com/QdrfMv2CxRgAAAAC/office.gif)

:bulb: **Ce qu'il faut retenir**

### Les cardinalités

Les cardinalités permettent de définir le nombre d'occurrences d'une entité qui peuvent être associées à une autre entité.

Il y a 3 types de cardinalités :

-   **1** : une seule occurrence.
-   **0** : aucune occurrence.
-   **n** : plusieurs occurrences.

_Comment savoir si je met 0, 1 ou n ?_

Admettons les entitées suivantes :

User & Role et la relation entre les deux est `have`.

```mermaid
erDiagram
    User ||--o{ Role : have
```

Nous nous posons la question suivante :

Un _utilisateur_ a au **minimum** doit avoir un _rôle_, et un _utilisateur_ a au **maximum** un _rôle_. Donc, la cardinalité est `11` du côté de l'utilisateur.

Ensuite pour le Role, un _rôle_ peut être associé au minimum a **aucun** _user_ et au **maximum** à plusieurs _utilisateurs_. Donc, la cardinalité est `0n` du côté du rôle.

### Les relations

Il y a 3 types de relations :

-   **1 to 1** : une seule entité est liée à une autre entité.
-   **1 to many** : une entité est liée à plusieurs entités.
-   **many to many** : plusieurs entités sont liées à plusieurs entités.

### 1 to many

![1 to many](./assets/1-to-many.png)

### Many to many

![many to many](./assets/many-to-many.png)

:link: _Liens utiles_

-   [SQL - Database Modelling](https://docs.google.com/presentation/d/1LHvOGnH6PSndwHSo8ZXPZZk0lKnSGXAWUNDEYBgMsLs/edit#slide=id.g28c786c5d62_0_47)
-   [Modéliser une base de données | Wild code school](https://wildcodeschool.github.io/workshop-db-modelisation/)
-   [GorskiAnthony/tp-bdd](https://github.com/GorskiAnthony/tp-bdd/tree/main)
-   [👨‍🎓 Après la théorie, des exos](https://github.com/GorskiAnthony/tp-bdd/tree/main?tab=readme-ov-file#-apr%C3%A8s-la-th%C3%A9orie)

---

### :calendar: 22/05/2024

:package: _Récap du jour_

Nous avons enfin vu MySQL ! Vous allez pouvoir stocker vos données.

Mais pour ce faire, un petit rappel sur les **bases de données relationnelles.**

### 💡 Ce qu'il faut retenir

`SQL` est un langage de manipulation de données, il permet de créer, de lire, de mettre à jour et de supprimer des données dans une base de données relationnelle.

Voilà une liste des commandes SQL :

```sql
-- Création d'une base de données
CREATE DATABASE IF NOT EXISTS `my_database`;

-- Sélection de la base de données
USE `my_database`;

-- Création d'une table
CREATE TABLE IF NOT EXISTS `my_table` (
	`id` INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
	`name` VARCHAR(255) NOT NULL,
	`age` INT NOT NULL
);

-- Insertion de données
INSERT INTO `my_table` (`name`, `age`) VALUES
	('John', 25),
	('Jane', 30),
	('Bob', 20);

-- Alteration de la table pour ajouter une colonne
ALTER TABLE `my_table` ADD `email` VARCHAR(255) NOT NULL;

-- Alteration de la table pour supprimer une colonne
ALTER TABLE `my_table` DROP `email`;

-- Alteration de la table pour modifier une colonne
ALTER TABLE `my_table` MODIFY `name` VARCHAR(50);

-- Sélection de toutes les données
SELECT * FROM `my_table`;

-- Sélection de données avec une condition
SELECT * FROM `my_table` WHERE `age` > 25;

-- Sélection de données avec un alias
SELECT `name` AS `nom`, `age` AS `âge` FROM `my_table`;

-- Séléction de données avec LIKE
SELECT * FROM `my_table` WHERE `name` LIKE 'J%';

-- Mise à jour de données
UPDATE `my_table` SET `age` = 40 WHERE `name` = 'John';

-- Suppression de données
DELETE FROM `my_table` WHERE `name` = 'Bob';

-- Nettoyage de la table
TRUNCATE TABLE `my_table`;

-- Suppression de la table
DROP TABLE `my_table`;

-- Suppression de la base de données
DROP DATABASE `my_database`;
```

:link: _Liens utiles_

-   [SQL [FR] - Intro](https://docs.google.com/presentation/d/1-hBQBvMN4Xud-jMk7QV47YVMgnfcWU4L8YRY0v2AljE/edit#slide=id.g27de47c1a64_0_95)
-   [Base de données | Wild code school](https://wildcodeschool.github.io/workshop-database-introduction/)
-   [Cours et Tutoriels sur le Langage SQL](https://sql.sh/)

---

## ON A ROMPICHE

![](https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExOGRienRnenJ6MGxqMWtoeDVpb2Mya3U2azdncmY2Y3plbThheGNkMiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/5i0RdWktDx0xW/giphy.gif)

---

## Saison 3️⃣

### :calendar: 23/04/2024

:package: _Récap du jour_

Retour à React :D

Et cette fois-ci, nous allons voir la notion de `Context`.

Et oui, le context est très utile pour passer des données de composant en composant sans passer par les props.

### Props drilling

![props drilling](https://github.com/GorskiAnthony/WCS-react-context/raw/crm/_docs/props_drilling.png)

### Context

![context](https://github.com/GorskiAnthony/WCS-react-context/raw/crm/_docs/context.png)

L'avantage, c'est que l'on peut passer des données de composant en composant sans passer par les props.

```jsx
// context/NameContext.js

// j'importe createContext depuis react ainsi que useState
import { createContext, useState } from "react";

// je crée mon context
const NameContext = createContext("");

// je crée mon provider
const NameContextProvider = ({ children }) => {
	const [name, setName] = useState("");

	const handleChange = (e) => {
		setName(e.target.value);
	};

	return (
		<NameContext.Provider value={{ name, handleChange }}>
			{children}
		</NameContext.Provider>
	);
};

export { NameContextProvider, NameContext };
```

Et pour l'utiliser

```jsx
// main.jsx
// car je vais utiliser mon provider dans mon main

import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App.jsx";
// J'encapsule mon application dans le contexte NameContextProvider
// Maintenant, tous les composants de mon application ont accès au contexte NameContext
import { NameContextProvider } from "./context/NameContext.jsx";
import "./index.css";

ReactDOM.createRoot(document.getElementById("root")).render(
	<React.StrictMode>
		<NameContextProvider>
			<App />
		</NameContextProvider>
	</React.StrictMode>
);
```

Le composant B2

```jsx
// B2.jsx
import { useContext } from "react";
import { NameContext } from "../context/NameContext.jsx";
const B2 = () => {
	// Ici, je récupère le contexte NameContext
	// Je peux récupérer la valeur de name
	// grâce à la destructuration
	const { name } = useContext(NameContext);

	return (
		<div className="block">
			<h1>B2, and hello {name} 👋</h1>
		</div>
	);
};

export default B2;
```

:link: _Liens utiles_

-   [React [FR] - Context ](https://docs.google.com/presentation/d/1AEPYlFXoMfckTEyFFxQ-UIN2qzKzdPF6Fd49sqqKoV4/edit#slide=id.p)
-   [GorskiAnthony/WCS-react-context](https://github.com/GorskiAnthony/WCS-react-context)
-   [GorskiAnthony/WCS_TP_Context](https://github.com/GorskiAnthony/WCS_TP_Context)

---

### :calendar: 16/04/2024

🚨 Nouvelle notion ! 🚨

Et oui, nous avons appris le nouveau hook `useEffect` aujourd'hui !

### 💡 ce qu'il faut retenir

-   `useEffect` prend en paramètres :
    -   une fonction qui va être exécutée à chaque fois que le composant est rendu.
    -   tableau de dépendances, ce tableau permet de définir quand la fonction va être exécutée.

Concernant le tableau de dépendances, il est possible de définir :

-   `rien` : la fonction va être exécutée à chaque fois que le composant est rendu.
-   `[]` : la fonction va être exécutée une seule fois, au moment du rendu du composant.
-   `[value]` : la fonction va être exécutée à chaque fois que la valeur de `value` change.

```js
import { useEffect } from "react";

function App() {
	useEffect(() => {
		console.log("render");
	}, []);

	return <div>App</div>;
}
```

Le hook useEffect peut être utilisé pour effectuer différentes tâches, telles que :

> -   Récupérer des données depuis une API et mettre à jour l'état du composant en conséquence
> -   Abonner le composant à des événements (ex : clics de souris, mouvements de la souris, frappes de clavier, etc.)
> -   Mettre à jour le DOM pour refléter les changements d'état du composant
>     Nettoyer les effets de bord, tels que les abonnements aux événements, les connexions à des API, etc.

Il est important de noter que le hook useEffect doit être utilisé avec prudence, car il peut entraîner des effets de bord indésirables s'il est mal utilisé. Il est recommandé de ne pas exécuter de code coûteux dedans

En résumé, le hook useEffect est un outil puissant pour gérer les effets de bord dans les composants React. Il peut être utilisé pour exécuter une logique après le rendu d'un composant, telle que la récupération de données depuis une API, l'abonnement à des événements, la mise à jour du DOM, etc.

:link: _Liens utiles_

-   [React lifecycle methods diagram](https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/)
-   [UseEffect in Functional Component Vs Class Component Methods](https://blog.stackademic.com/useeffect-in-functional-component-vs-class-component-methods-also-starting-a-learn-react-hooks-626923fac5b5)

---

### :calendar: 15/04/2024

:package: _Récap du jour_

Ce matin, il y avait un atelier sur `react-router-dom`.

Il y a beaucoup de texte, mais dans tout ça, il faut retenir que `react-router-dom` est une librairie qui permet de gérer la navigation dans une application React.

#### Installation

Pour installer `react-router-dom`, il faut taper la commande suivante :

```shell
$ npm install react-router-dom
```

#### Les instructions d'importation

-   `createBrowserRouter` : permet de créer un contexte de navigation, il contient toute la logique de navigation.
-   `Link` : permet de créer un lien vers une autre page. (Celle ci ne recharge pas la page)
-   `RouterProvider` : permet de fournir le contexte de navigation à l'application.
-

```jsx
import { createBrowserRouter, RouterProvider } from "react-router-dom";

const router = createBrowserRouter([
	{
		// le chemin de l'URL, ici `/`
		path: "/",
		element: (
			<>
				<nav>
					<Link to="/">Home</Link>
					<Link to="/about">About</Link>
				</nav>
				<main>
					// le composant à afficher, bien sûr, il faut l'importer
					<Home />
				</main>
			</>
		),
	},
	{
		// le chemin de l'URL, ici `/about`
		path: "/about",
		element: (
			<>
				<nav>
					<Link to="/">Home</Link>
					<Link to="/about">About</Link>
				</nav>
				<main>
					// le composant à afficher, bien sûr, il faut l'importer
					<About />
				</main>
			</>
		),
	},
]);
```

#### Comment rendre ça plus propre ?

Nous pouvons créer un composant `Layout` qui va contenir la navigation et le composant à afficher.

Ce composant `Layout` sera la base de notre application, son affichage ne changera pas.

Pour pouvoir passer un composant différent en fonction de l'URL, nous allons utiliser le composant `Outlet`.

-   `Outlet` : permet d'afficher le composant correspondant à l'URL.

Voilà à quoi ressemble notre `Layout` :

```jsx
// Layout.jsx
import { Link, Outlet } from "react-router-dom";

function Layout() {
	return (
		<>
			<nav>
				<Link to="/">Home</Link>
				<Link to="/about">About</Link>
			</nav>
			<main>
				<Outlet />
			</main>
		</>
	);
}

export default Layout;
```

Maintenant que nous avons notre `Layout`, nous pouvons l'utiliser dans notre `router`.

```jsx
import { createBrowserRouter, RouterProvider } from "react-router-dom";

// router creation
const router = createBrowserRouter([
	{
		path: "/",
		element: <Layout />,
		children: [
			{
				path: "/",
				element: <Home />,
			},
			{
				path: "/about",
				element: <About />,
			},
		],
	},
]);
```

Oh, un nouveau mot clé `children` est apparu, il permet de définir les routes enfants. C'est à dire les routes qui sont dans le `Layout`.

Dans notre exemple, `/` possède le composant `<Home />` et va donc être affiché dans le `Layout` à la place de `<Outlet />`. La même chose pour `/about`.

Si je souhaite avoir une route qui n'est pas dans le `Layout`, je peux la définir en dehors.

![outlet](./assets/outlet.png)

```jsx
const router = createBrowserRouter([
	{
		path: "/",
		element: <Layout />,
		children: [
			{
				path: "/",
				element: <Home />,
			},
			{
				path: "/about",
				element: <About />,
			},
		],
	},
	{
		path: "/contact",
		element: <Contact />,
	},
]);
```

Si vous souhaitez avoir une route "dynamique", alors, vous pouvez utiliser les `paramètres`.

```jsx
const router = createBrowserRouter([
	{
		path: "/",
		element: <Layout />,
		children: [
			{
				path: "/",
				element: <Home />,
			},
			{
				path: "/about",
				element: <About />,
			},
			{
				path: "/user/:id",
				element: <User />,
			},
		],
	},
]);
```

Pour récupérer le paramètre, vous pouvez utiliser `useParams()`.

```jsx
// User.jsx

import { useParams } from "react-router-dom";

function User() {
	// Ici, useParams est un hook qui permet de récupérer les paramètres de l'URL
	// Dans notre cas, on récupère l'id. l'"id" est la clé que nous avons défini dans la route
	const { id } = useParams();

	return <h1>User {id}</h1>;
}
```

:link: _Liens utiles_

-   [React Router | Wild code school](https://wildcodeschool.github.io/workshop-react-router/#pourquoi-react-router)

---

### :calendar: 09/04/2024

:package: _Récap du jour_

Les API ! C'est cool ! Mais c'est quoi une API ?

#### C'est quoi une API ?

Une API (Application Programming Interface) est un ensemble de règles et de protocoles qui permettent à des logiciels de communiquer entre eux.

#### Les types d'API

Il existe plusieurs types d'API :

-   API REST
-   API SOAP
-   API GraphQL
-   ...

Nous allons nous concentrer sur les API REST ✨ !

API REST pour `Representational State Transfer` est un style d'architecture qui définit un ensemble de contraintes pour la création de services web.

![rest](./assets/api_rest.png)

#### Les méthodes HTTP

Les méthodes HTTP sont des verbes qui permettent de définir l'action à effectuer sur une ressource. Il y a une méthode pour chaque action.

| Méthode HTTP | Action   | Description                   |
| ------------ | -------- | ----------------------------- |
| POST         | `C`REATE | Créer une entrée              |
| GET          | `R`EAD   | Récupérer une information     |
| PUT          | `U`PDATE | Mettre à jour une information |
| DELETE       | `D`ELETE | Supprimer un élément          |

#### Les codes de statut HTTP

Les codes de statut HTTP sont des codes numériques qui indiquent le résultat d'une requête HTTP. Il y a pleins de catégories de codes :

-   `1xx` : Information
-   `2xx` : Succès
-   `3xx` : Redirection
-   `4xx` : Erreur client
-   `5xx` : Erreur serveur

#### Consommer une API en JS

Pour `consommer` une API en JS, il faut utiliser la méthode `fetch()`.

```js
fetch("https://api.exemple.com")
	.then((response) => response.json())
	.then((data) => console.log(data));
```

#### Créer une API en JS

Pour créer une API en JS, on va utiliser `express` qui est un framework pour Node.js.

```js
const express = require("express");
const app = express();

const things = [
	{ id: 1, name: "thing1" },
	{ id: 2, name: "thing2" },
	{ id: 3, name: "thing3" },
];

// Route pour récupérer les choses
app.get("/api", (req, res) => {
	res.json(things);
});
```

Ici, nous avons une API qui retourne un tableau d'objets.

#### JSON

Le JSON (JavaScript Object Notation) est un format de données textuelles qui est facile à lire et à écrire pour les humains.

```json
{
	"key": "value",
	"key2": "value2"
}
```

:link: _Liens utiles_

-   [JS [FR] - API & fetch](https://docs.google.com/presentation/d/1WE8ZjzOgp8FZxVkXV2Risl5PR-vlm_PGfH7Tk020ZwI/edit#slide=id.p)
-   [Express [FR] - API & express](https://docs.google.com/presentation/d/1OEwzuMFD91XF04rLOjP1iIWt3a1qG2h5Ppa6Q3ZXZZs/edit#slide=id.p)
-   [API-Express](https://github.com/WildCodeSchool-2024-02/JS-RemoteFR-CrewDragon-API-Express)
-   [API REST : définition](https://www.redhat.com/fr/topics/api/what-is-a-rest-api#rest)

---

### :calendar: 05/04/2024

:package: _Récap du jour_

Nous allons pas écrire grand chose pour ce jour car ce n'est pas une généralité mais quand même, nous allons parler du workflow git de la Wild.

#### Le workflow git de la Wild

Nous allons avoir 3 branches disctinctes :

-   [x] `main 🔐` : c'est la branche qui contient le code de production, c'est à dire le code qui est en ligne.

-   [x] `dev 🔐` : c'est la branche qui contient le code de développement, c'est à dire le code qui est en cours de développement.

-   [x] `features` : c'est la branche qui contient le code de la feature que vous êtes en train de développer.

#### Nommage des branches

Nous vous conseillons d'appeler vos branches de la manière suivante :

-   `<N° du sprint><N° de l'US>_<Ma feature>`

Ex :

-   `S01US01_navbar`
-   `S02US12_contact_form`

#### Quand je suis content, je commit

Nous vous conseillons de faire un commit à chaque fois que vous avez fini une tâches technique.

-   [x] HTML
-   [x] Style
-   [x] Validation

Par exemple.

#### Les labels

Nous vous quelques labels pour définir l'état de votre US.

-   REVIEWED
-   CHANGES REQUESTED
-   CORRECTIONS DONE
-   CONFLICTS
-   CONFLICTS RESOLVED

:link: _Liens utiles_

-   [Git / GitHub [FR] - Git Workflow](https://docs.google.com/presentation/d/1PTOk3AvxB2y3VbupsjRk0fNrZwhuczkC--tc7pN4nq0/edit#slide=id.g21e144eb45e_0_611)

---

### :calendar: 04/04/2024

Nous avons fait un petit cours sur la méthodologie Agile avec le framwork Scrum.

Nous n'allons pas faire un gros récap, car le cours est assez long.

Mais en gros, pourquoi choisir la méthodologie Agile dans un projet ?

![what-is-the-difference-between-agile-and-waterfall-model.png (750×500)](https://codetiburon.com/app/uploads/2017/02/what-is-the-difference-between-agile-and-waterfall-model.png)

Regardé le cours, et si vous avez des questions, n'hésitez pas. (J'ai aussi mis un lien vers mon cours sur github)

:package: _Récap du jour_

![agile](./assets/agile.png)

:link: _Liens utiles_

-   [SCRUM [FR] - Agile Methodology & SCRUM](https://docs.google.com/presentation/d/18g-SYdgsxzNdLvIV9wfBDl9key2rPCQfOPn_1hpmOmI/edit)
-   [GorskiAnthony/CoursAgiles](https://github.com/GorskiAnthony/CoursAgiles)

---

### :calendar: 27/03/2024

:package: _Récap du jour_

On continue sur notre lancée avec React.

Nous avons appréhendé les props.

### 💡Ce qu'il faut retenir

#### Les props

![props](./assets//props.png)

![props2](./assets/props_img.png)

Les props sont des arguments passés à un composant React.

On passe **TOUJOURS** les props de parent à enfant.

```js
// src/App.js
import Welcome from "./components/Welcome";

function App() {
	return (
		<div>
			<Welcome name="Hermione" />
			<Welcome name="Ron" />
			<Welcome name="Harry" />
		</div>
	);
}
```

Props est un objet qui contient les propriétés passées à un composant.

```js
// src/components/Welcome.js
function Welcome(props) {
	console.log(props);
	/* ex: { name: "Hermione" }  */
	return <h1>Hello, {props.name}</h1>;
}
```

### Pour brillé en société

#### La destructuration

La destructuration permet de récupérer une valeur d'un objet ou d'un tableau.

Dans notre exemple, voilà comment on peut faire :

```jsx
// src/components/User.jsx

function User(props) {
	const { firstname } = props;
	return (
		<div>
			<h1>{firstname}</h1>
		</div>
	);
}

// OU cette façon qui est plus utilisée

function User({ firstname }) {
	return (
		<div>
			<h1>{firstname}</h1>
		</div>
	);
}
```

### Rappel

Les retours implicites en JS

```js
// return implicite
const sum = (a, b) => a + b;

// syntaxe classique
const multiply = (a, b) => {
	return a * b;
};

console.log(sum(5, 7));
console.log(multiply(2, 2));
```

:link: _Liens utiles_

-   [Workshop React](./assets/workshop2.png)

---

### :calendar: 26/03/2024

:package: _Récap du jour_

![dance](https://media.giphy.com/media/wAxlCmeX1ri1y/giphy.gif?cid=ecf05e47xatcijrvxgr5b1qfiy80uxfjga683vp0mixu3nuu&ep=v1_gifs_search&rid=giphy.gif&ct=g)

**REACT 👏👏👏**

**REACT 👏👏👏**

**REACT 👏👏👏**

Et oui, nous entamons la partie React de notre formation.

Alors qu'avons-nous vu aujourd'hui ?

### 💡Ce qu'il faut retenir

#### C'est quoi React ?

React est une **bibliothèque** JavaScript pour la construction d'interfaces utilisateur.

#### Pourquoi React ?

-   **Facile à apprendre** : React est facile à apprendre, surtout si vous avez des connaissances en HTML, CSS et JavaScript.
-   **Réutilisable** : React vous permet de créer des composants réutilisables.
-   **Performant** : React utilise une technique appelée DOM virtuel qui améliore les performances de l'application.

#### JSX

JSX est une extension de la syntaxe JavaScript qui permet d'écrire du HTML dans du JavaScript.
Alors le JSX ça ressemble à l'html, à l'odeur, à la couleur, mais ce n'est pas de l'html.

```js
const element = <h1>Hello, world!</h1>;
```

#### Les composants

Les composants sont les éléments de base de React. Ils permettent de diviser l'interface utilisateur en morceaux indépendants et réutilisables.

```js
function Welcome() {
	return <h1>Hello world!</h1>;
}
```

:link: _Liens utiles_

Le cours viendra plus tard, car il est assez long et je ne veux pas vous spoiler. 😎

-   [Workshop React](./assets/workshop1.png)
-   [JS-RemoteFR-CrewDragon-HtmlToReact](https://github.com/WildCodeSchool-2024-02/JS-RemoteFR-CrewDragon-HtmlToReact)
-   [React Developer Tools – React](https://react.dev/learn/react-developer-tools)

---

## Saison 2️⃣

### :calendar: 19/03/2024

:package: _Récap du jour_

Node.js, c'est quoi ? C'est un environnement d'exécution JavaScript côté serveur.

Node.js est basé sur le moteur JavaScript V8 de Chrome.

#### Comment ça marche ?

Pour utiliser Node.js, il faut installer Node.js sur votre machine => [Node.js](https://nodejs.org/en/)

Ensuite, vous pouvez écrire du code JavaScript dans un fichier `.js` et l'exécuter avec Node.js.

```shell
$ node
> console.log("Hello World !");
```

Pas terrible comme utilisation, du coup, nous allons utiliser plutôt un fichier.

```js
// index.js
console.log("Hello World !");
```

```shell
$ node index.js
# output
Hello World !
```

### NPM

[NPM](https://www.npmjs.com/) (Node Package Manager) est un gestionnaire de paquets pour Node.js.

Il permet d'installer des paquets (bibliothèques) pour Node.js.

```shell
$ npm install chalk@4.1.2
```

Détail de la commande :

-   `npm` : le gestionnaire de paquets
-   `install` : commande pour installer un paquet
-   `chalk` : le nom du paquet
-   `@4.1.2` : la version du paquet

Je prend la version 4.1.2 de chalk car la version 5 ou plus utilise ESM (ECMAScript Modules) et je ne veux pas vous embrouiller avec ça.

```js
// index.js
const chalk = require("chalk");

console.log(chalk.blue("Hello World !"));
```

:link: _Liens utiles_

-   [JS [FR] - What is Node?](https://docs.google.com/presentation/d/1ngtYXEY8nngkFq-SOg97Hq-wK7x-1OUKpm78ZLBZO7A/edit)
-   [Node.js](https://nodejs.org/en)
-   [npm | Home](https://www.npmjs.com/)

---

### :calendar: 14/03/2024

**Partie 2 / 2**

:package: _Récap du jour_

Encore rien de nouveau, mais ça ne fait pas de mal 😎

N'hésite pas à aller au [05/03/2024](#calendar-05032024), c'est quasiment le même cours.

### :bulb: Pour brillé en société

#### Optional chaining

L'opérateur de chaînage optionnel `?.` permet de lire la valeur d'une propriété située au sein d'une chaîne de connexion avec une valeur `null` ou `undefined` sans lever d'erreur.

```js
let user = {}; // l'utilisateur est sans nom

alert(user?.address?.street); // undefined (pas d'erreur)
```

Alors que sans l'opérateur de chaînage optionnel, nous aurions une erreur :

```js
let user = {}; // l'utilisateur est sans nom

alert(user.address.street); // Erreur !
```

#### Arrow function

Les fonctions fléchées sont des raccourcis pour déclarer des fonctions.

```js
// syntaxe
// ici, en plus de la syntaxe, nous avons un return implicite
let sum = (a, b) => a + b;

/* équivalent à */

let sum = function (a, b) {
	return a + b;
};
```

La différence entre `classic function` & `arrow function`

```js
const user = {
	name: "anthony",
	classicFunction: function () {
		console.log(this, this.name);
	},
	arrowFunction: () => {
		console.log(this, this.name);
	},
};

user.classicFunction();
user.arrowFunction();

/**********/
/* output */
/**********/

// {name: "anthony", classicFunction: ƒ, arrowFunction: ƒ} "anthony"

// Window {window: Window, self: Window, document: document, name: "", location: Location, …} undefined
```

Ce que ça veut dire, c'est que les fonctions fléchées n'ont pas de `this` propre, elles prennent le `this` de leur parent.

ET SURTOUT ! JAVA !== JAVASCRIPT

code java pour un hello world:

```java
public class HelloWorld {
  public static void main(String[] args) {
    System.out.println("Hello, World");
  }
}
```

code javascript pour un hello world:

```js
console.log("Hello, World");
```

Alors, c'est plus simple JS non ? :wink:

:link: _Liens utiles_

-   [JS [FR] - JS Basics](https://docs.google.com/presentation/d/1Nz2FAA4SaasV1qoXbTUPtjuJ8QvOoV1w76JBW9YN9Yw/edit)

---

### :calendar: 13/03/2024

**Partie 1 / 2**

:package: _Récap du jour_

Bon, rien de trop nouveau sous le soleil.
Mais on quand même vu les bases.

N'hésite pas à aller au [05/03/2024](#calendar-05032024), c'est quasiment le même cours.

:link: _Liens utiles_

-   [Can I use... Support tables for HTML5, CSS3, etc](https://caniuse.com/)
-   [Optional chaining (?.) - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining)

### :calendar: 12/03/2024

:package: _Récap du jour_

<em>✨ Enfin la manipulation du DOM ✨</em>

![noo](https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExNmJvY29zN3JkbzZwb2MxZDZ5N3QxOTIzbjJuazhydDJhaDh1ZWo3MyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/6gLyE15StAs3C/giphy.gif)

### Ce qu'il faut retenir

Le DOM (Document Object Model) est une interface de programmation pour les documents HTML.

Il représente la page web sous forme d'arbre d'objets.

Nous avons besoins de 3 étapes pour manipuler le DOM :

1. **Sélectionner un élément**
2. **Ajouter un événement**
3. **Modifier le contenu**

#### Sélectionner un élément

Il existe plusieurs façons de sélectionner un élément :

-   `document.getElementById('id')`
-   `document.getElementsByClassName('class')`
-   `document.getElementsByTagName('tag')`

Moi je préfère utiliser les méthodes suivantes :

-   `document.querySelector('selecteur')`
-   `document.querySelectorAll('selecteur')`

#### Ajouter un événement

Il existe plusieurs type d'événements :

-   `click` : au clic
-   `change` : à la modification
-   `mouseover` : au survol
-   ...

#### Modifier le contenu

Il existe plusieurs manière de modifier le contenu :

-   `innerHTML` : permet de modifier le contenu HTML
-   `textContent` : permet de modifier le contenu textuel
-   `setAttribute` : permet de modifier un attribut
-   `style` : permet de modifier le style
-   ...

#### Comment fonctionne la balise script

![script](./assets/classicImportJs.png)
![script](./assets/asyncImportJs.png)
![script](./assets/deferImportJs.png)

### 💡 Pour brillé en société

#### IIFE

Ici, nous avons une fonction qui s'appel et s'execute directement.
On appelle ça une [IIFE](https://developer.mozilla.org/fr/docs/Glossary/IIFE) (Immediately Invoked Function Expression).

```js
//IIFE

(function () {
	//code
})();
```

:link: _Liens utiles_

-   [JS [FR] - DOM basics](https://docs.google.com/presentation/d/1oKNELlK8d8x4fcGj_w0m6lmCbxS3ZKvtnibw8b7jjxg/edit)
-   [DOM workshop | Wild code school](https://wildcodeschool.github.io/workshop-js-dom/)
-   [GorskiAnthony/tp-todo](https://github.com/GorskiAnthony/tp-todo)

## Saison 1

### :calendar: 08/03/2024

:package: _Récap du jour_

_Comment faire une bonne démo_ voilà le thème abordé aujourd'hui.

Nous avons vu ce qu'il fallait faire et ne pas faire lors d'une démo. ⬇️

-   [x] N’attendez pas la dernière minute
-   [x] Soyez clair et concis
-   [x] Appuyez-vous sur votre support
-   [x] Adaptez-vous à votre interlocuteur
-   [x] Préparez la répartition de la parole
-   [x] Anticipez les questions / réponses
-   [x] Entraînez-vous !!!!!

Nous commençons aussi les press reviews.
Chaque semaine, vous devez parler d'un sujet en relation avec le dev'.

-   Un fait d'actualité
-   Un nouvel outil
-   Un framework
-   Etc.

:link: _Liens utiles_

-   [Onboarding [FR] - How to do a good demo](https://docs.google.com/presentation/d/1ZaYBN_BnKqAhBKcG_FMNP3coTk_nVaEaS7qPf3Dq12U/edit#slide=id.p1)

### :calendar: 07/03/2024

:package: _Récap du jour_

Nous avons vu aujourd'hui comment passer des wireframes papier vers un prototype sur figma ainsi que les bonnes pratiques UX/UI.

Pour rappel :

![](assets/ux-usability-banner.png)

:link: _Liens utiles_

-   [UX/UI [FR] - Website conception](https://docs.google.com/presentation/d/1cMJyttPWY6dyjU3bPfMU1VVeP-yQQzK0LHRL1CR1IjU/edit#slide=id.p)
-   [UX/UI [FR] - Web design](https://docs.google.com/presentation/d/1EqV-WMtcyuntKUYJnZC7G9N49gnrZvjvGvcZr9BOfPw/edit#slide=id.p)

---

-   [Analyse et vérification du contraste | Adobe Color](https://color.adobe.com/fr/create/color-contrast-analyzer)
-   [User Inyerface - A worst-practice UI experiment](https://userinyerface.com/)

---

Merci à [Fanny](https://github.com/fanny-pretre) pour les liens suivants :

-   [Définition de la Loi de Fitts, son rôle dans l'expérience utilisateur (UX)](https://www.usabilis.com/definition-loi-de-fitts/)
-   [color.adobe.com/fr/trends](https://color.adobe.com/fr/trends)
-   [Les lois de la Gestalt appliquées au Design | bluedrop.fr, Agence web Drupal - Usinons Drupal](https://www.bluedrop.fr/content/les-lois-de-la-gestalt-appliqu%C3%A9es-au-design#:~:text=Cette%20th%C3%A9orie%20cherche%20%C3%A0%20expliquer,une%20vision%20globale%20des%20choses)

---

-   [WAVE Evaluation Tool](https://chromewebstore.google.com/detail/wave-evaluation-tool/jbbplnpkjmmeebjpijfedlgcdilocofh)

### :calendar: 06/03/2024

:package: _Récap du jour_

#### C'est quoi git & github ❓

`Git` est un logiciel de versionning, c'est à dire qu'il permet de gérer les versions de notre code, il est en local.

`Github` est un service en ligne qui permet de stocker notre code en ligne.

#### Les commandes de bases

| commande                  | description                                 |
| ------------------------- | ------------------------------------------- |
| `git init`                | permet d'initialiser un repo git            |
| `git add .`               | permet d'ajouter tous les fichiers au stage |
| `git commit -m "message"` | permet de créer un commit                   |
| `git push`                | permet d'envoyer le code sur github         |
| `git pull`                | permet de récupérer le code sur github      |
| `git status`              | permet de voir l'état du repo git           |
| `git checkout`            | permet de changer de branche                |
| `git switch`              | depuis la version 2.23                      |
| `git branch`              | permet de créer une branche                 |

![git](assets/gitImg.png)

Si vous souhaitez avoir un git cheat sheet, voici le lien : [Git Cheat Sheet](./assets/git-cheat-sheet-education.png)

```mermaid
gitGraph
   commit
   commit
   branch develop
   checkout develop
   commit
   commit
   checkout main
   merge develop
   commit
   commit
```

Ensuite, à vous l'atelier git & github !

:link: _Liens utiles_

-   [Git / GitHub [FR] - Intro](https://docs.google.com/presentation/d/1e4G26qbY_5vGG0l9w05TCuIv_Kkw-bxFeZ4Q1hc6xFs/edit#slide=id.p)

---

-   [WorkShop Chip & Dale](https://wildcodeschool.github.io/workshop-git/README-FR)

---

-   [SSH Key & Git by Antho](./assets/GIT.pdf)
-   [Apprendre Git](https://learngitbranching.js.org/?locale=fr_FR)
-   [Simple Git Workflow | Wild code school](https://wildcodeschool.github.io/workflow-project-1/README-FR)

### :calendar: 05/03/2024

:package: _Récap du jour_

✨ _LES BASES PROGRAMMATIONS_ ✨

![gif](https://media4.giphy.com/media/5aLrlDiJPMPFS/200w.gif?cid=6c09b952yip4czs96byhqxsyhdve8k5atj8kwqv0ga348rgg&ep=v1_gifs_search&rid=200w.gif&ct=g)

Alors, oui, c'est assez dur, il y a plein de choses à connaître, mais en vrai. Çaaa vaaaaa !

Les éléments communs pour tout le monde :

-   Les variables
-   Les conditions
-   Les tableaux
-   Les boucles
-   Les fonctions
-   🎁 les 6 falsy values

#### Les variables

Une variable est un espace mémoire qui permet de stocker une valeur.

```js
let maVariable = "Hello World !";
```

Attention, quand une variable est réassignée, elle perd sa valeur précédente.

```js
let prenom = "anthony";

prenom = "samuel";
```

anthony est remplacé par samuel.

![variable](assets/variables.png)

#### Les types de données

Il existe plusieurs types de données :

Les primitifs :

-   `string` : chaîne de caractères
-   `number` : nombre
-   `boolean` : vrai ou faux
-   `null` : nul
-   `undefined` : non défini
-   ...

Les non primitifs :

-   `object` : objet
-   `array` : tableau
-   `function` : fonction
-   ...

#### Les opérateurs

Il y a les opérateurs mathématiques que vous connaissez déjà, mais il y en a d'autres.

Voilà le lien pour les opérateurs : [Opérateurs](https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Expressions_et_Op%C3%A9rateurs)

#### Les tableaux

Les tableaux permettent de stocker plusieurs valeurs.

```js
let monTableau = [2, "Hello", true, ["coucou"]];
```

Il existent plusieurs méthodes pour manipuler les tableaux :

-   `push()` : ajoute un élément à la fin du tableau
-   `pop()` : supprime le dernier élément du tableau
-   `shift()` : supprime le premier élément du tableau
-   `unshift()` : ajoute un élément au début du tableau

#### Les conditions

Les conditions permettent de faire des choix dans le code.

L'architecture d'un `if/else`:

```js
// Une condition doit obligatoirement se répondre par true ou false
if (condition) {
	// code
} else if (condition) {
	// code
} else {
	// code
}
```

Ex:

```js
let maVariable = "Bouh";

if (maVariable === "Hello World !") {
	console.log("C'est cool !");
} else {
	console.log("C'est pas cool !");
}
```

💡 Astuce !

Si votre condition est un booléen (`true` ou `false`), vous pouvez faire comme ça :

```js
let maVariable = true;

if (maVariable) {
	console.log("C'est cool !");
} else {
	console.log("C'est pas cool !");
}
```

Ou encore :

```js
if (!maVariable) {
	console.log("C'est pas cool !");
} else {
	console.log("C'est cool !");
}
```

#### Les boucles

Les boucles permettent de répéter une action.

Il y a 3 informations importantes :

-   L'initialisation
-   La condition d'arrêt
-   L'incrémentation

`Boucle for`:

```js
for (let i = 0; i < 10; i++) {
	console.log(i);
}
```

`Boucle while & do while`: (attention à ne pas faire de boucle infinie !)

```js
let i = 0;

while (condition) {
	// code

	i++;
}
```

```js
let i = 0;

do {
	// code
	i++;
} while (condition);
```

Il existe tout un tas d'autre façon de boucler, mais ce sont les plus courants.

#### Les fonctions

Les fonctions permettent de réutiliser du code.

La syntaxe :

![fonction](assets/syntaxe.png)

-   `function` : mot clé pour déclarer une fonction
-   `maFonction` : nom de la fonction
-   `()` : les paramètres
-   `{}` : le corps de la fonction

```js
function maFonction() {
	console.log("Hello World !");
}

/* réutilisation de la fonction maFonction */
maFonction();
maFonction();
```

![fonction](assets/fonctions.png)

⚠️ Attention, une fonction qui ne fait qu'un `console.log()` ne sert à rien !
Il faut que la fonction retourne (`return`) une valeur.

```js
function maFonction() {
	return "Hello World !";
}
```

Et pour récupérer la valeur de la fonction :

```js
let maVariable = maFonction();
```

<details>
  <summary>Un exemple qui regroupe plein d'info 😎</summary>

```js
// ma variable students qui est un tableau d'étudiants
const students = [
	"Aurélien",
	"Mohamed",
	"Laurent",
	"Frank",
	"Kelly",
	"Fanny",
	"Amandine",
	"Vincent",
	"David",
	"Baptiste",
	"Sacha",
	"Nicolas",
	"Kylian",
	"Fab",
	"Jeviraj",
	"Simon",
];

// une fonction sayHello qui prend 1 paramètre `name`
function sayHello(name) {
	console.log("Coucou " + name + " 👋");
}

// Une boucle for qui commence à 0 jusqu'à la taille du tableau
for (let i = 0; i < students.length; i += 1) {
	// utilisation de la fonction sayHello qui prend un argument
	// students[i] qui vaut le prénom de mon tableau "students" à l'index `i`
	sayHello(students[i]);
}
```

</details>

#### 🎁 Les 6 falsy values

Les 6 falsy values sont des valeurs qui sont évaluées à `false` dans une condition.

-   `false`
-   `0`
-   `""`
-   `null`
-   `undefined`
-   `NaN`

Si vous voulez en savoir plus, voici un article qui en parle : [Les 6 falsy values](https://developer.mozilla.org/fr/docs/Glossaire/Falsy)

:link: _Liens utiles_

-   [Programming Basics [FR]](https://docs.google.com/presentation/d/1OBivzxzUzk8J5-L93OMpW0ObVeInsFYmmluh9J0UeBE/edit)
-   [Programming Basics | Wild code school](https://wildcodeschool.github.io/workshop-programming-basics/)

### :calendar: 01/03/2024

:package: _Récap du jour_

Notre petit cours d'aujourd'hui était sur les bases du web.
Le principe est de comprendre comment fonctionne le web, et ainsi, faire la différence entre le `web` et `internet`.

### 💡Ce qu'il faut retenir

**Web**

Le web est un système de publication et de consultation de documents hypertextes liés entre eux et accessibles via le réseau internet.

**Internet**

Internet est un réseau informatique mondial accessible au public. Il permet de partager des informations et des ressources.

**Protocoles**

-   HTTP(S) : Hypertext Transfer Protocol (Secure)
-   FTP : File Transfer Protocol
-   etc.

**Navigateur**

Un navigateur web est un logiciel permettant de consulter des pages web. Les plus connus sont Chrome, Firefox, Safari, Edge, Opera.

**URL**

Une URL (Uniform Resource Locator) est une adresse web. Elle est composée de plusieurs éléments :

-   Protocole : `http://` ou `https://`
-   Nom de domaine : `www.google.com`
-   Chemin : `/search?q=hello+world`

### Bonus

![ipv4 ipv6](https://academy.avast.com/hs-fs/hubfs/New_Avast_Academy/IPv4%20vs.%20IPv6%20What%E2%80%99s%20the%20Difference/IPv4-vs-IPv6-FR.png?width=660&name=IPv4-vs-IPv6-FR.png)

:link: _Liens utiles_

-   [Web [FR] - Web Basics](https://docs.google.com/presentation/d/1fDH6eD-udpIGQ8b_LF2CLQCJwN94Bj_h33K4MmD6xMo/edit#slide=id.p)

### :calendar: 29/02/2024

:package: _Récap du jour_

Nouvelle connaissance débloquée : Le Terminal.

![giphy](https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExamRzNDN0bXdqN2V4bHB0cGVkMDY1eXNwNjhiMGhwZHZrbHI4NnJ6byZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/lptIayuGHV9Utu3iTv/giphy.gif)

Oui, le terminal est un outil puissant, mais il peut être intimidant au début. C'est pourquoi nous avons vu les bases pour vous aider à vous familiariser avec cet outil.

### 💡Ce qu'il faut retenir

Le kit de survie du terminal :

| Commande  | Description                                          |
| --------- | ---------------------------------------------------- |
| `pwd`     | affiche le répertoire courant                        |
| `ls`      | liste les fichiers et dossiers du répertoire courant |
| `cd`      | change de répertoire                                 |
| `mkdir`   | crée un dossier                                      |
| `touch`   | crée un fichier                                      |
| `rm`      | supprime un fichier                                  |
| `rm -r`   | supprime un dossier                                  |
| `mv`      | déplace un fichier ou un dossier                     |
| `cp`      | copie un fichier ou un dossier                       |
| `cat`     | affiche le contenu d'un fichier                      |
| `echo`    | affiche un message à l'écran                         |
| `clear`   | efface le terminal                                   |
| `.`       | répertoire courant                                   |
| `..`      | répertoire parent                                    |
| `man`     | affiche le manuel d'une commande                     |
| `history` | affiche l'historique des commandes                   |

Bien sûr, il y a beaucoup plus de commandes, mais ce sont les bases pour commencer.

:link: _Liens utiles_

-   [Web [FR] - Terminal](https://docs.google.com/presentation/d/1LWyNTqUL8qsP2bRF5a9V--iGav9wt2Q2b08on67Coz8/edit#slide=id.p)

---

-   [Voyage au centre de l’ordinateur | Wild code school](https://wildcodeschool.github.io/workshop-terminal/README-FR#conna%C3%AEtre-ses-racines)
-   [Exo console](https://www.notion.so/anthony-gorski/Console-bf80d102e2dd4a039a4a8f752cce619e)

### :calendar: 28/02/2024

:package: _Récap du jour_

Ladies and gentlemen, aujourd'hui, nous avons vu les bases du responsive design.

![woaw](https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExZDhzdTN5amh5d3NrZGY1aXZyMnlsMDB2Zm9ocXpocHVjOHYwdHhlaSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/iFJfZNSDDQUVk9bvDC/giphy.gif)

Le responsive, c'est la capacité d'un site web à s'adapter à la taille de l'écran de l'utilisateur. C'est un élément essentiel pour un site web, car il est important que le site soit lisible sur tous les supports.

Nous avons parler des grids et flexbox, qui sont des outils de mise en page en CSS. Ils permettent de créer des mises en page complexes et de les rendre responsive.

### 💡Ce qu'il faut retenir

Voilà un petit récap des breakpoints (points de rupture) les plus utilisés :

![img](./assets/mediaquerie.png)

:link: _Liens utiles_

-   [CSS [FR] - Responsive Web Design](https://docs.google.com/presentation/d/1Uk_vi8dYmhXGHFg32Bdd-8PSTNGaqF_EibH_Lum6-bI/edit)

---

-   [Am I Responsive?](https://ui.dev/amiresponsive?url=https://www.wildcodeschool.com/fr-fr/)
-   [Interactive CSS Grid Generator | Layoutit Grid](https://grid.layoutit.com/)
-   [:root - CSS : Feuilles de style en cascade | MDN](https://developer.mozilla.org/fr/docs/Web/CSS/:root)

### :calendar: 27/02/2024

:package: _Récap du jour_

Aujourd'hui, nous avons vu les bases de l'HTML et du CSS et comment lier les deux.

Je vous rassure, il n'est pas nécessaire de tout retenir, mais il est important de comprendre les concepts de base.

### 💡Ce qu'il faut retenir

-   HTML : c'est la structure de la page web
-   CSS : c'est la mise en forme de la page web
-   Les balises HTML sont des éléments de structure
    -   `<h1></h1>` : titre de niveau 1
    -   `<p></p>` : paragraphe
    -   `<a></a>` : lien
    -   `<img />` : image
    -   etc.
-   Les sélecteurs CSS permettent de cibler des éléments HTML
    -   `h1` : cible tous les titres de niveau 1
    -   `.ma__classe` : cible tous les éléments ayant la classe `class="ma__classe"`
    -   `#mon__id` : cible l'élément ayant l'id `id="mon__id"`

```html
<!DOCTYPE html>
<html>
	<head>
		<title>Titre de la page</title>
		<link rel="stylesheet" type="text/css" href="style.css" />
	</head>
	<body>
		<h1>Titre de la page</h1>
		<p>Un paragraphe</p>
	</body>
</html>
```

```css
h1 {
	color: blue;
	font-size: 12px;
}
```

Concernant les propriétés CSS, il est important de comprendre qu'il est impossible de toutes les retenir. C'est pourquoi il est essentiel de savoir où trouver les informations.
L'anglais est un atout pour la programmation, car la majorité des ressources sont en anglais.

:link: _Liens utiles_

-   [HTML [FR] - Basics](https://docs.google.com/presentation/d/1N-yUZcQfiuh8nInZXnB5D5uTaua9Tp4IYMk98IJ_yuY/edit#slide=id.p)
-   [CSS [FR] - Basics](https://docs.google.com/presentation/d/1-t0tqyjMs-FwVG723MSuzYAoKEra8LSZ-sRxADr1F64/edit#slide=id.p)

---

-   [W3Schools Online Web Tutorials](https://www.w3schools.com/)
-   [HTML Reference](https://www.w3schools.com/tags/default.asp)
-   [CSS Reference](https://www.w3schools.com/cssref/index.php)
-   [Méthodologie BEM pour le CSS](https://alticreation.com/bem-pour-le-css/)

---

-   [Flexbox Froggy - Un jeu pour apprendre les flexbox CSS](https://flexboxfroggy.com/#fr)
-   [Grid Garden - Un jeu pour apprendre les grid CSS](https://cssgridgarden.com/#fr)
-   [CSS Diner - Un jeu pour apprendre les sélecteurs CSS](https://flukeout.github.io/)
-   [CSS Battle - Un jeu pour apprendre le CSS](https://cssbattle.dev/)
-   [Codepen - Un site pour partager du code HTML/CSS/JS](https://codepen.io/)

### :calendar: 26/02/2024

:package: _Récap du jour_

Hello 👋 !

Aujourd'hui c'est présentation ! Ensuite, on continue avec une petite présentation des cursus JS & PHP

Vous avez même eu le mot du CEO de la Wild Code School !

:link: _Liens utiles_

-   [2024 - Programme des prochains mois](https://docs.google.com/presentation/d/1ppBPDll3PK0LSY3AFHG_zzGX5GoIEg-rARVEWTH9yKM/edit#slide=id.g210c0f5cbca_0_0)
-   [FR. 2024 Méthodes d'enseigement](https://docs.google.com/presentation/d/1-TWa72u96FVZxeBPs_FwLJIwy8M7JuNd9PBrbO6DpCU/edit#slide=id.p1)
