# Premier pas avec NodeJS

<span style='font-size:5em;'>🎆</span>

(il était temps)

## Web Basics

### Front VS Back

![FrontVSBack](../../img/frontend-vs-backend-768x432.png)

### Front-end / Back-end

| Front-end                                                                                 | Front-office                              |
| ----------------------------------------------------------------------------------------- | ----------------------------------------- |
| Partie visible de l’iceberg                                                              | Partie invisible de l’iceberg            |
| Design                                                                                    | Gestion de la masse d’utilisateurs       |
| Gestion d’un seul utilisateur                                                            | Mise en place et configuration du serveur |
| Transformation action utilisateur en données compréhensible par le Back-End               | Traitement efficace et rapide des données |
| Transformation données reçu par le BackEnd en informations compréhensible par utilisateur | Conception et communication avec la BDD   |
| Sécurité                                                                                  | Mise à disposition de Web Services        |
| SEO                                                                                       | SEO                                       |
|                                                                                           | Sécurité                                  |

### Front-office / Back-office ? 

**Front-office** = interface utilisateur visible par tous les utilisateurs (connecté ou non)

**Back-office** = interface utilisateur reservé à l'administration d'un site (connecté ou non)

## What is Node.JS ?

### Créateur

<img src="/subjects/img/ryan_dahl.png" width=300 />

**2009 -> Ryan Dahl**

**3 idées**

1. Arrêter avec les entrées et sorties bloquantes (_Event Loop_)
2. Les communautés sont bloquées
3. La portabilité des programmes

Sa réponse ? **NODE.JS**

### Chiffres

En 2018

**8M**

de serveurs à travers le monde

**1st**

Framework le plus populaire (d'après StackOverflow)

**2nd**

Technologie la plus appréciée (d'après StackOverflow)

### Comparaisons des packages disponibles selon les plateformes

<img src="/subjects/img/comparison_packages.png" width=750 />

### Pourquoi Node.JS?

#### Réflexions

> _Un langage qui n'affecte pas la façon dont vous pensez à la programmation, n'est pas intéressant à connaître_(**Alan J. Perlis**)

**House of many ideas**

- POO VS Fonctionnel
- Typage dynamique VS Typage statique
- Architecture légère VS Architecture Robuste

#### Multi-plateformes

| Plateformes |     |     |     |                                                                                                                                                                                  |
| ----------- | --: | --- | --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IOT         | = = | =   | >   | <img src="https://ruckus-www.s3.amazonaws.com/images/products/iot-controller.png"  height=100 />                                                                                 |
| Browser     | = = | =   | >   | <img src="https://cdn-images-1.medium.com/max/1200/1*F3-8rM92bbTy7JDZpkcJdw.png"  height=100 />                                                                                  |
| Desktop     | = = | =   | >   | <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR3XyofDx2Fubd7cLF47tFFLq7yU1NzAx2k4MhXfKxGrKNxCnQw" height=100 />                                                |
| Web server  | = = | =   | >   | <img src="https://b.kisscc0.com/20180723/uee/kisscc0-computer-servers-computer-icons-web-server-applica-server-database-5b561bdadab249.7043650415323698828958.jpg" height=100 /> |

#### Une communauté réactive

- 753521 packages sur `npm`

- La communauté ré-invente sans cesse

- Open-source obsessive

### The World of Node.JS

<img src="/subjects/img/worldofnodejs.png" width=750 />

**=> Your project**

## Development Basics

### Bases

#### JS
<img src="/subjects/img/pillars_js.png" width=350 />

#### Modules
<img src="/subjects/img/pillars_modules.png" width=750 />

#### Créer un module

Module = `file`

Choisir ce qu'on veut exporter

Exporting code -> 
```javascript
module.exports = someFunction
```

Importing code -> 
```javascript
require(‘./someModule.js’)

import * as myImportedModule from './someModule.js'

import myImportedModule from './someModule.js'

import { props } from './someModule.js'
```

#### NPM - Node Package Manager

Solution = 10% de votre code + 90% de code de la communauté

1 Module est décrit par :
1. ses propriétés
2. ses dépendances

Description du module => `package.json`

NPM = marketplace des modules

##### Commandes utiles

```javascript
npm init – craft an empty solution
npm install – add new local/online package
npm install <pkg> --save-dev – add package for dev purposes
npm uninstall <pkg> --save – remove a package
npm start – run the application
npm test – test the application
npm publish [tag] – share your app/package with the world
npm run <command> [-- <args>...] – run specific command describe into `package.json`
```

##### BONUS - Yarn

Autre gestionnaire de paquets (by Facebook)

```javascript
yarn init – craft an empty solution
yarn install – add new local/online package
yarn add <package...> [--dev/-D] – add package for dev purposes
yarn add <package...> – add package 
yarn global <add/bin/list/remove/upgrade> [--prefix]– add package globally 
yarn remove <pkg> – remove a package
yarn start – run the application
yarn test – test the application
yarn publish [tag] – share your app/package with the world
yarn run <command> [-- <args>...] – run specific command describe into `package.json`
```

##### TP 1 - Utiliser NPM pour gérer ses dépendances

Dans le cadre du TP, il vous faut installer tous les softs requis pour faire fonctionner l'environnement node.js.

1. Installer Node.JS (https://nodejs.org/fr/download/)
2. Créer un dossier dans votre espace de travail appelé `TP1`
3. Initialiser le dossier grâce au CLI de NPM (peu importe ce que vous saisissez, l'important c'est la génération du `package.json`)
4. Créer un fichier `index.js` à la racine du dossier `TP1` (`<votre_espace_de_travail>/TP1/index.js`)
5. Ajouter la dépendance `console-log-hello-world` à votre projet
6. Utiliser la dépendance `console-log-hello-world` dans le fichier `index.js`
7. Pour vérifier l'éxécution, ajouter un bloque `scripts` dans le `package.json` de la manière suivante: 
    ```javacript
    {
        ...contenu du package.json
        , scripts: {
            <le nom de ma nouvelle commande>: 
                '<le contenu de ma commande>',
        }
    }
    ```
8. Une fois toutes les étapes effectuées, lors de l'éxécution du script, vous devez voir afficher `Hello World`.