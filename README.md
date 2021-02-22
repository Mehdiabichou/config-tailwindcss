# Comment configurer Tailwind

## Installation

Initialiser un projet  avec `npm init  -y`

Installer tailwindcss avec les dépendances nécessaires .

```bash
npm install tailwindcss autoprefixer postcss postcss-cli
```

Une fois installé nous allons créé 2 fichiers de configuration `postcss.config.js` et `tailwind.config.js` .

```bash
npx tailwindcss init -p 
```

On peux aussi utiliser la commande 

```bash
npx tailwindcss init -full
```

Cette commande nous permettra de récupérer toutes les class de tailwind afin de les modifier ou d'ajouter de nouvelle class à notre projet. 

Ensuite il faudra créer un fichier CSS à la racine de notre projet.

Dans ce fichier nous allons devoir importer les éléments depuis le dossier node_modules pour cela nous allons ajouter c'est ligne à nôtre fichier.

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Maintenant nous allons définir notre chemin du fichier de développement pour cela nous allons créer un dossier `dist` à l'intérieur de celui-ci un dossier CSS comme ceci :  `./dist/css/`

Enfin nous allons créer un script dans notre  fichier `package.json` qui nous permettra d'exécuter la compilation de notre fichier de développement  

```json
"script":{
" build":"tailwindcss build fichier.css -o ./dist/css/style.css",
}
```

Nous allons lancer la compilation grace au script :

```bash
npm run build
```

Une fois le script lancer il va nous créer un fichier css en sortie dans notre dossier `dist/css/fichier.css .`

maintenant nous pouvons utiliser tailwind dans notre projet.

Tailwindcss  intègre une façon de supprimer tout le css qui n'est pas utiliser pour cela ont utilise purgecss
