# angular-guide
Angular Complete Guide


# WHat is angular?

Angular is a JavaScript Framework which allows you to create reactive Single Page Applications(SPAs)

Single Page Application : only one HTML file and a bunch of JavaScript code got from the server

# Angular vs Angular 2 vs Latest Angular version

AnguarJS(Angular 1) -> Angular 2 (rewrite) -> Angular 4, 10, 11.. 15
Angular releases version every 6 months with minor changes

$ Updating the CLI

[sudo] npm uninstall -g angular-cli @angular/cli 

npm cache verify 

[sudo] npm install -g @angular/cli 

# Angular CLI

you can create a new project using angular command line interface for angular
- ng new my-dream-app
- cd my-dream-app
- ng serve

# TypeScript 

TypeScript is a superset of JavaScript. It offers more features than vanilla JavaScript, like classes, interfaces and strong typing. However, typescript doesnt run in the browser, so it is compiled to JavaScript in the end. This compilation is handled by the CLI; one of the reasons why we need a
project management tool like CLI.

# How an Angular App Gets Loaded and Started

Initially, index.html file here is served by the server. As angular is used to create a Single Page application, the index.html is the single page which is served.



app-component is the root component created by the Angular CLI

How is angular triggered?

The answer is in the final index.html file, getting served in the browser and we can verify by inspecting the source code. We got a couple of script imports at the end which are injected by angular CLI automatically.

NG SERVES process rebuild our project which creates bundles of our projects and automatically add the right imports in the index.html file. Final file, these script imports are presents and contains our own code.

main.ts

first code that is executed by angular:

platformBrowserDynamic().bootstrapModule(AppModule)
  .catch(err => console.error(err));

This line bootstraps starts the Angular application by passing an app module to this method. The
AppModule refers to the line 'import {AppModule} from './app/app.module';' which refers to the
app.module.ts file

main.ts > app.module.ts > bootstrap array i.e bootstrap: [AppComponent] > analyze app.component > read the @Component that contains templates