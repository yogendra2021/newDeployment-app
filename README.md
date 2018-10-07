# DeployDemo

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.2.4.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `-prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).
Before running the tests make sure you are serving the app via `ng serve`.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

## deployment environments
1. github 
head over to github
create a repository - followers-app
git remote add origin https://github.com/rvdabhi/followers-app.git
git push origin master
npm i -g angular-cli-ghpages
ng build --prod --base-href="https://yogendra2021.github.io/followers-app"
ngh --no-silent


2. Firebase

head over to https://console.firebase.google.com
create a project - followers-app
sudo npm install -g firebase-tools
firebase login
firebase init (From project directory)
Add  below configuration to firebase.json
"hosting": {
    "public": "dist"
  }

firebase deploy

After running solution for not found error is by adding below rewrite rules in the configuration
{
  "hosting": {
    "public": "dist",
    "rewrites": [
      {
        "source": "**",
        "destination": "/index.html"
      }
    ]
  }
}

3. Heroku
    heroku --version
    heroku login
    heroku create ?"name"
    package.json 
        1. move andgular/cli, typescript and angular/compile-cli to dependencies
        2. add script for "postinstall" : "ng build --prod"
        3. replace start script from ng server to node server.js
    git add .
    git commint -m "prepare for heroku"
    git push heroku master
    heroku open
