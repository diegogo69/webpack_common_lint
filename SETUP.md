# Setting up the webpack project


##  Create a package.json
To create a default one use:

`npm init -y`


##  Install webpack. 
Runs with `npx webpack` and outputs the project contents in the **dist** directory

`npm install --save-dev webpack webpack-cli`


##  Create a webpack config file 

The project template already have one. `touch webpack.config.js`


##  Handling HTML HtmlWebpackPlugin 

`npm install --save-dev html-webpack-plugin`


##  Loading CSS (imported on JS) 

`npm install --save-dev style-loader css-loader`

  
##  Loading images from the HTML (not css nor js)
We use html-loader to load images from an html file like **template.html**

`npm install --save-dev html-loader`


##  Installing Webpack dev server

Runs with `npx webpack serve` and is hosted on <http://localhost:8080/>

`npm install --save-dev webpack-dev-server`


## Installing webpack-merge

This allows us to use separate webpack configuration files for different modes, and merge them in a common config file   

`npm install --save-dev webpack-merge`


## Installing ESlint

`npm install --save-dev eslint @eslint/js`


### Add an eslint.config.js file:

Create JavaScript configuration file

`touch eslint.config.js`

import js from "@eslint/js";

export default [
    js.configs.recommended,

   {
       rules: {
           "no-unused-vars": "warn",
           "no-undef": "warn"
       }
   }
];

## Install Prettier locally:

`npm install --save-dev --save-exact prettier`


### create an empty config file to let editors and other tools know you are using Prettier:

`node --eval "fs.writeFileSync('.prettierrc','{}\n')"`


### create a .prettierignore file to let the Prettier CLI and editors know which files to not format

`node --eval "fs.writeFileSync('.prettierignore','# Ignore artifacts:\nbuild\ncoverage\n')"`

### Install eslint-config-prettier:

`npm install --save-dev eslint-config-prettier`

#### Add eslint-config-prettier to your ESLint configuration

__eslint.config.js (flat config):__ Import eslint-config-prettier, and put it in the configuration array – after other configs that you want to override.

```
import someConfig from "some-other-config-you-use";
import eslintConfigPrettier from "eslint-config-prettier";

export default [
  someConfig,
  eslintConfigPrettier,
];
```