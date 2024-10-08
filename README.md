## Inicializar el repositorio
git init

## Crear archivo .gitignore

# Node.js
node_modules/
.env

# Logs
logs
*.log
npm-debug.log*

# Docker
docker-compose.yml
db_data/

# Testing
coverage/
jest-html-reporters/
test-output/

# IDEs and Editors
.vscode/
.idea/
.DS_Store

# OS generated files
Thumbs.db

## Primer commit
git add .
git commit -m "Initial commit: setup project structure"

## 
git remote add origin https://github.com/<tu-usuario>/<nombre-repositorio>.git


## Push cambios
git push -u origin master

## Buenas prácticas
git commit -m "Add HTML structure and basic styles"

## Ramas separadas por funcionalidades
git checkout -b feature/setup-eslint-prettier

## ESLint y Prettier
npm install --save-dev eslint prettier eslint-plugin-prettier eslint-config-prettier eslint-plugin-node eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react eslint-plugin-react-hooks

## ESLint
npx eslint --init

How would you like to use ESLint? - To check syntax, find problems, and enforce code style.
What type of modules does your project use? - JavaScript modules (import/export).
Which framework does your project use? - React.
Does your project use TypeScript? - No.
Where does your code run? - Browser.

# .eslintrc.json
{
  "extends": ["airbnb", "prettier"],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": "error"
  },
  "env": {
    "browser": true,
    "es2021": true
  }
}

# .prettierrc.json
{
  "singleQuote": true,
  "trailingComma": "all",
  "printWidth": 80,
  "tabWidth": 2,
  "semi": true
}

##  Agregar Scripts de Linting y Formateo

# package.json
{
  "name": "my-first-js-project",
  "version": "1.0.0",
  "scripts": {
    "lint": "eslint 'src/**/*.js'",
    "lint:fix": "eslint 'src/**/*.js' --fix",
    "format": "prettier --write 'src/**/*.js'",
    "start": "node src/index.js"
  },
  "devDependencies": {
    // Aquí estarán las dependencias que ya instalaste
  }
}

# Script para Linting
npm run lint

# Formateo
npm run format

# Instalo Husky y lint-stage
npx husky-init && npm install
npm install lint-staged

# package.json
"lint-staged": {
  "src/**/*.js": [
    "eslint --fix",
    "prettier --write"
  ]
}
