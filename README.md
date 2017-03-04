# awebsite

So you want a website...

## Features

* just HTML, CSS, and JS, no weird template or preprocessor languages
* transpiles ES6, ES2016, and ES2017 with babel
* autoprefixes CSS rules
* @import statements cause separate CSS files to get concatenated into one file
* use any npm packages you want simply using require('some-module') 
* .html files get wrapped in a layout
* in dev mode files get watched for changes

## Getting Started

* install [Node.js](https://nodejs.org/en/)
* clone this repo

## Development

* run `npm start`
* open a browser to `localhost:8080`
* edit the .html, .css, .js in the /src dir

## Deploying

* open `package.json` and change "awebsite.surge.sh"
* run `npm run deploy`
* login to surge or create an account

## Under the hood

Metalsmith is running the show. There are two configurations `dev.json` and `prod.json`. The dev one watches files for changes. The prod one will minimize stuff (not yet though). 

### HTML

HTML files are handled by `metalsmith-layout` which just sticks the contents of the file into the `layouts/default.html` file. You can add frontmatter to these files, and the values will wind up in the layout. You can create new layouts if you want. 

### CSS

CSS is handled by PostCSS. Two plugins are currently being used, one that inlines @imports, and one that autoprefixes. There's a lot of other PostCSS plugins that can be added. 

### JS

JS is handled by Browserify. One transform is currently being used; 'babelify' which passes the bundled JS through babel to transpile ESlatest to ES5.
