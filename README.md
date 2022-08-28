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


Keep in mind: Angular in the end is a JS framework, changing your DOM ('html') at runtime

# Components

Key feature of Angular. You built your whole application by composing it from a couple of components which you create on your own

app-component is the root component where we nest our other components

allows us to split application

When creating a component, we should use a decorator to specify which type of component we are declaring.
Decorators are a TypeScript feature which allow you to enhance your classes for example, enhance elements. Decorators are always attached by adding an @ sign in front of them. You need to import the component decorator from angular/core in order to use it.

import { Component } from "@angular/core";

@Component()
export class ServerComponent {

}

Note: Angular ships with a couple of packages where it basically groups its functionalities and the core package as the name implies gives us access to some of the core functionalities of angular

Now this @component decorator is known to typescript. When it parses this file and compiles it to javascript it is able to understand it.

Angular uses components to build web pages and uses modules to basically bundle different pieces. Module is a bundle of functionalities and gives angular the information which feature the app have and use.

@NgModule({
  declarations: [ // register new components here
    AppComponent,
    NewComponent
  ],
  imports: [ // allows us to import other modules
    BrowserModule
  ],
  providers: [],
  bootstrap: [AppComponent] // tells the module which component the application needs to be aware of at the point of time the whole application starts
})