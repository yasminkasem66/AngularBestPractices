# What is this Repository?
This repository is used along with the [Pluralsight Angular Best Practices course](https://app.pluralsight.com/library/courses/best-practices-angular/table-of-contents). 

Note that as it is here, this repo contains a project with poor practices. As you work through the Angular Best Practices course you will refactor this project to use best practices.

# Whitebeards

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.1.1.

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

## first part 
I leart one of the best practices 
1-Using angular cli 
2-file naming
3-folder structure 
4-one item per file 


## second part 
1-Single responsibilty principle =>create service for every crud operation
2-symbole naming =>service end with service word , component end with component word 
3-preferring immutability =>not mutating existing objects in memory but rather creating new object
ex instead of=> this.currentUser.classes.push(classId)
         use => this.currentUser={...this.currentUser,classes:this.currentUser.classes.concat(classId)}

ex instead of=> this.currentUser.classes = this.currentUser.classes.filter(c=>c.id!==id)
         use => this.currentUser={...this.currentUser,classes:this.currentUser.classes.filter(c=>c.id!==id)}

ex instead of=> user.classes=user.classes; this.currentUser=user   =>  this is not mutating the existing currnt user variable, it's replacing it,it's pointing the currentUSer
               variable to the  same user object 
         use => const classes= user.classes; this.currentUser={...user, classes:[...classes]}=>  this is will update currnt user variable to a new object that is populated with all properties from user and this called immutablity , change the refernce to objects to not point to the same refernce( deep clone)

concat is similar to push except it return a new array instead of pushing to an exisisting array
4-using small functions => not more than 15 line
5-using strict mode  => in tsconfig file 


## third  part 
App Module
core Module =>shared singletons service, App level component like navbar 
feature Module
shared Module => shared component directives and pipes


high level encapsulation everything in a module is package together and you only expose what's nesseccary to external modules 